---
title: 캠페인 입력 양식
description: 입력 양식을 사용자 지정하는 방법 알아보기
feature: Web Forms
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 62908bba-9cfa-42b6-b463-b601496d535b
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '2552'
ht-degree: 0%

---

# 입력 양식 시작{#gs-ac-forms}

스키마를 만들거나 확장할 때 최종 사용자가 볼 수 있도록 관련 입력 양식을 작성하거나 수정해야 합니다.

입력 양식을 사용하면 Adobe Campaign 클라이언트 콘솔에서 데이터 스키마와 연결된 인스턴스를 편집할 수 있습니다. 양식은 해당 이름 및 네임스페이스로 식별됩니다.

양식의 ID 키는 네임스페이스와 콜론으로 구분되는 이름으로 구성된 문자열입니다. 예: &quot;cus:contact&quot;

## 입력 양식 편집

에서 입력 양식 만들기 및 구성 **[!UICONTROL Administration]> [!UICONTROL Configuration] >[!UICONTROL Input forms]** 클라이언트 콘솔의 폴더:

![](assets/form_arbo.png)

편집 영역에서 입력 양식의 XML 내용을 입력할 수 있습니다.

![](assets/form_edit.png)

미리 보기는 입력 양식의 표시를 생성합니다.

![](assets/form_preview.png)

## 양식 구조

양식에 대한 설명은 양식 스키마의 문법을 준수하는 구조화된 XML 문서입니다 **xtk:form**.

입력 양식의 XML 문서에는 `<form>` 루트 요소가 있는 요소  **이름** 및  **namespace** 양식 이름과 네임스페이스를 채울 속성입니다.

```
<form name="form_name" namespace="name_space">
...
</form>
```

기본적으로 양식은 이름 및 네임스페이스가 동일한 데이터 스키마와 연결됩니다. 다른 이름과 양식을 연결하려면 **entity-schema** 의 속성 `<form>` 요소를 스키마 키의 이름으로 지정합니다. 입력 양식의 구조를 보여주기 위해 &quot;cus:recipient&quot; 예제 스키마를 사용하여 인터페이스를 설명하겠습니다.

```
<srcSchema name="recipient" namespace="cus">
  <enumeration name="gender" basetype="byte">    
    <value name="unknown" label="Not specified" value="0"/>    
    <value name="male" label="Male" value="1"/>   
    <value name="female" label="Female" value="2"/>   
  </enumeration>

  <element name="recipient">
    <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
    <attribute name="birthDate" type="datetime" label="Date"/>
    <attribute name="gender" type="byte" label="Gender" enum="gender"/>
  </element>
</srcSchema>
```

예제 스키마를 기반으로 하는 입력 양식:

![](assets/do-not-localize/form_exemple1.png)

```
<form name="recipient" namespace="cus">
  <input xpath="@gender"/>
  <input xpath="@birthDate"/>
  <input xpath="@email"/>
</form>
```

편집 컨트롤의 설명은 `<form>` 루트 요소. 편집 컨트롤이 **`<input>`** 요소가 있는 요소 **xpath** 스키마에 필드의 경로를 포함하는 속성입니다.

편집 컨트롤은 해당 데이터 형식에 자동으로 적응하고 스키마에 정의된 레이블을 사용합니다.

>[!NOTE]
>
>를 추가하여 데이터 스키마에 정의된 레이블을 덮어쓸 수 있습니다 **레이블** 속성을 `<input>` 요소:\
>`<input label="E-mail address" xpath="@name" />`

기본적으로 각 필드는 단일 행에 표시되며 데이터 유형에 따라 사용 가능한 모든 공간을 차지합니다.

![](../assets/do-not-localize/book.png) 모든 양식 속성은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/developer/campaign-api/api/control-Button.html){target="_blank"}.

## 양식화 {#formatting}

