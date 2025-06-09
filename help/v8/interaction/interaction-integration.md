---
product: campaign
title: 웹 페이지에 오퍼 추가
description: 웹 페이지에 오퍼를 추가하는 방법 알아보기
feature: Interaction, Offers
role: User, Admin
exl-id: 1eb0775a-5da9-4a27-aa7b-339372748f9c
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '1458'
ht-degree: 0%

---

# 웹 페이지에 오퍼 추가{#add-an-offer-in-web}

웹 페이지에서 오퍼 엔진을 호출하려면 JavaScript 코드에 대한 호출을 페이지에 직접 삽입합니다. 이 호출은 타깃팅된 요소에 오퍼 콘텐츠를 반환합니다.

URL을 호출하는 스크립트는 다음과 같습니다.

```
<script id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=" type="text/javascript"></script>
```

&quot;**env**&quot; 매개 변수는 익명 상호 작용 전용 라이브 환경의 내부 이름을 받습니다.

오퍼를 표시하려면 Adobe Campaign에서 환경과 오퍼 공간을 만든 다음 HTML 페이지를 구성해야 합니다.

다음 사용 사례에서는 JavaScript을 통해 오퍼를 통합할 수 있는 옵션을 자세히 설명합니다.

## 옵션 1: HTML 모드 {#html-mode}

### 익명 오퍼 제공 {#presenting-an-anonymous-offer}

**1단계: 오퍼 엔진 준비**

1. Adobe Campaign 인터페이스를 열고 익명 환경을 준비합니다.
1. 익명 환경에 연결된 오퍼 공간을 만듭니다.
1. 오퍼 및 오퍼 공간에 연결된 오퍼 표현을 만듭니다.

**2단계: HTML 페이지의 콘텐츠 업데이트**

HTML 페이지에는 만든 오퍼 공간(&quot;i_internal name space&quot;)의 내부 이름 값이 있는 @id 속성이 있는 요소가 포함되어야 합니다. 오퍼는 상호 작용에 의해 이 요소에 삽입됩니다.

이 예에서 @id 속성은 &quot;i_SPC12&quot; 값을 수신하며, 여기서 &quot;SPC12&quot;는 이전에 만든 오퍼 공간의 내부 이름입니다.

```
<div id="i_SPC12"></div>
```

이 예에서 스크립트를 호출하는 URL은 다음과 같습니다(&quot;OE3&quot;는 라이브 환경의 내부 이름입니다).

```
<script id="interactionProposalScript" src="https://instance.adobe.org:8080/nl/interactionProposal.js?env=OE3" type="text/javascript"></script>
```

>[!CAUTION]
>
>`<script>` 태그는 자동으로 닫으면 안 됩니다.

이 정적 호출은 오퍼 엔진에 필요한 모든 매개 변수를 포함하는 동적 호출을 자동으로 생성합니다.

이 비헤이비어를 사용하면 오퍼 엔진에 대한 단일 호출로 관리할 수 있도록 동일한 페이지에서 여러 오퍼 공간을 사용할 수 있습니다.

**3단계: HTML 페이지에 결과 표시**

오퍼 표시 콘텐츠는 오퍼 엔진에 의해 HTML 페이지로 반환됩니다.

```
<div id="banner_header">
 <div id="i_SPC12">
   <table>
    <tbody>
        <tr>
            <td><h3>Fly to Japan!</h3></td>
        </tr>
        <tr>
            <td><img width="150px" src="https://instance.adobe.org/res/Track/874fdaf72ddc256b2d8260bb8ec3a104.jpg"></td>
            <td>
            <p>Discover Japan for 2 weeks at an unbelievable price!!</p>
            <p><b>2345 Dollars - All inclusive</b></p>
        </td>
        </tr>
    </tbody>
    </table>
 </div>
<script src="https://instance.adobe.org:8080/nl/interactionProposal.js?env=OE3" id="interactionProposalScript" type="text/javascript"></script>
</div>
```

### 식별된 오퍼 제공 {#presenting-an-identified-offer}

