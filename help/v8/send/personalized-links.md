---
title: 개인화된 링크 추적
description: 이메일에서 개인화된 링크를 추적하는 방법에 대해 알아보기
feature: Personalization
role: User
level: Beginner
exl-id: d0e00b40-e7dd-4484-b37c-fd3f3ac70fda
source-git-commit: 6e465ec24f72d0b30c4fc287da5d4c4bcaeda05b
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 2%

---

# 개인화된 링크 추적 {#tracking-personalized-links}

개인화가 포함된 이메일 콘텐츠의 링크는 추적할 특정 구문이 필요합니다.

이메일 콘텐츠(HTML 또는 텍스트)에서 JavaScript을 사용하면 두 가지 제한 사항을 포함하여 다이내믹 콘텐츠를 생성하여 수신자에게 보낼 수 있습니다.

* 스크립트는 데이터베이스에 직접 액세스할 수 없습니다(SQL 함수 및 API 함수를 사용할 수 없음).
* 링크를 추적할 수 있도록 Adobe Campaign에서 URL을 감지할 수 있어야 합니다.

## 전처리 지침 {#pre-processing-instructions}

특정 전처리 명령을 추가하여 URL을 스크립팅하고 추적할 수 있습니다. 이러한 지침은 JavaScript에서 작성되어야 하며 `<%@`(으)로 시작해야 합니다.

예제:

```
<%@ value object="myObject" xpath="@myField" %>
```

이 명령은 `myField` 개체에서 `myObject` 필드의 값을 검색합니다.

## URL 감지 {#url-detection}

추적 검색을 위해 Adobe Campaign은 [Tidy](https://www.html-tidy.org/)을 임베드하여 HTML 소스를 구문 분석하고 패턴을 감지합니다. 콘텐츠의 모든 URL을 나열하므로 개별적으로 추적할 수 있습니다. Adobe Campaign은 Tidy를 다시 사용하여 URL(`http://myurl.com`)을 Adobe Campaign 리디렉션 서버를 가리키는 URL로 바꿉니다.

예를 들어 초기 콘텐츠에서 `http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>`은(는) `http://emailing.customer.com/r/?id=h617791,71ffa3,71ffa8&p1=CustomerName`(으)로 한 특정 수신자에 대해 대체됩니다.

위치:

* &quot;h&quot;는 HTML 콘텐츠(또는 텍스트 콘텐츠의 경우 &quot;t&quot;)를 의미합니다.
* 617791은 메시지 ID / broadLog ID (16진수)입니다.
* 71ffa3은 NmsDelivery ID(16진수)입니다.
* 71ffa8은 NmsTrackingUrl ID(16진수)입니다.
* p1, p2 등은 URL에서 대체할 모든 매개 변수입니다.

### 불검출의 예 {#non-detection-example}

`<%= getURL("http://mynewsletter.com") %>`이(가) 작동하여 웹 페이지의 실제 콘텐츠를 전자 메일로 수신자에게 보냅니다. 하지만 어떤 링크도 추적되지 않습니다. MTA에서 보내기 전에 각 이메일에 대해 `"<%=getURL(..."`을(를) 실행하기 때문입니다. 수신자마다 다를 수 있으므로 Adobe Campaign은 추적을 위한 URL을 알고 태그 ID를 할당할 수 없습니다.

다운로드할 페이지가 모든 수신자에 대해 동일한 경우 가장 좋은 방법은 다음을 사용하는 것입니다.

```
<%@ include url="http://mynewsletter.com" %>
```

이 경우 페이지는 분석 중에 추적 감지 전에 다운로드됩니다. 이를 통해 Adobe Campaign은 링크를 검색하고, 태그 ID를 할당하고, 추적할 수 있습니다.

### 권장 패턴 {#recommended-pattern}

`<%@` 명령을 처리한 후 추적할 URL의 구문은 다음과 같아야 합니다.

```
<a href="http://myurl.com/a.php?param1=aaa&param2=<%=escapeUrl(recipient.xxx)%>&param3=<%=escapeUrl(recipient.xxx)%>">
```

>[!IMPORTANT]
>
>다른 모든 패턴은 Adobe에서 지원되지 않으므로 잠재적인 보안 공백을 방지하기 위해 피해야 합니다.

## URL 매개변수 {#url-parameters}

개인화된 URL이 올바르게 추적되도록 하려면 URL의 매개 변수에 대해 `escapeUrl()` 함수나 적절한 인코딩 메서드를 사용해야 합니다.

**예:**

```
<a href="http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>">Click here</a>
```

이렇게 하면 개인화된 매개 변수가 Adobe Campaign에 의해 올바르게 인코딩 및 추적됩니다.

## `<%@ foreach %>`(으)로 반복 {#foreach}

`<%@ foreach %>` 명령을 사용하면 게재에 로드된 개체 배열을 반복하여 개체와 관련된 개별 링크를 추적할 수 있습니다.

### 구문

```
<%@ foreach object="myObject" xpath="myLink" index="3" item="myItem" %>
  <!-- Content to repeat -->
<%@ end %>
```

**매개 변수:**

* **`object`**: 시작할 개체의 이름(일반적으로 추가 스크립트 개체이지만 게재가 될 수 있음)
* **`xpath`**(선택 사항): 반복할 컬렉션의 XPath. 기본값은 &quot;.&quot;입니다. 이것은 개체가 반복할 배열임을 의미합니다.
* **`index`**(선택 사항): xpath가 &quot;.&quot;가 아닌 경우 및 개체는 배열 자체이며, 개체의 항목 인덱스(0에서 시작)입니다.
* **`item`**(선택 사항): foreach 루프 내에서 `<%@ value %>`을(를) 통해 액세스할 수 있는 새 개체의 이름입니다. 기본값은 스키마의 링크 이름입니다

### 예제

게재 속성/개인화에서 문서 배열 및 수신자와 문서 간의 관계 테이블을 로드합니다.

개별 추적을 사용하여 다음 문서에 대한 링크를 표시할 수 있습니다.

```
<%@ foreach object="articleList" item="article" %>
  <a href="http://example.com/article.jsp?id=<%@ value object="article" xpath="@id" %>">
    <%@ value object="article" xpath="@title" %>
  </a>
<%@ end %>
```

이렇게 하면 Adobe Campaign은 문서 링크를 클릭한 것만 추적하는 것이 아니라 각 수신자가 클릭한 특정 문서를 추적할 수 있습니다.

## 모범 사례 {#best-practices}

* 동적 URL 매개 변수에 항상 `escapeUrl()` 함수 사용
* 컬렉션에서 개별 항목을 추적해야 할 때 `<%@ foreach %>` 사용
* 게재를 보내기 전에 추적을 테스트하여 모든 링크가 올바르게 작동하는지 확인합니다
* 개인화된 링크의 형식이 게재 콘텐츠에서 올바르게 지정되었는지 확인
* 추적 로그를 확인하여 개인화된 매개 변수가 올바르게 캡처되고 있는지 확인합니다

## 관련 항목 {#related-topics}

* [추적된 링크를 구성하는 방법 알아보기](tracked-links.md)
* [URL 추적 옵션을 구성하는 방법 알아보기](url-tracking.md)
* [개인화 필드를 추가하는 방법 알아보기](personalization-fields.md)