컨트롤의 레이아웃은 HTML 테이블에 사용되는 레이아웃과 비슷하며 컨트롤을 여러 열로 분할하거나 요소를 삽입하거나 사용 가능한 공간의 위치를 지정할 수 있습니다. 그러나 이 서식을 지정하면 해당 영역을 비율로 나눌 수 있습니다. 개체에 고정 치수를 지정할 수 없습니다.

위의 예제 컨트롤을 두 열로 표시하려면 다음을 수행합니다.

![](assets/do-not-localize/form_exemple2.png)

```
<form name="recipient" namespace="cus">
  <container colcount="2">
    <input xpath="@gender"/>
    <input xpath="@birthDate"/>
    <input xpath="@email"/>
  </container>
</form>
```

다음 **`<container>`** 요소가 있는 요소 **colcount** 특성을 사용하면 자식 컨트롤을 두 개의 열에 강제 표시할 수 있습니다.

다음 **colspan** 컨트롤의 특성은 값에 입력한 열 수로 컨트롤을 확장합니다.

![](assets/do-not-localize/form_exemple3.png)

```
<form name="recipient" namespace="cus">
  <container colcount="2">
    <input xpath="@gender"/>
    <input xpath="@birthDate"/>
    <input xpath="@email" colspan="2"/>
  </container>
</form> 
```

다음 **type=&quot;frame&quot;** 이 속성을 사용하면 컨테이너는 자식 컨트롤 주위에 해당 레이블이 포함된 프레임을 추가합니다 **레이블** attribute:

![](assets/do-not-localize/form_exemple4.png)

```
<form name="recipient" namespace="cus">
  <container colcount="2" type="frame" label="General">
    <input xpath="@gender"/>
    <input xpath="@birthDate"/>
    <input xpath="@email" colspan="2"/>
  </container>
</form>
```

A **`<static>`** 요소를 사용하여 입력 양식 서식을 지정할 수 있습니다.

![](assets/do-not-localize/form_exemple5.png)

```
<form name="recipient" namespace="cus">
  <static type="separator" colspan="2" label="General"/>
  <input xpath="@gender"/>
  <input xpath="@birthDate"/>
  <input xpath="@email" colspan="2"/>
  <static type="help" label="General information about recipient with date of birth, gender, and e-mail address." colspan="2"/>
</form>
```

다음 **`<static>`** 태그와 함께 **구분 기호** type을 사용하면 **레이블** 속성을 사용합니다.

도움말 텍스트를 `<static>` 태그 내에 도움말 유형을 지정합니다. 텍스트 내용은 **레이블** 속성을 사용합니다.

## 컨테이너 사용 {#containers}

사용 **컨테이너** 컨트롤 집합을 그룹화하는 데 사용됩니다. 이 변수들은 **`<container>`** 요소를 생성하지 않습니다. 위의 여러 열에 대한 컨트롤 서식을 지정하는 데 사용됩니다.

다음 **xpath** 속성 `<container>` 자식 컨트롤 참조를 단순화할 수 있습니다. 그러면 컨트롤 참조가 상위에 상대적입니다 `<container>` 상위

xpath가 없는 컨테이너의 예:

```
<container colcount="2">
  <input xpath="location/@zipCode"/>
  <input xpath="location/@city"/>
</container>
```

예를 들어 &quot;location&quot;이라는 요소에 &quot;xpath&quot;를 추가하면 됩니다.

```
<container colcount="2" xpath="location">
  <input xpath="@zipCode"/>
  <input xpath="@city"/>
</container>
```

컨테이너는 페이지에서 형식이 지정된 필드 집합을 사용하여 복잡한 컨트롤을 구성하는 데 사용됩니다.

### 탭 추가(노트북) {#tab-container}

다음 작업 **노트북** 컨테이너 를 사용하여 탭에서 액세스할 수 있는 페이지의 데이터 형식을 지정합니다.

![](assets/do-not-localize/form_exemple6.png)