식별된 연락처에 오퍼를 제공하기 위한 프로세스는 이 섹션](#presenting-an-anonymous-offer)의 자세한 [과(와) 유사합니다.

웹 페이지의 콘텐츠에서 오퍼 엔진 호출 중에 연락처를 식별하는 다음 스크립트를 추가해야 합니다.

```
<script type="text/javascript">
  interactionTarget = <contact_identifier>;
</script>
```

1. 웹 페이지에서 호출할 오퍼 공간으로 이동하여 **[!UICONTROL Advanced parameters]**&#x200B;을(를) 클릭하고 ID 키를 하나 이상 추가합니다.

   ![](assets/interaction_htmlmode_001.png)

   이 예제에서 식별 키는 이메일과 수신자 이름을 기반으로 하므로 합성 키입니다.

1. 웹 페이지가 표시되는 동안 스크립트 평가를 통해 수신자 ID를 오퍼 엔진에 전달할 수 있습니다. ID가 합성인 경우, 키는 고급 설정에 사용된 것과 동일한 순서로 표시되며, |.

   다음 예에서는 연락처가 웹 사이트에 로그온했으며 이메일 및 이름 덕분에 오퍼 엔진 호출 중에 인식되었습니다.

   ```
   <script type="text/javascript">
     interactionTarget = myEmail|myName;
   </script>
   ```

### HTML 렌더링 기능 사용 {#using-an-html-rendering-function}

HTML 오퍼 표현을 자동으로 생성하려면 렌더링 함수를 사용할 수 있습니다.

1. 오퍼 공간으로 이동하여 **[!UICONTROL Edit functions]** 링크를 클릭합니다.
1. **[!UICONTROL Overload the HTML rendering function]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL HTML rendering]** 탭으로 이동하여 오퍼 콘텐츠에 대해 정의된 필드와 일치하는 변수를 오퍼 공간에 삽입합니다.

   ![](assets/interaction_htmlmode_002.png)

   이 예제에서 오퍼는 웹 페이지에 배너 형태로 표시되며 클릭 가능한 이미지와 오퍼 콘텐츠에 정의된 필드와 일치하는 제목으로 구성됩니다.

## 옵션 2: XML 모드 {#xml-mode}

### 오퍼 제공 {#presenting-an-offer}

Campaign **상호 작용** 모듈을 사용하면 오퍼 엔진을 호출하는 HTML 페이지에 XML 노드를 반환할 수 있습니다. 이 XML 노드는 고객 측에서 개발해야 하는 함수에 의해 처리될 수 있습니다.

오퍼 엔진에 대한 호출은 다음과 같습니다.

```
<script type="text/javascript" id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=&cb="></script>
```

* &quot;**env**&quot; 매개 변수는 라이브 환경의 내부 이름을 받습니다.

* &quot;**cb**&quot; 매개 변수는 (콜백) 제안을 포함하는 엔진에서 반환된 XML 노드를 읽을 함수의 이름을 받습니다. 이 매개 변수는 선택 사항입니다.

* &quot;**t**&quot; 매개 변수는 식별된 상호 작용에 대해서만 대상 값을 받습니다. 이 매개 변수는 **interactionTarget** 변수와 함께 전달할 수도 있습니다. 이 매개 변수는 선택 사항입니다.

* &quot;**c**&quot; 매개 변수는 범주의 내부 이름 목록을 받습니다. 이 매개 변수는 선택 사항입니다.

* &quot;**th**&quot; 매개 변수는 테마 목록을 받습니다. 이 매개 변수는 선택 사항입니다.

* &quot;**gctx**&quot; 매개 변수는 전체 페이지에 대한 호출 데이터 전역(컨텍스트)을 수신합니다. 이 매개 변수는 선택 사항입니다.

반환된 XML 노드는 다음과 같습니다.

```
<propositions>
 <proposition id="" offer-id="" weight="" rank="" space="" div=""> //proposition identifiers
   ...XML content defined in Adobe Campaign...
 </proposition>
 ...
</propositions>
```

