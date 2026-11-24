---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 3%
---
# generateTrackingTag

웹 추적을 위해 JavaScript 태그를 자동으로 생성합니다.

```text
generateTrackingTag (request [, tagid ] [, folder ])
```

## 매개변수

**요청** HttpServletRequest 개체

**tagid** 개인화된 tagid의 이름을 나타내는 문자 문자열입니다. 비어 있는 경우 함수는 경로 이름을 기반으로 태그를 생성합니다.

**폴더** 폴더의 내부 이름을 나타내는 문자열. 비어 있는 경우 태그는 기본 디렉토리(예: &quot;웹 추적 태그&quot;)에 생성됩니다.

## 반환 값

포함할 JavaScript 코드가 포함된 문자 문자열입니다.

## 비고

생성된 태그는 웹 앱, html 페이지, 컨트롤러 또는 일반적으로 말해서 태그 ID가 입력되지 않은 경우 경로 이름을 기반으로 합니다. 마지막 매개 변수는 태그 대상 폴더를 지정합니다. 함수를 호출하려면 요청 개체를 인수로 전달합니다. 함수가 html 코드를 생성하므로 &lt;%==을(를) 사용하십시오. 예:

```xml
              <%== generateTrackingTag(request, request.getParameter('art'), request.getParameter('cat')) %>
```

## 기능

**다음 위치에서 사용 가능:**

* JSSP
* 웹 앱