```
<container type="notebook">
  <container colcount="2" label="General">
    <input xpath="@gender"/>
    <input xpath="@birthDate"/>
    <input xpath="@email" colspan="2"/>
  </container>
  <container colcount="2" label="Location">
    ...
  </container>
</container>
```

기본 컨테이너는 **type=&quot;notebook&quot;** 속성을 사용합니다. 탭은 하위 컨테이너에서 선언되며 탭의 레이블은 **레이블** 속성을 사용합니다.

추가 **style=&quot;down&quot;** 속성 을 사용하여 컨트롤 아래에 탭 레이블의 세로 위치를 지정합니다. 이 속성은 선택 사항입니다. 기본값은 입니다. **&quot;up&quot;**.

![](assets/do-not-localize/form_exemple7.png)

`<container style="down" type="notebook">  ... </container>`

### 아이콘 추가(iconbox) {#icon-list}

이 컨테이너를 사용하여 표시할 페이지를 선택할 수 있는 세로 아이콘 막대를 표시합니다.

![](assets/do-not-localize/form_exemple8.png)

```
<container type="iconbox">
  <container colcount="2" label="General" img="xtk:properties.png">
    <input xpath="@gender"/>
    <input xpath="@birthDate"/>
    <input xpath="@email" colspan="2"/>
  </container>
  <container colcount="2" label="Location" img="nms:msgfolder.png">
    ...
  </container>
</container>
```

기본 컨테이너는 **type=&quot;iconbox&quot;** 속성을 사용합니다. 아이콘과 연관된 페이지는 하위 컨테이너에서 선언됩니다. 아이콘의 레이블은 **레이블** 속성을 사용합니다.

페이지의 아이콘은 `img="<image>"` 속성, 위치 `<image>` 은 이름 및 네임스페이스로 구성된 키에 해당하는 이미지 이름입니다(예: &quot;xtk:properties.png&quot;).

이미지는 **[!UICONTROL Administration > Configuration > Images]** 노드 아래에 있어야 합니다.

### 컨테이너 숨기기(visibleGroup) {#visibility-container}

동적 조건을 통해 컨트롤 집합을 숨길 수 있습니다.

다음 예에서는 &quot;Gender&quot; 필드 값에 대한 컨트롤의 가시성을 보여줍니다.

```
<container type="visibleGroup" visibleIf="@gender=1">
  ...
</container>
<container type="visibleGroup" visibleIf="@gender=2">
  ...
</container>
```

가시성 컨테이너는 속성에 의해 정의됩니다 **type=&quot;visibleGroup&quot;**. 다음 **visibleIf** 속성에는 가시성 조건이 포함됩니다.

조건 구문의 예:

* **visibleIf=&quot;@email=&#39;peter.martinezATneolane.net&#39;&quot;**: 문자열 유형 데이터에 대해 같음 테스트를 수행합니다. 비교 값은 따옴표로 묶어야 합니다.
* **visibleIf=&quot;@gender >= 1 및 @gender!= 2&quot;**: 숫자 값에 대한 조건.
* **visibleIf=&quot;@boolean1=true 또는 @boolean2=false&quot;**: 부울 필드에서 테스트합니다.

### 조건부 표시(enabledGroup) {#enabling-container}

이 컨테이너를 사용하여 동적 조건에서 데이터 세트를 활성화하거나 비활성화할 수 있습니다. 컨트롤을 비활성화하면 컨트롤이 편집되지 않습니다. 다음 예제에서는 &quot;Gender&quot; 필드의 값에서 컨트롤을 활성화하는 방법을 보여 줍니다.

```
<container type="enabledGroup" enabledIf="@gender=1">
  ...
</container>
<container type="enabledGroup" enabledIf="@gender=2">
  ...
</container>
```

사용 가능한 컨테이너는 **type=&quot;enabledGroup&quot;** 속성을 사용합니다. 다음 **enabledIf** 속성에는 활성화 조건이 포함되어 있습니다.

## 링크 편집 {#editing-a-link}

링크는 데이터 스키마에 다음과 같이 선언됩니다.

