---
product: Adobe Campaign
title: Campaign 데이터베이스 매핑
description: Campaign 데이터베이스 매핑
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '1463'
ht-degree: 0%

---

# 데이터베이스 매핑{#database-mapping}

예제 스키마의 SQL 매핑은 다음 XML 문서를 제공합니다.

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">
  <enumeration basetype="byte" name="gender">    
    <value label="Not specified" name="unknown" value="0"/>    
    <value label="Male" name="male" value="1"/>    
    <value label="Female" name="female" value="2"/> 
  </enumeration>  

  <element name="recipient" sqltable="CusRecipient">    
    <attribute desc="Recipient e-mail address" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
    <attribute default="GetDate()" label="Date of creation" name="created" sqlname="tsCreated" type="datetime"/>    
    <attribute enum="gender" label="Gender" name="gender" sqlname="iGender" type="byte"/>    
    <element label="Location" name="location">      
      <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
    </element>  
  </element>
</schema>
```

## 설명 {#description}

스키마의 루트 요소가 더 이상 **`<srcschema>`**&#x200B;이 아니라 **`<schema>`**&#x200B;입니다.

이렇게 하면 소스 스키마에서 자동으로 생성되는 다른 유형의 문서가 스키마라고 합니다. 이 스키마는 Adobe Campaign 애플리케이션에서 사용됩니다.

SQL 이름은 요소 이름과 유형에 따라 자동으로 결정됩니다.

SQL 이름 지정 규칙은 다음과 같습니다.

* 표:스키마 네임스페이스 및 이름 연결

   이 예제에서 테이블 이름은 **sqltable** 특성에 있는 스키마의 기본 요소를 통해 입력됩니다.

   ```
   <element name="recipient" sqltable="CusRecipient">
   ```

* 필드:형식에 따라 정의된 접두사가 앞에 오는 요소의 이름(&#39;i&#39;, 정수의 경우 &#39;d&#39;, 문자열의 경우 &#39;s&#39;, 날짜의 경우 &#39;ts&#39; 등)

   필드 이름은 입력한 각 **`<attribute>`** 및 **`<element>`**&#x200B;에 대해 **sqlname** 속성을 통해 입력됩니다.

   ```
   <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
   ```

>[!NOTE]
>
>소스 스키마에서 SQL 이름을 오버로드할 수 있습니다. 이렇게 하려면 관련 요소에서 &quot;sqltable&quot; 또는 &quot;sqlname&quot; 속성을 채웁니다.

확장 스키마에서 생성된 테이블을 만드는 SQL 스크립트는 다음과 같습니다.

```
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

SQL 필드 제약 조건은 다음과 같습니다.

* 숫자 및 날짜 필드에 null 값이 없습니다.
* 숫자 필드가 0으로 초기화됩니다.

## XML 필드 {#xml-fields}

기본적으로 입력한 **`<attribute>`** 및 **`<element>`** 요소는 데이터 스키마 테이블의 SQL 필드에 매핑됩니다. 그러나 SQL 대신 XML에서 이 필드를 참조할 수 있으므로 모든 XML 필드의 값이 들어 있는 테이블의 메모 필드(&quot;mData&quot;)에 데이터가 저장됨을 의미합니다. 이러한 데이터의 저장소는 스키마 구조를 준수하는 XML 문서입니다.

XML의 필드를 채우려면 **xml** 속성을 &quot;true&quot; 값으로 해당 요소에 추가해야 합니다.

**예**:다음은 XML 필드 사용의 두 가지 예입니다.

* 여러 줄 주석 필드:

   ```
   <element name="comment" xml="true" type="memo" label="Comment"/>
   ```

* HTML 형식의 데이터에 대한 설명:

   ```
   <element name="description" xml="true" type="html" label="Description"/>
   ```

   html 유형을 사용하면 HTML 컨텐츠를 CDATA 태그에 저장하고 Adobe Campaign 클라이언트 인터페이스에 특수 HTML 편집 검사를 표시할 수 있습니다.

XML 필드를 사용하면 데이터베이스의 물리적 구조를 수정할 필요 없이 필드를 추가할 수 있습니다. 리소스(SQL 필드에 할당된 크기, 테이블당 필드 수의 제한 등)를 줄일 수도 있습니다.

## 키 관리 {#management-of-keys}

테이블에 테이블의 레코드를 식별하는 키가 하나 이상 있어야 합니다.

키는 데이터 스키마의 기본 요소에서 선언됩니다.

