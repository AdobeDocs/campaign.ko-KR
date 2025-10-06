---
title: 캠페인 스키마 구조
description: 캠페인 스키마 구조
feature: Schema Extension, Configuration, Data Model
role: Developer
level: Intermediate, Experienced
exl-id: 9c4a9e71-3fc8-4b4e-8782-0742bbeaf426
source-git-commit: 2898fe400e9bf53fc2fe8fde26ccc61ec43bc69e
workflow-type: tm+mt
source-wordcount: '1417'
ht-degree: 1%

---

# 스키마 구조{#schema-structure}

`<srcschema>`의 기본 구조는 다음과 같습니다.

```
<srcSchema>
    <enumeration>
        ...          //definition of enumerations
    </enumeration>
   
    <element>         //definition of the root <element>    (mandatory)

        <compute-string/>  //definition of a compute-string
        <key>
            ...        //definition of keys
        </key>
        <sysFilter>
            ...           //definition of filters
        </sysFilter>
        <attribute>
            ...             //definition of fields
        </attribute>
    
            <element>           //definition of sub-<element> 
                  <attribute>           //(collection, links or XML)
                  ...                         //and additional fields
                  </attribute>
                ...
            </element>
      
    </element> 

        <methods>                 //definition of SOAP methods
            <method>
                ...
            </method>
            ...
    </methods>  
          
</srcSchema>
```

데이터 스키마의 XML 문서에는 스키마 이름과 해당 네임스페이스를 채우려면 **`<srcschema>`**&#x200B;이름&#x200B;**및**&#x200B;네임스페이스&#x200B;**특성이 있는** 루트 요소가 있어야 합니다.

```
<srcSchema name="schema_name" namespace="namespace">
...
</srcSchema>
```

다음 XML 콘텐츠를 사용하여 데이터 스키마의 구조를 보여 드리겠습니다.

```
<recipient email="John.doe@aol.com" created="AAAA/DD/MM" gender="1"> 
  <location city="London"/>
</recipient>
```

해당 데이터 스키마 포함:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <attribute name="email"/>
    <attribute name="created"/>
    <attribute name="gender"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

## 설명 {#description}

스키마의 시작점은 주 요소입니다. 스키마와 이름이 같기 때문에 식별하기 쉽고 루트 요소의 하위 항목이어야 합니다. 콘텐츠에 대한 설명은 이 요소에서 시작됩니다.

이 예제에서 기본 요소는 다음 줄로 표시됩니다.

```
<element name="recipient">
```

기본 요소 뒤에 오는 요소 **`<attribute>`** 및 **`<element>`**&#x200B;을(를) 사용하면 XML 구조에서 데이터 항목의 위치 및 이름을 정의할 수 있습니다.

샘플 스키마에서는 다음과 같습니다.

```
<attribute name="email"/>
<attribute name="created"/>
<attribute name="gender"/>
<element name="location">
  <attribute name="city"/>
</element>
```

다음 규칙을 준수해야 합니다.

* 각 **`<element>`** 및 **`<attribute>`**&#x200B;은(는) **name** 특성을 통해 이름으로 식별되어야 합니다.

  >[!CAUTION]
  >
  >요소의 이름은 간결해야 하며, 가급적 영어로 작성해야 하고, XML 이름 지정 규칙에 따라 승인된 문자만 포함해야 합니다.

* XML 구조에는 **`<element>`** 요소만 **`<attribute>`** 요소와 **`<element>`** 요소를 포함할 수 있습니다.
* **`<attribute>`** 요소는 **`<element>`** 내에서 고유한 이름을 가져야 합니다.
* 여러 줄 데이터 문자열에서 **`<elements>`**&#x200B;을(를) 사용하는 것이 좋습니다.

## 데이터 유형 {#data-types}

데이터 형식은 **및** 요소의 **`<attribute>`** type **`<element>`** 특성을 통해 입력됩니다.

자세한 목록은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=ko#configuring-campaign-classic){target="_blank"}를 참조하세요.

이 특성이 채워지지 않으면 요소에 자식 요소가 들어 있지 않으면 **string**&#x200B;이(가) 기본 데이터 형식입니다. 이 경우 요소를 계층 구조화하는 데만 사용됩니다(이 예제에서는 **`<location>`** 요소).