```
<element label="Company" name="company" target="cus:company" type="link"/>
```

입력 양식의 링크 편집 컨트롤은 다음과 같습니다.

![](assets/do-not-localize/form_exemple9.png)

```
<input xpath="company"/>
```

편집 필드를 통해 Target 선택에 액세스할 수 있습니다. 입력한 처음 몇 문자에서 대상 요소를 쉽게 찾을 수 있도록 시작 유형이 지원됩니다. 그러면 검색이 **계산 문자열** 대상 스키마에 정의되어 있습니다. 컨트롤에 유효성 검사 후 스키마가 없으면 즉시 대상 만들기에 대한 확인 메시지가 표시됩니다. 확인은 대상 테이블에 새 레코드를 만들어 링크와 연결합니다.

드롭다운 목록은 이미 생성된 레코드 목록에서 대상 요소를 선택하는 데 사용됩니다.

다음 **[!UICONTROL Modify the link]** (폴더) 아이콘은 타깃팅된 요소 목록과 필터 영역을 사용하여 선택 양식을 시작합니다.

다음 **[!UICONTROL Edit link]** (돋보기) 아이콘이 연결된 요소의 편집 양식을 시작합니다. 사용되는 양식은 기본적으로 타깃팅된 스키마의 키에 따라 추론됩니다. 다음 **양식** 속성을 사용하면 편집 양식의 이름(예: &quot;cus:company2&quot;)

을 추가하여 대상 요소의 선택을 제한할 수 있습니다 **`<sysfilter>`** 입력 양식의 링크 정의에 있는 요소:

```
<input xpath="company">
  <sysFilter>
    <condition expr="[location/@city] =  'Newton"/>
  </sysFilter>
</input>
```

목록을 **`<orderby>`** 요소:

```
<input xpath="company">
  <orderBy>
    <node expr="[location/@zipCode]"/>
  </orderBy>
</input>
```

## 컨트롤 속성 {#control-properties}

* **noAutoComplete**: 자동 완성 사용 안 함(값 &quot;true&quot; 사용)
* **createMode**: 링크가 없는 경우 즉시 링크를 만듭니다. 가능한 값은 다음과 같습니다.

   * **없음**: 생성을 비활성화합니다. 링크가 없으면 오류 메시지가 표시됩니다
   * **인라인**: 편집 필드에 컨텐츠가 있는 링크를 만듭니다.
   * **에디션**: 링크에 편집 양식을 표시합니다. 양식의 유효성이 확인되면 데이터가 저장됩니다(기본 모드)

* **noZoom**: 링크에 양식 편집 없음(값 &quot;true&quot; 사용)
* **양식**: 타깃팅된 요소의 편집 양식을 오버로드함

## 링크(바인딩되지 않음) 목록 추가 {#list-of-links}

데이터 스키마에 컬렉션 요소로 입력한 링크(unbound=&quot;true&quot;)는 연결된 모든 요소를 보려면 목록을 통과해야 합니다.

원칙은 최적화된 데이터 로딩이 있는 연결된 요소 목록을 표시하는 것입니다(데이터 배치로 다운로드, 표시되는 경우에만 목록 실행).

스키마에 있는 컬렉션 링크의 예:

```
<element label="Events" name="rcpEvent" target="cus:event" type="link" unbound="true">
...
</element>
```

입력 양식의 목록:

```
 <input xpath="rcpEvent" type="linklist">
  <input xpath="@label"/>
  <input xpath="@date"/>
</input>
```

목록 컨트롤은 **type=&quot;linklist&quot;** 속성을 사용합니다. 목록 경로는 수집 링크를 참조해야 합니다.

열은 를 통해 선언됩니다 **`<input>`** 목록의 요소입니다. 다음 **xpath** 속성은 대상 스키마에 있는 필드의 경로를 나타냅니다.

스키마 링크에 정의된 레이블이 있는 도구 모음이 자동으로 목록 위에 배치됩니다.