아래 사용 사례에서는 XML 모드를 활성화하기 위해 Adobe Campaign에서 수행하는 구성에 대해 자세히 설명한 후 HTML 페이지에 엔진 호출 결과를 표시합니다.

1. **환경 및 오퍼 공간 만들기**

   환경 만들기에 대한 자세한 내용은 [이 페이지](interaction-env.md)를 참조하세요.

   오퍼 공간을 만드는 방법에 대한 자세한 내용은 [이 페이지](interaction-offer-spaces.md)를 참조하세요.

1. **오퍼 스키마를 확장하여 새 필드 추가**

   이 스키마는 제목 번호 2 및 가격 필드를 정의합니다.

   예제의 스키마 이름은 **cus:offer**&#x200B;입니다.

   ```
   <srcSchema _cs="Marketing offers (cus)" created="2013-01-18 17:14:20.762Z" createdBy-id="0"
              desc="" entitySchema="xtk:srcSchema" extendedSchema="nms:offer" img="nms:offer.png"
              label="Marketing offers" labelSingular="Marketing offers" lastModified="2013-01-18 15:20:18.373Z"
              mappingType="sql" md5="F14A7AA009AE1FCE31B0611E72866AC3" modifiedBy-id="0"
              name="offer" namespace="cus" xtkschema="xtk:srcSchema">
     <createdBy _cs="Administrator (admin)"/>
     <modifiedBy _cs="Administrator (admin)"/>
     <element img="nms:offer.png" label="Marketing offers" labelSingular="Marketing offer"
              name="offer">
       <element label="Content" name="view">
         <element label="Price" name="price" type="long" xml="true"/>
         <element label="Title 2" name="title2" type="string" xml="true"/>
   
         <element advanced="true" desc="Price calculation script." label="Script price"
                  name="price_jst" type="CDATA" xml="true"/>
         <element advanced="true" desc="Title calculation script." label="Script title"
                  name="title2_jst" type="CDATA" xml="true"/>
       </element>
     </element>
   </srcSchema>
   ```

   >[!CAUTION]
   >
   >각 요소를 두 번 정의해야 합니다. CDATA(&quot;_jst&quot;) 유형 요소에는 개인화 필드가 포함될 수 있습니다.
   >
   >데이터베이스 구조를 업데이트하는 것을 잊지 마십시오.

   오퍼 스키마를 확장하여 배치 및 단일 모드와 모든 형식(텍스트, HTML 및 XML)의 새 필드를 추가할 수 있습니다.

1. **오퍼 수식을 확장하여 새 필드를 편집하고 기존 필드를 수정합니다**

   **오퍼(nsm)** 입력 양식을 편집합니다.

   &quot;보기&quot; 섹션에 다음 콘텐츠가 있는 두 개의 새 필드를 삽입합니다.

   ```
   <input label="Title 2" margin-right="5" prebuildSubForm="false" type="subFormLink" xpath="title2_jst">
        <form label="Edit title 2" name="editForm" nothingToSave="true">
            <input nolabel="true" toolbarAlign="horizontal" type="jstEdit" xpath="." xpathInsert="/ignored/customizeTitle2">
            <container>
                <input menuId="viewMenuBuilder" options="inbound" type="customizeBtn" xpath="/ignored/customizeTitle2"/>
            </container>
            </input>
        </form>
    </input>
    <input nolabel="true" type="edit" xpath="title2_jst"/>
    <input label="Price" margin-right="5" prebuildSubForm="false" type="subFormLink" xpath="price_jst">
        <form label="Edit price" name="editForm" nothingToSave="true">
        <input nolabel="true" toolbarAlign="horizontal" type="jstEdit" xpath="." xpathInsert="/ignored/customizePrice">
            <container>
                <input menuId="viewMenuBuilder" options="inbound" type="customizeBtn" xpath="/ignored/customizePrice"/>
            </container>
        </input>
        </form>
    </input>
    <input colspan="2" label="Prix" nolabel="true" type="number" xpath="price_jst"/>
   ```

   대상 URL 필드를 주석 처리합니다.

   ![](assets/interaction_xmlmode_form_001.png)

   >[!CAUTION]
   >
   >( `<input>`) 양식의 필드는 만들어진 스키마에 정의된 CDATA 형식 요소를 가리켜야 합니다.

   오퍼 표시 양식의 렌더링은 다음과 같습니다.

   ![](assets/interaction_xmlmode_form.png)

   **[!UICONTROL Title 2]** 및 **[!UICONTROL Price]** 필드가 추가되었으며 **[!UICONTROL Destination URL]** 필드가 더 이상 표시되지 않습니다.