스키마에서 지원되는 데이터 유형은 다음과 같습니다.

* **문자열**: 문자열. 예: 이름, 마을 등

  **length** 특성(선택 사항, 기본값 &quot;255&quot;)을 통해 크기를 지정할 수 있습니다.

* **부울**: 부울 필드입니다. 가능한 값의 예: true/false, 0/1, yes/no 등.
* **바이트**, **짧음**, **길이**: 정수(1바이트, 2바이트, 4바이트). 예: 나이, 계정 번호, 포인트 수 등
* **double**: 배정밀도 부동 소수점 수입니다. 예: 가격, 요금 등
* **날짜**, **날짜/시간**: 날짜 및 날짜 + 시간. 예: 생년월일, 구매일 등
* **datetimenotz**: 시간대 데이터가 없는 날짜 + 시간입니다.
* **timespan**: 기간. 예: 연공서열.
* **메모**: 긴 텍스트 필드(여러 줄)입니다. 예: 설명, 주석 등
* **uuid**: &quot;uniqueidentifier&quot; 필드

  >[!NOTE]
  >
  >**uuid** 필드를 포함하려면 &quot;newuuid()&quot; 함수를 추가하고 기본값으로 완료해야 합니다.

다음은 입력한 유형이 포함된 예제 스키마입니다.

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <attribute name="email" type="string" length="80"/>
    <attribute name="created" type="datetime"/>
    <attribute name="gender" type="byte"/>
    <element name="location">
      <attribute name="city" type="string" length="50"/>
   </element>
  </element>
</srcSchema>
```

## 속성 {#properties}

데이터 스키마의 **`<elements>`** 및 **`<attributes>`** 요소를 다양한 속성으로 보강할 수 있습니다. 현재 요소를 설명하기 위해 레이블을 채울 수 있습니다.

### 레이블 및 설명 {#labels-and-descriptions}

* **label** 속성을 사용하면 간단한 설명을 입력할 수 있습니다.

  >[!NOTE]
  >
  >레이블은 인스턴스의 현재 언어와 연결됩니다.

  **예**:

  ```
  <attribute name="email" type="string" length="80" label="Email"/>
  ```

  레이블은 Adobe Campaign 클라이언트 콘솔 입력 양식에서 볼 수 있습니다.

  ![](assets/schema_label.png)

* **desc** 속성을 사용하면 긴 설명을 입력할 수 있습니다.

  설명은 Adobe Campaign 클라이언트 콘솔 주 창의 상태 표시줄에 있는 입력 양식에서 볼 수 있습니다.

  >[!NOTE]
  >
  >설명은 인스턴스의 현재 언어와 연결됩니다.

  **예**:

  ```
  <attribute name="email" type="string" length="80" label="Email" desc="Email of recipient"/>
  ```

### 기본값 {#default-values}

**default** 속성을 사용하면 콘텐츠 생성 시 기본값을 반환하는 식을 정의할 수 있습니다.

값은 XPath 언어를 준수하는 표현식이어야 합니다. 이 작업에 대한 자세한 정보는 [이 섹션](#reference-with-xpath)을 참조하십시오.

**예**:

* 현재 날짜: **default=&quot;GetDate()&quot;**
* 카운터: **default=&quot;&#39;FRM&#39;+CounterValue(&#39;myCounter&#39;)&quot;**

  이 예제에서 기본값은 문자열의 연결을 사용하여 만들어지고 무료 카운터 이름으로 **CounterValue** 함수를 호출합니다. 반환되는 숫자는 삽입 시마다 하나씩 증가합니다.

  >[!NOTE]
  >
  >Adobe Campaign 클라이언트 콘솔에서 **[!UICONTROL Administration>Counters]** 노드를 사용하여 카운터를 관리합니다.

필드에 기본값을 연결하려면 `<default>  or  <sqldefault>   field.  </sqldefault> </default>`을(를) 사용합니다.

`<default>`: 엔터티를 만들 때 기본값으로 필드를 미리 채울 수 있도록 해줍니다. 이 값은 기본 SQL 값이 아닙니다.

`<sqldefault>`: 필드를 만들 때 값을 추가할 수 있습니다. 이 값은 SQL 결과로 나타납니다. 스키마 업데이트 중에는 새 레코드만 이 값의 영향을 받습니다.

### 열거형 {#enumerations}

필드 값을 제어하려면 무료, 고정 또는 데이터베이스 기반 [열거형](../config/enumerations.md)을 사용하세요. 보다 쉬운 입력, 일관된 데이터 및 유연한 스키마 디자인을 위한 드롭다운 목록을 제공합니다.

#### 자유 열거형 {#free-enumeration}

**userEnum** 속성을 사용하면 이 필드를 통해 입력한 값을 기억하고 표시할 수 있는 무료 열거형을 정의할 수 있습니다. 구문은 다음과 같습니다.

**userEnum=&quot;열거형 이름&quot;**

열거형에 지정한 이름은 자유롭게 선택하고 다른 필드와 공유할 수 있습니다.

다음 값은 입력 양식의 드롭다운 목록에 표시됩니다.

![](assets/schema_user_enum.png)

>[!NOTE]
>
>Adobe Campaign 클라이언트 콘솔에서 **[!UICONTROL Administration > Enumerations]** 노드는 열거형을 관리하는 데 사용됩니다.

#### 열거형 설정 {#set-enumeration}

**enum** 속성을 사용하면 가능한 값 목록을 미리 알 때 사용되는 고정 열거형을 정의할 수 있습니다.

**enum** 특성은 기본 요소 외부의 스키마에 채워진 열거형 클래스의 정의를 참조합니다.

열거형을 사용하면 일반 입력 필드에 값을 입력하는 대신 드롭다운 목록에서 값을 선택할 수 있습니다.

![](assets/schema_enum.png)

데이터 스키마의 열거 선언 예:

```
<enumeration name="gender" basetype="byte" default="0">    
  <value name="unknown" label="Not specified" value="0"/>    
  <value name="male" label="male" value="1"/>   
  <value name="female" label="female" value="2"/>   
