---
solution: Campaign
product: Adobe Campaign
title: 캠페인 스키마 구조
description: 캠페인 스키마 구조
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '1396'
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

스키마 이름 및 해당 네임스페이스를 채우려면 데이터 스키마의 XML 문서에 **`<srcschema>`** 루트 요소가 **name** 및 **namespace** 특성으로 포함되어야 합니다.

```
<srcSchema name="schema_name" namespace="namespace">
...
</srcSchema>
```

다음 XML 내용을 사용하여 데이터 스키마 구조를 보여 줍니다.

```
<recipient email="John.doe@aol.com" created="AAAA/DD/MM" gender="1"> 
  <location city="London"/>
</recipient>
```

해당 데이터 스키마 사용:

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

스키마의 진입점은 기본 요소입니다. 스키마와 동일한 이름을 가지며 루트 요소의 자식이어야 하므로 쉽게 식별할 수 있습니다. 컨텐츠에 대한 설명은 이 요소로 시작합니다.

이 예제에서는 기본 요소를 다음 줄로 표시합니다.

```
<element name="recipient">
```

기본 요소를 따르는 **`<attribute>`** 및 **`<element>`** 요소를 사용하면 XML 구조에서 데이터 항목의 위치와 이름을 정의할 수 있습니다.

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

* 각 **`<element>`** 및 **`<attribute>`**&#x200B;은 **name** 속성을 통해 이름으로 식별되어야 합니다.

   >[!CAUTION]
   >
   >요소 이름은 간결해야 하며, 영어로만 작성되어야 하며 XML 이름 지정 규칙에 따라 권한이 있는 문자만 포함해야 합니다.

* **`<element>`** 요소만 XML 구조에 **`<attribute>`** 요소 및 **`<element>`** 요소를 포함할 수 있습니다.
* **`<attribute>`** 요소는 **`<element>`** 내에 고유한 이름을 가져야 합니다.
* 여러 줄 데이터 문자열에서 **`<elements>`**&#x200B;을 사용하는 것이 좋습니다.

## 데이터 유형 {#data-types}

데이터 유형은 **`<attribute>`** 및 **`<element>`** 요소에서 **type** 특성을 통해 입력됩니다.

자세한 목록은 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic)에서 확인할 수 있습니다.

이 속성이 채워지지 않으면 요소에 자식 요소가 포함되어 있지 않은 한 **string**&#x200B;은 기본 데이터 유형입니다. 그럴 경우 계층 구조 요소(**`<location>`** 요소(예:  요소)에만 사용됩니다.

스키마에서 지원되는 데이터 유형은 다음과 같습니다.

* **문자열**:문자열. 예:이름, 마을 등.

   크기는 **length** 특성(선택 사항, 기본값 &quot;255&quot;)을 통해 지정할 수 있습니다.

* **부울**:부울 필드. 가능한 값의 예:참/거짓, 0/1, 예/아니요 등
* **byte**,  **short**,  **long**:정수(1바이트, 2바이트, 4바이트). 예:연령, 계좌 번호, 포인트 수 등
* **이중**:배정밀도 부동 소수점 숫자 예:가격, 요금 등
* **date**,  **datetime**:날짜 및 날짜 + 시간. 예:생년월일, 구매 날짜 등
* **datetimenotz**:날짜 + 시간(시간대 데이터 없음)
* **timespan**:기간을 설정합니다. 예:상사.
* **메모**:긴 텍스트 필드(여러 줄). 예:설명, 주석 등
* **uuid**:&quot;uniquidentifier&quot; 필드

   >[!NOTE]
   >
   >**uuid** 필드를 포함하려면 &quot;newuuid()&quot; 함수를 추가하고 기본값을 사용하여 완료해야 합니다.

입력한 유형의 예제 스키마는 다음과 같습니다.

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

데이터 스키마의 **`<elements>`** 및 **`<attributes>`** 요소는 다양한 속성을 사용하여 농축할 수 있습니다. 현재 요소를 설명하도록 레이블을 채울 수 있습니다.

### 레이블 및 설명 {#labels-and-descriptions}

* **label** 속성을 사용하여 간단한 설명을 입력할 수 있습니다.

   >[!NOTE]
   >
   >레이블은 인스턴스의 현재 언어와 연결됩니다.

   **예제**:

   ```
   <attribute name="email" type="string" length="80" label="Email"/>
   ```

   레이블은 Adobe Campaign 클라이언트 콘솔 입력 양식에서 볼 수 있습니다.

   ![](assets/schema_label.png)