목록은 **[!UICONTROL Filters]** 열을 추가 및 정렬하도록 단추 및 구성되었습니다.

다음 **[!UICONTROL Add]** 및 **[!UICONTROL Delete]** 버튼을 사용하면 링크에서 수집 요소를 추가하고 삭제할 수 있습니다. 기본적으로 요소를 추가하면 대상 스키마의 편집 양식이 실행됩니다.

다음 **[!UICONTROL Detail]** 버튼이 자동으로 추가됨 **zoom=&quot;true&quot;** 속성은 다음에서 완료됩니다 **`<input>`** 태그에 다음 코드를 배치하십시오. 선택한 라인의 편집 양식을 시작할 수 있습니다.

목록을 로드하는 동안 필터링 및 정렬을 적용할 수 있습니다.

```
 <input xpath="rcpEvent" type="linklist">
  <input xpath="@label"/>
  <input xpath="@date"/>
  <sysFilter>
    <condition expr="@type = 1"/>
  </sysFilter>
  <orderBy>
    <node expr="@date" sortDesc="true"/>
  </orderBy>
</input>
```

## 관계 테이블 정의 {#relationship-table}

관계 테이블을 사용하면 두 테이블을 N-N 카디널리티에 연결할 수 있습니다. 관계 테이블에는 두 테이블에 대한 링크만 포함됩니다.

따라서 목록에 요소를 추가하면 관계 테이블의 두 링크 중 하나에서 목록을 완료할 수 있습니다.

스키마에 있는 관계 테이블의 예:

```
<srcSchema name="subscription" namespace="cus">
  <element name="recipient" type="link" target="cus:recipient" label="Recipient"/>
  <element name="service" type="link" target="cus:service" label="Subscription service"/>
</srcSchema>
```

이 예제에서는 &quot;cus:recipient&quot; 스키마의 입력 양식으로 시작합니다. 이 목록에는 서비스 구독과 연결된 연결이 표시되어야 하며 기존 서비스를 선택하여 구독을 추가할 수 있어야 합니다.

![](assets/do-not-localize/form_exemple12.png)

```
<input type="linklist" xpath="subscription" xpathChoiceTarget="service" xpathEditTarget="service" zoom="true">
  <input xpath="recipient"/>
  <input xpath="service"/>
</input>
```

다음 **xpathChoiceTarget** 속성을 사용하면 입력한 링크에서 선택 양식을 시작할 수 있습니다. 관계 테이블 레코드를 만들면 현재 받는 사람 및 선택한 서비스에 대한 링크가 자동으로 업데이트됩니다.

>[!NOTE]
>
>다음 **xpathEditTarget** 속성을 사용하면 입력한 링크에 대해 선택한 라인을 강제로 편집할 수 있습니다.

### 목록 속성 {#list-properties}

* **noToolbar**: 도구 모음을 숨깁니다(값 &quot;true&quot;가 있는 경우).
* **toolbarCaption**: 도구 모음 레이블 오버로드
* **toolbarAlign**: 도구 모음의 세로 또는 가로 형상을 수정합니다(가능한 값: &quot;vertical&quot;|&quot;horizontal&quot;)
* **img**: 목록에 연결된 이미지를 표시합니다
* **양식**: 타깃팅된 요소의 편집 양식을 오버로드함
* **확대/축소**: 추가 **[!UICONTROL Zoom]** 타깃팅된 요소를 편집하는 단추
* **xpathEditTarget**: 입력한 링크에 대한 편집 설정
* **xpathChoiceTarget**: 또한 입력한 링크에서 선택 양식을 시작합니다

## 메모리 목록 컨트롤 추가 {#memory-list-controls}

메모리 목록을 사용하면 목록 데이터 미리 로드를 사용하여 수집 요소를 편집할 수 있습니다. 이 목록은 필터링하거나 구성할 수 없습니다.

이 목록은 XML 매핑 컬렉션 요소 또는 낮은 볼륨 링크에서 사용됩니다.