</enumeration>
```

열거형은 **`<enumeration>`** 요소를 통해 주 요소 외부에 선언됩니다.

열거형 속성은 다음과 같습니다.

* **baseType**: 값과 연결된 데이터 형식,
* **label**: 열거형에 대한 설명,
* **이름**: 열거형의 이름,
* **기본값**: 열거형의 기본값.

열거형 값은 다음 특성을 사용하여 **`<value>`** 요소에 선언됩니다.

* **name**: 내부적으로 저장된 값의 이름,
* **label**: 그래픽 인터페이스를 통해 표시되는 레이블입니다.

#### 드베넘 열거 {#dbenum-enumeration}

* **dbenum** 속성을 사용하면 **enum** 속성과 유사한 속성을 가진 열거형을 정의할 수 있습니다.

  그러나 **name** 특성은 값을 내부적으로 저장하지 않으며, 관련 테이블을 스키마를 수정하지 않고 확장할 수 있는 코드를 저장합니다.

  값은 **[!UICONTROL Administration>Enumerations]** 노드를 통해 정의됩니다.

  예를 들어 이 열거형은 캠페인의 특성을 지정하는 데 사용됩니다.

  ![](assets/schema_dbenum.png)

### 예제 {#example}

다음은 속성이 채워진 예제 스키마입니다.

```
<srcSchema name="recipient" namespace="cus">
  <enumeration name="gender" basetype="byte">    
    <value name="unknown" label="Not specified" value="0"/>    
    <value name="male" label="male" value="1"/>   
    <value name="female" label="female" value="2"/>   
  </enumeration>

  <element name="recipient">
    <attribute name="email" type="string" length="80" label="Email" desc="Email of recipient"/>
    <attribute name="created" type="datetime" label="Date of creation" default="GetDate()"/>
    <attribute name="gender" type="byte" label="gender" enum="gender"/>
    <element name="location" label="Location">
      <attribute name="city" type="string" length="50" label="City" userEnum="city"/>
   </element>
  </element>