* **desc** 속성을 사용하여 긴 설명을 입력할 수 있습니다.

   설명은 Adobe Campaign 클라이언트 콘솔 주 창의 상태 표시줄에 있는 입력 양식에서 볼 수 있습니다.

   >[!NOTE]
   >
   >설명은 인스턴스의 현재 언어와 연결됩니다.

   **예제**:

   ```
   <attribute name="email" type="string" length="80" label="Email" desc="Email of recipient"/>
   ```

### 기본값 {#default-values}

**default** 속성을 사용하면 내용 생성 시 기본값을 반환하는 표현식을 정의할 수 있습니다.

값은 XPath 언어와 호환되는 표현식이어야 합니다. 이 작업에 대한 자세한 정보는 [이 섹션](#reference-with-xpath)을 참조하십시오.

**예제**:

* 현재 날짜:**default=&quot;GetDate()&quot;**
* 카운터:**default=&quot;&#39;FRM&#39;+CounterValue(&#39;myCounter&#39;)&quot;**

   이 예제에서 기본값은 문자열의 연결과 무료 카운터 이름으로 **CounterValue** 함수를 호출하여 구성됩니다. 반환되는 번호는 삽입할 때마다 1씩 증가합니다.

   >[!NOTE]
   >
   >Adobe Campaign 클라이언트 콘솔에서 **[!UICONTROL Administration>Counters]** 노드는 카운터를 관리하는 데 사용됩니다.

기본값을 필드에 연결하려면 `<default>  or  <sqldefault>   field.  </sqldefault> </default>`

`<default>` :엔티티를 만들 때 기본값으로 필드를 미리 채울 수 있습니다. 이 값은 기본 SQL 값이 아닙니다.

`<sqldefault>` :필드를 만들 때 값을 추가할 수 있습니다. 이 값은 SQL 결과로 나타납니다. 스키마 업데이트 중에 새 레코드만 이 값에 영향을 받습니다.

### 열거형 {#enumerations}

#### 무료 열거형 {#free-enumeration}

**userEnum** 속성을 사용하면 이 필드를 통해 입력한 값을 암기하고 표시할 무료 열거형을 정의할 수 있습니다. 구문은 다음과 같습니다.

**userEnum=&quot;name of enumeration&quot;**

열거형에 지정된 이름은 자유롭게 선택하고 다른 필드와 공유할 수 있습니다.

이러한 값은 입력 양식의 드롭다운 목록에 표시됩니다.

![](assets/schema_user_enum.png)

>[!NOTE]
>
>Adobe Campaign 클라이언트 콘솔에서 **[!UICONTROL Administration > Enumerations]** 노드가 열거형을 관리하는 데 사용됩니다.

#### 열거형 {#set-enumeration} 설정

**enum** 속성을 사용하면 가능한 값 목록을 미리 알 때 사용되는 고정 열거형을 정의할 수 있습니다.

**enum** 특성은 기본 요소 외부에 있는 스키마에 채워진 열거형 클래스의 정의를 나타냅니다.

열거형을 사용하면 일반 입력 필드에 값을 입력하는 대신 드롭다운 목록에서 값을 선택할 수 있습니다.

![](assets/schema_enum.png)

데이터 스키마의 열거형 선언의 예:

```
<enumeration name="gender" basetype="byte" default="0">    
  <value name="unknown" label="Not specified" value="0"/>    
  <value name="male" label="male" value="1"/>   
  <value name="female" label="female" value="2"/>   
</enumeration>
```

열거형은 **`<enumeration>`** 요소를 통해 기본 요소 외부에 선언됩니다.

열거형 속성은 다음과 같습니다.

* **baseType**:값과 관련된 데이터 유형,
* **레이블**:열거에 대한 설명,
* **이름**:열거형의 이름,
* **기본값**:열거형의 기본값.

열거형 값은 다음 특성을 가진 **`<value>`** 요소에 선언됩니다.

* **이름**:내부적으로 저장된 값의 이름,
* **레이블**:그래픽 인터페이스를 통해 표시되는 레이블입니다.

#### dbenum enumeration {#dbenum-enumeration}

* **dbenum** 속성을 사용하여 **enum** 속성의 속성과 비슷한 속성을 갖는 열거형을 정의할 수 있습니다.

   그러나 **name** 속성은 값을 내부적으로 저장하지 않고 스키마를 수정하지 않고 관련 테이블을 확장할 수 있는 코드를 저장합니다.

   값은 **[!UICONTROL Administration>Enumerations]** 노드를 통해 정의됩니다.

   이 열거형은 예를 들어 캠페인의 특성을 지정하는 데 사용됩니다.

   ![](assets/schema_dbenum.png)

### 예제 {#example}

속성이 채워진 예제 스키마는 다음과 같습니다.

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

컬렉션은 동일한 이름과 동일한 계층 수준의 요소 목록입니다.

값이 &quot;true&quot;인 **언바운드** 특성을 사용하여 컬렉션 요소를 채울 수 있습니다.

**예**:스키마에 있는  **`<group>`** 컬렉션 요소의 정의입니다.

```
<element name="group" unbound="true" label="List of groups">
  <attribute name="label" type="string" label="Label"/>
</element>
```

XML 컨텐츠 투영 사용:

```
<group label="Group1"/>
<group label="Group2"/>
```

## XPath {#reference-with-xpath}에 대한 참조

XPath 언어는 Adobe Campaign에서 데이터 스키마에 속하는 요소 또는 특성을 참조하는 데 사용됩니다.

XPath는 XML 문서의 트리에서 노드를 찾을 수 있는 구문입니다.

요소는 이름으로 지정되며 속성은 문자 앞에 &quot;@&quot;가 붙은 이름으로 지정됩니다.

**예제**:

* **@email**:이메일을 선택하고
* **location/@city**:요소 아래의 &quot;city&quot; 속성을  **`<location>`** 선택합니다.
* **../@email**:현재 요소의 상위 요소에서 전자 메일 주소를 선택합니다.
* **그룹`[1]/@label`**:첫 번째  **`<group>`** 컬렉션 요소의 하위 항목인 &quot;label&quot; 속성을 선택합니다.
* **그룹`[@label='test1']`**:요소의 자식이며 &quot;test1&quot; 값을 포함하는 &quot;label&quot;  **`<group>`** 속성을 선택합니다.

>[!NOTE]
>
>패스가 하위 요소를 교차할 때 추가 제약 조건이 추가됩니다. 이 경우 대괄호 사이에 다음 표현식을 배치해야 합니다.
>
>* **location/@** cityn이 잘못되었습니다.사용  **`[location/@city]`**
>* **`[@email]`** 및  **@** emailare equivalent

>



다음 산술 연산과 같이 복잡한 표현식을 정의할 수도 있습니다.

* **@gender+1**:genderattribute의 컨텐츠에 1을  **** 추가합니다.
* **@email + &#39;(&#39;+@created+&#39;)&#39;**:괄호 사이에 만든 날짜에 추가된 전자 메일 주소 값을 사용하여 문자열을 생성합니다(문자열 유형의 경우 따옴표로 상수를 넣습니다).

이 언어의 가능성을 높이기 위해 고급 기능이 표현식에 추가되었습니다.

Adobe Campaign 클라이언트 콘솔에서 표현식 편집기를 통해 사용 가능한 함수 목록에 액세스할 수 있습니다.

![](assets/schema_function.png)

**예제**:

* **GetDate()**:현재 날짜를 반환합니다.
* **연도(@created)**:&quot;created&quot; 속성에 포함된 날짜의 연도를 반환합니다.
* **GetEmailDomain(@email)**:전자 메일 주소의 도메인을 반환합니다.

## 계산 문자열 {#building-a-string-via-the-compute-string}을(를) 통해 문자열 만들기

**계산 문자열**&#x200B;은 스키마와 연관된 테이블의 레코드를 나타내는 문자열을 만드는 데 사용되는 XPath 표현식입니다. **계산** 문자열은 주로 그래픽 인터페이스에서 선택한 레코드의 레이블을 표시하는 데 사용됩니다.

**계산 문자열**&#x200B;은 데이터 스키마의 주 요소 아래의 **`<compute-string>`** 요소를 통해 정의됩니다. **expr** 속성에는 디스플레이를 계산하는 XPath 식이 포함되어 있습니다.

**예**:받는 사람 테이블의 계산 문자열.

```
<srcSchema name="recipient" namespace="nms">  
  <element name="recipient">
    <compute-string expr="@lastName + ' ' + @firstName +' (' + @email + ')' "/>
    ...
  </element>
</srcSchema>
```

수신자에 대한 계산된 문자열의 결과:**Doe John (john.doe@aol.com)**

>[!NOTE]
>
>스키마에 계산 문자열이 없는 경우, 계산 문자열은 기본적으로 스키마의 기본 키 값으로 채워집니다.