1. **오퍼 만들기**

   오퍼 만들기에 대한 자세한 내용은 [이 페이지](interaction-offer.md)를 참조하세요.

   다음 사용 사례에서는 오퍼를 다음과 같이 입력합니다.

   ![](assets/interaction_xmlmode_offer.png)

1. **오퍼 승인**

   오퍼를 승인하거나 다른 사람이 승인하도록 한 다음, 연결된 라이브 환경에서 사용할 수 있도록 마지막 단계에서 만든 오퍼 공간에서 활성화합니다.

1. **HTML 페이지의 엔진 호출 및 결과**

   HTML 페이지의 오퍼 엔진에 대한 호출은 다음과 같습니다.

   ```
   <script id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=OE7&cb=alert" type="text/javascript">
   ```

   &quot;**env**&quot; 매개 변수의 값은 라이브 환경의 내부 이름입니다.

   &quot;**cb**&quot; 매개 변수의 값은 엔진에서 반환된 XML 노드를 해석해야 하는 함수의 이름입니다. 이 예에서 호출된 up 함수는 모달 창(alert() 함수)을 엽니다.

   오퍼 엔진에서 반환된 XML 노드는 다음과 같습니다.

   ```
   <propositions>
    <proposition id="a28002" offer-id="10322005" weight="1" rank="1" space="SPC14" div="i_SPC14">
     <xmlOfferView>
      <title>Travel to Russia</title>
      <price>3456</price>
      <description>Discover this vacation package!INCLUDES 10 nights. FEATURES buffet breakfast daily. BONUS 5th night free.</description>
      <image>
       <path>https://myinstance.com/res/Track/ae1d2113ed732d58a3beb441084e5960.jpg</path>
       <alt>Travel to Russia</alt>
      </image>
     </xmlOfferView>
    </proposition>
   </propositions>
   ```

### 렌더링 함수 사용 {#using-a-rendering-function-}

XML 렌더링 함수를 사용하여 오퍼 프레젠테이션을 만들 수 있습니다. 이 함수는 오퍼 엔진을 호출하는 동안 HTML 페이지로 반환되는 XML 노드를 수정합니다.

1. 오퍼 공간으로 이동하여 **[!UICONTROL Edit functions]** 링크를 클릭합니다.
1. **[!UICONTROL Overload the XML rendering function]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL XML rendering]** 탭으로 이동하여 원하는 함수를 삽입합니다.

   함수는 다음과 같이 표시될 수 있습니다.

   ```
   function (proposition) {
     delete proposition.@id;
     proposition.@newAttribute = "newValue";
   } 
   ```

![](assets/interaction_xmlmode_001.png)

## SOAP 통합 설정

오퍼 관리에 제공되는 SOAP 웹 서비스는 Adobe Campaign에서 일반적으로 사용되는 서비스와 다릅니다. 이전 섹션에 설명된 상호 작용 URL을 통해 액세스할 수 있으며, 지정된 연락처에 대한 오퍼를 제시하거나 업데이트할 수 있습니다.

### 오퍼 제안 {#offer-proposition}

SOAP을 통한 오퍼 제안에 대해 **nms:proposition#Propose** 명령과 다음 매개 변수를 추가합니다.