```
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

키는 다음 규칙에 따릅니다.

* 키는 테이블에서 하나 이상의 필드를 참조할 수 있습니다.
* 키는 채울 스키마의 첫 번째 경우나 값이 &quot;true&quot;인 **internal** 속성을 포함하는 경우 &#39;primary&#39;(또는 &#39;priority&#39;)라고 합니다.

**예제**:

* 전자 메일 주소 및 도시에 키 추가:

   ```
   <srcSchema name="recipient" namespace="cus">
     <element name="recipient">
       <key name="email">
         <keyfield xpath="@email"/> 
         <keyfield xpath="location/@city"/> 
       </key>
   
       <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
       <element name="location" label="Location">
         <attribute name="city" type="string" length="50" label="City" userEnum="city"/>
       </element>
     </element>
   </srcSchema>
   ```

   생성된 스키마:

   ```
   <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
     <element name="recipient" sqltable="CusRecipient">    
      <key name="email">      
       <keyfield xpath="@email"/>      
       <keyfield xpath="location/@city"/>    
      </key>    
   
      <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
      <element label="Location" name="location">      
        <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
      </element>  
     </element>
   </schema>
   ```

* &quot;id&quot; 이름 필드에 기본 또는 내부 키 추가:

   ```
   <srcSchema name="recipient" namespace="cus">
     <element name="recipient">
       <key name="id" internal="true">
         <keyfield xpath="@id"/> 
       </key>
   
       <key name="email">
         <keyfield xpath="@email"/> 
       </key>
   
       <attribute name="id" type="long" label="Identifier"/>
       <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
     </element>
   </srcSchema>
   ```

   생성된 스키마:

   ```
   <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
     <element name="recipient" sqltable="CusRecipient">    
       <key name="email">      
         <keyfield xpath="@email"/>    
       </key>  
   
       <key internal="true" name="id">      
        <keyfield xpath="@id"/>    
       </key>    
   
       <attribute label="Identifier" name="id" sqlname="iRecipientId" type="long"/>    
       <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>  
     </element>
   </schema>
   ```

### 기본 키 - 식별자

Adobe Campaign 테이블의 기본 키는 데이터베이스 엔진에서 자동으로 생성된 **Universally Unique ID(UUID)**&#x200B;입니다. 키 값은 전체 데이터베이스에서 고유합니다. 레코드의 삽입 시 키의 내용이 자동으로 생성됩니다.

**예제**

소스 스키마에서 증분 키 선언:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"  autopk="true" autouuid="true">
  ...
  </element>
</srcSchema>
```

생성된 스키마:

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient"  autopk="true" autouuid="true" sqltable="CusRecipient"> 

    <key internal="true" name="id">
      <keyfield xpath="@id"/>
    </key>

    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iRecipientId" type="long"/>
  </element>
</schema>
```

키의 정의 외에 자동 생성된 기본 키를 포함하기 위해 &quot;id&quot;라는 숫자 필드가 확장 스키마에 추가되었습니다.

>[!CAUTION]
>
>테이블 생성 시 기본 키가 0으로 설정된 레코드가 자동으로 삽입됩니다. 이 레코드는 볼륨 테이블에서 유효하지 않은 외부 조인을 방지하기 위해 사용됩니다. 기본적으로 모든 외래 키는 값 0으로 초기화되므로 데이터 항목이 채워지지 않을 때 조인에서 항상 결과를 반환할 수 있습니다.

## 링크:{#links--relation-between-tables} 테이블 간의 관계

링크는 한 테이블과 다른 테이블 간의 연결을 설명합니다.

다양한 연결 유형(&quot;카디널리티&quot;라고 함)은 다음과 같습니다.

* 카디널리티 1-1:소스 테이블의 발생 항목 하나는 타겟 테이블의 해당 발생 항목을 최대 한 개까지 가질 수 있습니다.
* 카디널리티 1-N:소스 테이블의 발생 항목 하나는 타겟 테이블의 여러 발생 항목을 가질 수 있지만, 타겟 테이블의 발생 항목 하나는 소스 테이블의 해당 발생 항목을 최대 한 개까지 가질 수 있습니다.
* 카디널리티 N-N:소스 테이블의 발생 항목 하나는 타겟 테이블의 여러 발생 항목을 가질 수 있고, 그 반대의 경우도 마찬가지입니다.

인터페이스에서 아이콘 덕분에 다양한 유형의 관계를 쉽게 구분할 수 있습니다.

캠페인 테이블/데이터베이스와 연결 관계의 경우:

* ![](assets/do-not-localize/join_with_campaign11.png) :카디널리티 1-1. 예를 들어, 수신자와 현재 순서 사이의 경우입니다. 수신자는 한 번에 하나의 현재 주문 테이블의 발생 항목만 연관시킬 수 있습니다.
* ![](assets/do-not-localize/externaljoin11.png) :카디널리티 1-1, 외부 조인 예를 들어, 수신자와 해당 국가 간. 수신자는 테이블 국가의 발생 항목만 연관시킬 수 있습니다. 국가 테이블의 내용은 저장되지 않습니다.
* ![](assets/do-not-localize/join_with_campaign1n.png) :카디널리티 1-N.예를 들어 수신자 및 구독 테이블 간. 수신자는 가입 테이블의 여러 발생 횟수와 관련될 수 있습니다.

Federated Database Access를 사용한 조인 관계의 경우:

* ![](assets/do-not-localize/join_fda_11.png) :카디널리티 1-1
* ![](assets/do-not-localize/join_fda_1m.png) :카디널리티 1-N

[!DNL :bulb:] FDA 테이블에 대한 자세한 내용은  [Federated Data Access](../connect/fda.md)를 참조하십시오.

주 요소를 통해 연결된 테이블의 외래 키가 포함된 스키마에서 링크를 선언해야 합니다.

```
<element name="name_of_link" type="link" target="key_of_destination_schema">
  <join xpath-dst="xpath_of_field1_destination_table" xpath-src="xpath_of_field1_source_table"/>
  <join xpath-dst="xpath_of_field2_destination_table" xpath-src="xpath_of_field2_source_table"/>
  ...