</srcSchema>
```

## 컬렉션 {#collections}

컬렉션은 이름이 같고 계층 수준이 같은 요소의 목록입니다.

값이 &quot;true&quot;인 **unbound** 특성을 사용하면 컬렉션 요소를 채울 수 있습니다.

**예**: 스키마에 있는 **`<group>`** 컬렉션 요소의 정의입니다.

```
<element name="group" unbound="true" label="List of groups">
  <attribute name="label" type="string" label="Label"/>
</element>
```

XML 콘텐츠 투영 시:

```
<group label="Group1"/>
<group label="Group2"/>
```

## XPath를 사용한 참조 {#reference-with-xpath}

XPath 언어는 Adobe Campaign에서 데이터 스키마에 속하는 요소나 특성을 참조하는 데 사용됩니다.

XPath는 XML 문서의 트리에서 노드를 찾을 수 있는 구문입니다.

요소는 이름으로 지정되고, 속성은 &quot;@&quot; 문자 앞에 오는 이름으로 지정됩니다.

**예**:

* **@email**: 전자 메일을 선택하고
* **location/@city**: **`<location>`** 요소 아래에서 &quot;city&quot; 특성을 선택합니다.
* **../@email**: 현재 요소의 부모 요소에서 전자 메일 주소를 선택합니다.
* **그룹`[1]/@label`**: 첫 번째 **`<group>`** 컬렉션 요소의 자식 &quot;label&quot; 특성을 선택합니다.
* **그룹`[@label='test1']`**: **`<group>`** 요소의 자식이며 &quot;test1&quot; 값을 포함하는 &quot;label&quot; 특성을 선택합니다.

>[!NOTE]
>
>경로가 하위 요소를 교차하면 추가 제약 조건이 추가됩니다. 이 경우 대괄호 사이에 다음 표현식을 배치해야 합니다.
>
>* **location/@city**&#x200B;이(가) 잘못되었습니다. **`[location/@city]`**&#x200B;을(를) 사용하십시오.
>* **`[@email]`**&#x200B;과(와) **@email**&#x200B;이(가) 같습니다.
>

다음 산술 연산과 같은 복잡한 표현식을 정의할 수도 있습니다.

* **@gender+1**: **gender** 특성의 콘텐츠에 1을 추가합니다.
* **@email + &#39;(&#39;+@created+&#39;)&#39;**: 괄호 사이에 만든 날짜에 추가된 전자 메일 주소의 값을 사용하여 문자열을 구성합니다(문자열 형식의 경우 상수를 따옴표로 묶음).

이 언어의 잠재력을 강화하기 위해 표현식에 높은 수준의 함수가 추가되었습니다.

Adobe Campaign 클라이언트 콘솔의 표현식 편집기를 통해 사용 가능한 함수 목록에 액세스할 수 있습니다.

![](assets/schema_function.png)

**예**:

* **GetDate()**: 현재 날짜를 반환합니다.
* **Year(@created)**: &quot;created&quot; 특성에 포함된 날짜의 연도를 반환합니다.
* **GetEmailDomain(@email)**: 전자 메일 주소의 도메인을 반환합니다.

## 계산 문자열을 통해 문자열 빌드 {#building-a-string-via-the-compute-string}

**계산 문자열**&#x200B;은 스키마와 연결된 테이블의 레코드를 나타내는 문자열을 만드는 데 사용되는 XPath 식입니다. **계산 문자열**&#x200B;은 주로 선택한 레코드의 레이블을 표시하는 그래픽 인터페이스에 사용됩니다.

**계산 문자열**&#x200B;은(는) 데이터 스키마의 기본 요소 아래에 있는 **`<compute-string>`** 요소를 통해 정의됩니다. **expr** 특성에 표시를 계산하는 XPath 식이 포함되어 있습니다.

**예**: 받는 사람 테이블의 계산 문자열입니다.

```
<srcSchema name="recipient" namespace="nms">  
  <element name="recipient">
    <compute-string expr="@lastName + ' ' + @firstName +' (' + @email + ')' "/>
    ...
  </element>
</srcSchema>
```

받는 사람에 대한 계산 문자열 결과: **Doe John(john.doe@aol.com)**

>[!NOTE]
>
>스키마에 계산 문자열이 포함되지 않으면 계산 문자열은 기본적으로 스키마의 기본 키 값으로 채워집니다.