* **targetId**: 받는 사람의 기본 키(복합 키일 수 있음).
* **maxCount**: 연락처의 오퍼 제안 수를 지정합니다.
* **컨텍스트**: 스페이스 스키마에 컨텍스트 정보를 추가할 수 있습니다. 사용된 스키마가 **nms:interaction**&#x200B;인 경우 **`<empty>`**&#x200B;을(를) 추가해야 합니다.
* **categories**: 오퍼가 속해야 하는 범주/IE를 지정합니다.
* **테마**: 오퍼가 속해야 하는 테마를 지정합니다.
* **uuid**: Adobe Campaign 영구 쿠키의 값(&quot;uuid230&quot;).
* **nli**: Adobe Campaign 세션 쿠키의 값(&quot;nlid&quot;)입니다.
* **noProp**: &quot;true&quot; 값을 사용하여 제안 삽입을 비활성화합니다.

>[!NOTE]
>
>**targetId** 및 **maxCount** 설정은 필수입니다. 다른 것들은 선택 사항입니다.

쿼리에 대해 SOAP 서비스는 다음 매개 변수를 반환합니다.

* **interactionId**: 인터랙션의 ID입니다.
* **제안**: XML 요소에는 각각 고유한 ID와 HTML 표현이 있는 제안 목록이 포함되어 있습니다.

### 오퍼 업데이트 {#offer-update}

**nms:interaction#UpdateStatus** 명령을 URL에 추가한 다음 다음 매개 변수를 추가합니다.

* **제안**: 문자열로, 오퍼 제안 중 출력으로 제공된 제안 ID가 포함되어 있습니다. [오퍼 제안](#offer-proposition)을 참조하세요.
* **상태**: 문자열 형식이며 오퍼의 새 상태를 지정합니다. 가능한 값은 **nms:common** 스키마의 **propositionStatus** 열거형에 나열됩니다. 예를 들어, 기본적으로 숫자 3은 **수락됨** 상태에 해당합니다.
* **context**: XML 요소를 사용하면 공간 스키마에 컨텍스트 정보를 추가할 수 있습니다. 사용된 스키마가 **nms:interaction**&#x200B;인 경우 **`<empty>`**&#x200B;을(를) 추가해야 합니다.

### SOAP 호출 사용 예 {#example-using-a-soap-call}

다음은 SOAP 호출에 대한 코드의 예입니다.

```
<%
  var space = request.parameters.sp
  var cnx = new HttpSoapConnection(
    "https://" + request.serverName + ":" + request.serverPort + "/interaction/" + env + "/" + space,
    "utf-8",
    HttpSoapConnection.SOAP_12)
  var session = new SoapService(cnx, "nms:interaction")
  var action = request.parameters.a
  if( action == undefined )
    action = 'propose'

  try
  {
    switch( action )
    {
    case "update":
      var proposition = request.parameters.p
      var status      = request.parameters.st
      session.addMethod("UpdateStatus", "nms:interaction#UpdateStatus",
       ["proposition", "string",
        "status",      "string",
        "context",     "NLElement"],
       [])
      session.UpdateStatus(proposition, status, <undef/>)
      var redirect = request.parameters.r
      if( redirect != undefined )
        response.sendRedirect(redirect)
      break;

    case "propose":
      var count = request.parameters.n
      var target = request.parameters.t
      var categorie = request.parameters.c
      var theme = request.parameters.th
      var layout = request.parameters.l
      if( count == undefined )
        count = 1
      session.addMethod("Propose", "nms:proposition#Propose",
       ["targetId",      "string",
        "maxCount",      "string",
         "categories",    "string",
         "themes",        "string",
        "context",       "NLElement"],
       ["interactionId", "string",
        "propositions",  "NLElement"])
      response.setContentType("text/html")
      var result = session.Propose(target, count, category, theme, <empty/>)
      var props = result[1]
  %><table><tr><%
      for each( var propHtml in props.proposition.*.mdSource )
      {
        %><td><%=propHtml%></td><%
      }
  %></tr></table><%
      break;
    }
  }
  catch( e )
  {
  }
  %>
```