</element>
```

링크는 다음 규칙에 따릅니다.

* 링크의 정의는 다음 속성을 사용하여 **link**-type **`<element>`**&#x200B;에 입력됩니다.

   * **이름**:소스 테이블의 링크 이름,
   * **target**:대상 스키마 이름,
   * **레이블**:링크 레이블,
   * **revLink** (선택 사항):대상 스키마에서 역방향 링크 이름(기본적으로 자동으로 추론됨),
   * **integrity** (선택 사항):대상 테이블의 발생에 대한 소스 테이블의 참조 무결성 가능한 값은 다음과 같습니다.

      * **정의**:대상 발생에 의해 더 이상 참조되지 않는 경우 소스 발생을 삭제할 수 있습니다.
      * **일반**:소스 발생 삭제 시 대상 발생(기본 모드)에 대한 링크의 키가 초기화되고 이 유형의 무결성은 모든 외래 키를 초기화합니다.
      * **자체**:소스 발생 항목을 삭제하면 타겟 항목이 삭제됩니다.
      * **다운로드**: **자체** (삭제의 경우)와 동일하거나 발생 횟수(중복의 경우)를 복제합니다.
      * **중립**:아무 작업도 하지 않습니다.
   * **revIntegrity** (선택 사항):대상 스키마의 무결성(선택 사항, &quot;정상&quot;),
   * **revCardinality** (선택 사항):값이 &quot;single&quot;이면 카디널리티는 유형 1-1(기본적으로 1-N)으로 채워집니다.
   * **externalJoin** (선택 사항):외부 결합 강제 적용
   * **revExternalJoin** (선택 사항):외부 연결을 역링크에 강제 적용


* 링크는 소스 테이블에서 대상 테이블로 하나 이상의 필드를 참조합니다. 조인( `<join>` 요소)을 구성하는 필드는 대상 스키마의 내부 키를 사용하여 기본적으로 자동으로 추론되므로 채우지 않아도 됩니다.
* 링크는 소스 스키마에서 첫 번째 링크가 선언되고 두 번째 링크는 대상 스키마의 확장 스키마에서 자동으로 만들어집니다.
* **externalJoin** 특성이 추가되고 값 &quot;true&quot;(PostgreSQL에서 지원됨)가 있는 경우 조인은 외부 조인이 될 수 있습니다.

>[!NOTE]
>
>링크는 스키마 끝에 선언된 요소입니다.

### 예제 1 {#example-1}

1-N은 &quot;cus:company&quot; 스키마 테이블과 관련되어 있습니다.

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    ...
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

생성된 스키마:

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" sqltable="CusRecipient"> 
    ...
    <element label="Company" name="company" revLink="recipient" target="cus:company" type="link">      
      <join xpath-dst="@id" xpath-src="@company-id"/>    
    </element>    
    <attribute advanced="true" label="Foreign key of 'Company' link (field 'id')" name="company-id" sqlname="iCompanyId" type="long"/>
  </element>
</schema>
```