## 열 목록 추가 {#column-list}

이 컨트롤은 추가 및 삭제 단추가 포함된 도구 모음이 있는 편집 가능한 열 목록을 표시합니다.

```
<input xpath="rcpEvent" type="list">
  <input xpath="@label"/>
  <input xpath="@date"/>
</input>
```

목록 컨트롤을 **type=&quot;list&quot;** 속성과 목록의 경로는 수집 요소를 참조해야 합니다.

그 열은 자식에 선언된다 **`<input>`** 태그입니다. 열 레이블과 크기는 **레이블** 및 **colSize** 속성을 사용합니다.

>[!NOTE]
>
>정렬 순서 화살표는 **ordered=&quot;true&quot;** 속성이 데이터 스키마의 수집 요소에 추가됩니다.

도구 모음 단추는 가로로 정렬할 수 있습니다.

```
<input nolabel="true" toolbarCaption="List of events" type="list" xpath="rcpEvent" zoom="true">
  <input xpath="@label"/>
  <input xpath="@date"/>
</input>
```

다음 **toolbarCaption** 속성을 사용하면 도구 모음의 가로 정렬을 적용하고 목록 위에 제목을 입력합니다.

### 목록 확대 활성화 {#zoom-in-a-list}

목록에서 데이터를 삽입하고 편집하는 작업은 별도의 편집 양식에 입력할 수 있습니다.

```
<input nolabel="true" toolbarCaption="List of events" type="list" xpath="rcpEvent" zoom="true" zoomOnAdd="true">
  <input xpath="@label"/>
  <input xpath="@date"/>

  <form colcount="2" label="Event">
    <input xpath="@label"/>
    <input xpath="@date"/>
  </form>
</input>
```

편집 양식은 `<form>`  목록 정의 아래의 요소. 그 구조는 입력 형태의 구조와 동일하다. 다음 **[!UICONTROL Detail]** 버튼이 자동으로 추가됨 **zoom=&quot;true&quot;** 속성은 다음에서 완료됩니다 **`<input>`** 태그입니다. 이 속성을 사용하여 선택한 라인의 편집 양식을 시작할 수 있습니다.

>[!NOTE]
>
>추가 **zoomOnAdd=&quot;true&quot;** 특성으로 인해 목록 요소가 삽입될 때 편집 양식이 호출됩니다.

### 목록 속성 {#list-properties-1}

* **noToolbar**: 도구 모음을 숨깁니다(값 &quot;true&quot;가 있는 경우).
* **toolbarCaption**: 도구 모음 레이블 오버로드
* **toolbarAlign**: 도구 모음의 위치 지정(가능한 값: &quot;vertical&quot;|&quot;horizontal&quot;)
* **img**: 목록에 연결된 이미지를 표시합니다
* **양식**: 타깃팅된 요소의 편집 양식을 오버로드함
* **확대/축소**: 추가 **[!UICONTROL Zoom]** 타깃팅된 요소를 편집하는 단추
* **zoomOnAdd**: 추가할 때 편집 양식을 시작합니다
* **xpathChoiceTarget**: 또한 입력한 링크에서 선택 양식을 시작합니다

## 편집할 수 없는 필드 추가 {#non-editable-fields}

필드를 표시하고 필드를 편집할 수 없도록 하려면 **`<value>`** 태그 지정 또는 완료 **readOnly=&quot;true&quot;** 속성 **`<input>`** 태그에 가깝게 포함했습니다.

&quot;성별&quot; 필드의 예:

![](assets/do-not-localize/form_exemple16.png)

```
<value value="@gender"/>
<input xpath="@gender" readOnly="true"/>
```

## 라디오 단추 추가 {#radio-button}

라디오 단추를 사용하면 여러 옵션 중에서 선택할 수 있습니다. 다음 **`<input>`** 태그를 사용하여 가능한 옵션과 **checkedValue** 속성은 선택과 연관된 값을 지정합니다.

&quot;성별&quot; 필드의 예:

