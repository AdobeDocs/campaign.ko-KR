---
product: campaign
title: 개인화된 PDF 문서 생성
description: 개인화된 PDF 문서를 생성하는 방법 알아보기
feature: Personalization
role: User
version: Campaign v8, Campaign Classic v7
source-git-commit: 25ee55d5327e0ba7f2192f7b462853269c8cbf46
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 1%

---

# 개인화된 PDF 문서 생성{#generating-personalized-pdf-documents}

## 변수 PDF 문서 정보 {#about-variable-pdf-documents}

Adobe Campaign을 사용하면 LibreOffice 또는 Microsoft Word 문서의 이메일 첨부 파일에 대한 변수 PDF 문서를 생성할 수 있습니다.

지원되는 확장은 &quot;.docx&quot;, &quot;.doc&quot; 및 &quot;.odt&quot;입니다.

문서를 개인화하기 위해 이메일 개인화와 동일한 JavaScript 기능을 사용할 수 있습니다.

**[!UICONTROL "The content of the file is personalized and converted to PDF during the delivery of each message"]** 옵션을 활성화합니다. 이 옵션은 게재 이메일에 파일을 첨부할 때 액세스할 수 있습니다. 계산된 파일을 첨부하는 방법에 대한 자세한 내용은 [Campaign v8 설명서](attaching-files.md)를 참조하세요.

동적 표를 생성하거나 URL을 통해 이미지를 포함하려면 특정 프로세스를 따라야 합니다.

## 동적 테이블 생성 {#generating-dynamic-tables}

동적 테이블을 생성하는 절차는 다음과 같습니다.

* 세 개의 행과 필요한 수만큼 열을 사용하여 표를 만든 다음 해당 레이아웃(테두리 등)을 구성합니다.
* 테이블에 커서를 놓고 **[!UICONTROL Table > Table properties]** 메뉴를 클릭합니다. **[!UICONTROL Table]** 탭으로 이동하여 **NlJsTable**(으)로 시작하는 이름을 입력합니다.
* 첫 번째 줄의 첫 번째 셀에서 표에 표시할 값에 대해 반복을 활성화하는 루프(&quot;for&quot;)를 정의합니다.
* 표의 두 번째 행에 있는 각 셀에 표시할 값을 반환하는 스크립트를 삽입합니다.
* 표의 세 번째 줄과 마지막 줄에 있는 고리를 닫습니다.

## 외부 이미지 삽입 {#inserting-external-images}

외부 이미지 삽입은 예를 들어 수신자의 필드에 URL을 입력하는 이미지로 문서를 개인화하려는 경우에 유용합니다.

이렇게 하려면 개인화 블록을 구성한 다음 첨부 파일에 개인화 블록에 대한 호출을 포함해야 합니다.

**예: 받는 사람의 국가에 따라 개인 맞춤화된 로고 삽입**

**1단계: 첨부 파일 만들기:**

* 개인화 블록에 대한 호출을 삽입합니다. **&lt;%@ include view=&quot;blockname&quot; %>**.
* 개인화된 콘텐츠를 파일 본문에 삽입합니다.

**2단계: 개인화 블록 만들기:**

* Adobe Campaign 콘솔의 **[!UICONTROL Resources > Campaign management > Personalization blocks]** 메뉴로 이동합니다.
* &quot;My_Logo&quot;를 내부 이름으로 사용하여 새 &quot;내 로고&quot; 개인화 블록을 만듭니다.
* **[!UICONTROL Advanced parameters...]** 링크를 클릭한 다음 **[!UICONTROL "The content of the block is included in an attachment"]** 옵션을 선택합니다. 이렇게 하면 개인화 블록의 정의를 OpenOffice 파일의 콘텐츠에 직접 복사할 수 있습니다.

  ![](assets/s_ncs_pdf_bloc_option.png)

  개인화 블록 내에서 두 가지 유형의 선언을 구별해야 합니다.

   * &quot;열기&quot; 및 &quot;닫힘&quot; V자형 화살표가 이스케이프 문자로 바뀌어야 하는 개인화 필드의 Adobe Campaign 코드(각각 `&lt;` 및 `&gt;`)입니다.
   * 전체 OpenOffice XML 코드는 OpenOffice 문서에 복사됩니다.

이 예에서 개인화 블록은 다음과 같습니다.

```
<% if (recipient.country.label == "Germany") { %>
<draw:frame svg:width="4cm" svg:height="3cm">
<draw:image xlink:href=https://..../logo_germany.png />
</draw:frame>
<% } else
if (recipient.country.label == "USA")
{ %>
<draw:frame svg:width="4cm" svg:height="3cm">
<draw:image xlink:href=https://..../logo_USA.png />
</draw:frame>
<% } %>
```

수신자의 국가에 따라 게재에 연결된 문서에 개인화가 표시됩니다.