링크 정의는 조인을 구성하는 필드, 즉 대상 스키마에 XPath(&quot;@id&quot;)가 있는 기본 키 및 스키마에 XPath(&quot;@company-id&quot;)가 있는 외부 키에 의해 보완됩니다.

외래 키는 다음 명명 규칙을 사용하여 대상 테이블의 관련 필드와 동일한 특성을 사용하는 요소에 자동으로 추가됩니다.대상 스키마의 이름 뒤에 관련 필드 이름(이 예제에서는 &quot;company-id&quot;)이 옵니다.

대상의 확장 스키마(&quot;cus:company&quot;):

```
<schema mappingType="sql" name="company" namespace="cus" xtkschema="xtk:schema">  
  <element name="company" sqltable="CusCompany"  autopk="true" autouuid="true"> 
    <key internal="true" name="id">      
      <keyfield xpath="@id"/>    
    </key>
    ...
    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iCompanyId" type="long"/>
    ...
    <element belongsTo="cus:recipient" integrity="define" label="Contact" name="recipient" revLink="company" target="nms:recipient" type="link" unbound="true">      
      <join xpath-dst="@company-id" xpath-src="@id"/>    
    </element>
  </element>
</schema>
```

다음 매개 변수와 함께 &quot;cus:recipient&quot; 테이블에 대한 역방향 링크가 추가되었습니다.

* **이름**:소스 스키마의 이름에서 자동으로 추론됩니다(소스 스키마의 링크 정의에 &quot;revLink&quot; 속성으로 강제 적용할 수 있음).
* **revLink**:역링크 이름
* **target**:연결된 스키마 키(&quot;cus:recipient&quot; 스키마)
* **바인딩되지 않음**:링크는 1-N 카디널리티에 대한 수집 요소로 선언됩니다(기본적으로)
* **무결성**:기본적으로 &quot;define&quot;(소스 스키마의 링크 정의에 &quot;revIntegrity&quot; 속성으로 강제 지정할 수 있음).

### 예제 2 {#example-2}

이 예에서는 &quot;nms:address&quot; 스키마 테이블에 대한 링크를 선언합니다. 조인은 외부 조인으로 받는 사람의 전자 메일 주소와 연결된 테이블의 &quot;@address&quot; 필드(&quot;nms:address&quot;)로 명시적으로 채워집니다.

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"> 
    ...
    <element integrity="neutral" label="Info about email" name="emailInfo" revIntegrity="neutral" revLink="recipient" target="nms:address" type="link" externalJoin="true">      
      <join xpath-dst="@address" xpath-src="@email"/>
    </element>
  </element>
</srcSchema>
```

### 예제 3 {#example-3}

&quot;cus:extension&quot; 스키마 테이블과 1-1 관계:

```
<element integrity="own" label="Extension" name="extension" revCardinality="single" revLink="recipient" target="cus:extension" type="link"/>
```

### 예제 5 {#example-4}

폴더(&quot;xtk:folder&quot; 스키마)에 대한 링크:

```
<element default="DefaultFolder('nmsFolder')" label="Folder" name="folder" revDesc="Recipients in the folder" revIntegrity="own" revLabel="Recipients" target="xtk:folder" type="link"/>
```

기본값은 &quot;DefaultFolder(&#39;nmsFolder&#39;)&quot; 함수에 입력한 첫 번째 적합한 매개 변수 형식 파일의 식별자를 반환합니다.

### 예제 5 {#example-5}

이 예에서는 **xlink** 속성과 (&quot;email&quot;) 테이블의 필드를 사용하는 링크(&quot;company&quot;와 &quot;cus:company&quot; 스키마)에 대한 키를 만들려고 합니다.

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <key name="companyEmail"> 
      <keyfield xpath="@email"/>
      <keyfield xlink="company"/>
    </key>
    
    <attribute name="email" type="string" length="80" label="Email" desc="Recipient email"/>
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

생성된 스키마:

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" sqltable="CusRecipient"> 
    <key name="companyEmail">      
      <keyfield xpath="@email"/>      
      <keyfield xpath="@company-id"/>    
    </key>

    <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>
    <element label="Company" name="company" revLink="recipient" target="sfa:company" type="link">      
      <join xpath-dst="@id" xpath-src="@company-id"/>    
    </element>    
    <attribute advanced="true" label="Foreign key of link 'Company' (field 'id')" name="company-id" sqlname="iCompanyId" type="long"/>
  </element>
</schema>
```

companyEmail 이름 키의 정의가 &quot;company&quot; 링크의 외부 키로 확장되었습니다.