```
<input type="RadioButton" xpath="@gender" checkedValue="0" label="Choice 1"/>
<input type="RadioButton" xpath="@gender" checkedValue="1" label="Choice 2"/>
<input type="RadioButton" xpath="@gender" checkedValue="2" label="Choice 3"/>
```

![](assets/do-not-localize/form_exemple17.png)

## 확인란 추가 {#checkbox}

확인란은 부울 상태(선택 또는 선택 안 함)를 반영합니다. 기본적으로 이 컨트롤은 &quot;부울&quot;(true/false) 필드에서 사용됩니다. 기본값이 0 또는 1인 변수는 이 버튼과 연결할 수 있습니다. 이 값은 **checkValue** 속성을 사용합니다.

```
<input xpath="@boolean1"/>
<input xpath="@field1" type="checkbox" checkedValue="Y"/>
```

![](assets/do-not-localize/form_exemple20.png)

## 탐색 계층 편집 {#navigation-hierarchy-edit}

이 컨트롤은 편집할 필드 집합에 트리를 만듭니다.

편집할 컨트롤은 **`<container>`** 아래에 **`<input>`** 트리 컨트롤의 태그:

```
<input nolabel="true" type="treeEdit">
  <container label="Text fields">
    <input xpath="@text1"/>
    <input xpath="@text2"/>
  </container>
  <container label="Boolean fields">
    <input xpath="@boolean1"/>
    <input xpath="@boolean2"/>
  </container>
</input>
```

![](assets/do-not-localize/form_exemple18.png)

## 표현식 필드 추가 {#expression-field}

표현식 필드는 표현식에서 동적으로 필드를 업데이트합니다. a **`<input>`** 태그는 **xpath** 업데이트할 필드의 경로 및 속성을 입력합니다. **expr** update 표현식을 포함하는 속성입니다.

```
<!-- Example: updating the boolean1 field from the value contained in the field with path /tmp/@flag -->
<input expr="Iif([/tmp/@flag]=='On', true, false)" type="expr" xpath="@boolean1"/>
<input expr="[/ignored/@action] == 'FCP'" type="expr" xpath="@launchFCP"/>
```

## 양식 컨텍스트 {#context-of-forms}

입력 양식 실행은 편집 중인 엔터티의 데이터를 포함하는 XML 문서를 초기화합니다. 이 문서는 양식의 컨텍스트를 나타내며 작업 공간으로 사용할 수 있습니다.

### 컨텍스트 업데이트 {#updating-the-context}

양식의 컨텍스트를 수정하려면 `<set expr="<value>" xpath="<field>"/>` 태그, 위치 `<field>` 는 대상 필드이며, `<value>` 는 업데이트 표현식 또는 값입니다.

사용 예 `<set>` 태그:

* **`<set expr="'Test'" xpath="/tmp/@test" />`**: 임시 위치 /tmp/@test1에 &#39;테스트&#39; 값을 배치합니다.
* **`<set expr="'Test'" xpath="@lastName" />`**: &quot;lastName&quot; 특성의 엔터티를 &#39;Test&#39; 값으로 업데이트합니다
* **`<set expr="true" xpath="@boolean1" />`**: &quot;boolean1&quot; 필드의 값을 &quot;true&quot;로 설정합니다.
* **`<set expr="@lastName" xpath="/tmp/@test" />`**: lastName 속성의 컨텐츠로 업데이트

을 통해 양식을 초기화하고 닫을 때 양식 컨텍스트를 업데이트할 수 있습니다 **`<enter>`** 및 **`<leave>`** 태그 사이에 Analytics JavaScript 코드를 배치했습니다.

```
<form name="recipient" namespace="cus">
  <enter>
    <set...
  </enter>
  ...
  <leave>
    <set...
  </leave>
</form>
```

>[!NOTE]
>
>다음 `<enter>`  및  `<leave>`   태그는 `<container>` 페이지 유형(&quot;notebook&quot; 및 &quot;iconbox&quot; 유형).

### 표현 언어 {#expression-language-}

조건부 테스트를 수행하기 위해 매크로 언어를 양식 정의에 사용할 수 있습니다.

다음 **`<if expr="<expression>" />`** 태그는 표현식이 확인되는 경우 태그 아래에 지정된 지침을 실행합니다.

```
<if expr="([/tmp/@test] == 'Test' or @lastName != 'Doe') and @boolean2 == true">
  <set xpath="@boolean1" expr="true"/>
</if>
```

다음 **`<check expr="<condition>" />`** 태그와 함께 **`<error>`** 태그는 양식의 유효성을 검사하지 않으며 조건이 충족되지 않으면 오류 메시지를 표시합니다.

```
<leave>
  <check expr="/tmp/@test != ''">
    <error>You must populate the 'Test' field!</error> 
  </check>
</leave>
```

## 도우미(마법사) {#wizards}

도우미가 페이지 형태로 데이터 시작 단계 집합을 안내합니다. 입력한 데이터는 양식의 유효성을 검사할 때 저장됩니다.

도우미를 추가하려면 다음 유형의 구조를 사용하십시오.

```
<form type="wizard" name="example" namespace="cus" img="nms:rcpgroup32.png" label="Wizard example" entity-schema="nms:recipient">
  <container title="Title of page 1" desc="Long description of page 1">
    <input xpath="@lastName"/>
    <input xpath="comment"/>
  </container>
  <container title="Title of page 2" desc="Long description of page 2">
    ...
  </container>
  ...
</form>
```

의 존재 **type=&quot;wizard&quot;** 속성 `<form>` 요소를 사용하면 양식 구성에서 마법사 모드를 정의할 수 있습니다. 페이지는 다음에서 완료됩니다. `<container>` 요소의 하위 요소인 `<form>` 요소를 생성하지 않습니다. 다음 `<container>` 페이지의 요소는 페이지 제목 아래에 설명을 표시하기 위해 제목 및 desc의 제목 속성으로 채워집니다. 다음 **[!UICONTROL Previous]** 및 **[!UICONTROL Next]** 페이지 간에 검색할 수 있도록 버튼이 자동으로 추가됩니다.

다음 **[!UICONTROL Finish]** 입력한 데이터를 저장하고 양식을 닫습니다.

### SOAP 메서드 {#soap-methods}

채운 SOAP 메서드에서 실행할 수 있습니다 **`<leave>`** 태깅 할 수 없습니다.

다음 **`<soapcall>`** 태그에 다음 입력 매개 변수를 사용하는 메서드에 대한 호출이 포함되어 있습니다.

```
<soapCall name="<name>" service="<schema>">
  <param type="<type>" exprIn="<xpath>"/>  
  ...
</soapCall>
```

서비스 이름 및 구현 스키마는 **이름** 및 **서비스** 의 속성 **`<soapcall>`** 태그에 가깝게 포함했습니다.

입력 매개 변수는 **`<param>`** 아래의 요소 **`<soapcall>`** 태그에 가깝게 포함했습니다.

매개 변수 유형은 **유형** 속성을 사용합니다. 가능한 유형은 다음과 같습니다.

* **string**: 문자 문자열
* **부울**: 부울
* **byte**: 8비트 정수
* **short**: 16비트 정수
* **장기간**: 32비트 정수
* **short**: 16비트 정수
* **이중**: 2정밀도 부동 소수점 숫자
* **돔 요소**: element-type 노드

다음 **exprIn** 속성에는 매개 변수로 전달할 데이터의 위치가 포함되어 있습니다.

**예제**:

```
<leave>
  <soapCall name="RegisterGroup" service="nms:recipient">         
    <param type="DOMElement" exprIn="/tmp/entityList"/>         
    <param type="DOMElement" exprIn="/tmp/choiceList"/>         
    <param type="boolean"    exprIn="true"/>       
  </soapCall>
</leave>
```
