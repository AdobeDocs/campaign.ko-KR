---
title: Campaign 스키마의 링크 관리
description: Adobe Campaign 스키마의 링크 관리 이해
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
source-git-commit: c7171a121f03eff0d945e64758e3ba1842e5436f
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 0%

---


# 링크 관리 {#links--relation-between-tables}

링크는 한 테이블과 다른 테이블 간의 연관을 설명합니다.

다음은 카디널리티라고도 하는 연관 유형입니다.

* 카디널리티 1-1: 소스 테이블의 발생 항목 하나는 타겟 테이블의 해당 발생 항목을 최대 한 개까지 가질 수 있습니다.
* 카디널리티 1-N: 소스 테이블의 발생 항목 하나는 타겟 테이블의 여러 발생 항목을 가질 수 있지만, 타겟 테이블의 발생 항목 하나는 소스 테이블의 해당 발생 항목을 최대 한 개까지 가질 수 있습니다.
* 카디널리티 N-N: 소스 테이블의 발생 항목 하나는 타겟 테이블의 여러 발생 항목을 가질 수 있으며, 그 반대의 경우도 가능합니다.

사용 인터페이스에서 카디널리티는 특정 아이콘으로 표시됩니다.

캠페인 테이블/데이터베이스와의 조인 관계의 경우:

* ![](assets/do-not-localize/join_with_campaign11.png) : 카디널리티 1-1. 예를 들어 수신자와 현재 주문 간에 적용될 수 있습니다. 수신자는 현재 주문 테이블을 한 번에 하나만 연결할 수 있습니다.
* ![](assets/do-not-localize/externaljoin11.png) : 카디널리티 1-1, 외부 조인. 예를 들어 수신자와 해당 국가 간. 수신자는 한 테이블 국가에만 관련될 수 있습니다. 국가 테이블의 내용은 저장되지 않습니다.
* ![](assets/do-not-localize/join_with_campaign1n.png) : 카디널리티 1-N. 예를 들어 수신자와 구독 테이블 간 수신자는 구독 테이블의 여러 발생 횟수와 관련될 수 있습니다.

FDA(Federated Database Access)를 사용하는 조인 관계의 경우:

* ![](assets/do-not-localize/join_fda_11.png) : 카디널리티 1-1
* ![](assets/do-not-localize/join_fda_1m.png) : 카디널리티 1-N

FDA 표에 대한 자세한 내용은 [외부 데이터베이스 액세스](../../installation/using/about-fda.md).

주 요소를 통해 연결된 테이블의 외래 키를 포함하는 스키마에서 링크를 선언해야 합니다.

```sql
<element name="name_of_link" type="link" target="key_of_destination_schema">
  <join xpath-dst="xpath_of_field1_destination_table" xpath-src="xpath_of_field1_source_table"/>
  <join xpath-dst="xpath_of_field2_destination_table" xpath-src="xpath_of_field2_source_table"/>
  ...
</element>
```

링크는 다음 규칙을 따릅니다.

* 링크의 정의는 **링크**-type **`<element>`** 다음 속성을 사용합니다.

   * **이름**: 소스 테이블의 링크 이름
   * **target**: 대상 스키마 이름
   * **레이블**: 링크 레이블
   * **revLink** (선택 사항): 대상 스키마의 역방향 링크 이름(기본적으로 자동으로 추론됨)
   * **무결성** (선택 사항): 소스 테이블의 발생과 대상 테이블의 발생에 대한 참조 무결성.
가능한 값:

      * **정의**: 대상 발생에서 더 이상 참조하지 않는 경우 소스 발생을 삭제할 수 있습니다
      * **표준**: 소스 발생 항목을 삭제하면 대상 발생 항목에 대한 링크의 키가 초기화됩니다(기본 모드). 이 유형의 무결성은 모든 외래 키를 초기화합니다
      * **소유**: 소스 발생 횟수를 삭제하면 타겟 발생 횟수가 삭제됩니다
      * **owncopy**: 와 동일 **소유** (삭제 시) 또는 발생 횟수 중복(중복 시)
      * **중립**: 특정 비헤이비어 없음

   * **revIntegrity** (선택 사항): 대상 스키마의 무결성 (선택 사항, 기본적으로 &quot;보통&quot;)
   * **반대 카디널리티** (선택 사항): 값 &quot;single&quot;을 사용하면 카디널리티가 유형 1-1(기본적으로 1-N)로 채워집니다.
   * **externalJoin** (선택 사항): 외부 조인을 강제 적용합니다
   * **revExternalJoin** (선택 사항): 역방향 링크에 외부 조인을 강제 적용합니다

* 링크는 소스 테이블에서 대상 테이블로 하나 이상의 필드를 참조합니다. 조인을 구성하는 필드( `<join>`  요소)는 대상 스키마의 내부 키를 사용하여 기본적으로 자동으로 추론되므로 채우지 않아도 됩니다.
* 확장 스키마에 있는 링크의 외부 키에 인덱스가 자동으로 추가됩니다.
* 링크는 두 개의 절반 링크로 구성되며, 첫 번째 링크는 소스 스키마에서 선언되고 두 번째 링크는 대상 스키마의 확장 스키마에서 자동으로 만들어집니다.
* 다음 경우에 조인은 외부 조인이 될 수 있습니다. **externalJoin** 값이 &quot;true&quot;인 속성이 추가됩니다(PostgreSQL에서 지원됨).

>[!NOTE]
>
>표준으로 링크는 스키마 끝에 선언된 요소입니다.

## 예: 역방향 링크 {#example-1}

아래 예에서는 &quot;cus:company&quot; 스키마 테이블과 1-N 관계를 선언합니다.

```sql
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    ...
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

생성된 스키마:

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" sqltable="CusRecipient"> 
    <dbindex name="companyId">      
      <keyfield xpath="@company-id"/>    
    </dbindex>
    ...
    <element label="Company" name="company" revLink="recipient" target="cus:company" type="link">      
      <join xpath-dst="@id" xpath-src="@company-id"/>    
    </element>    
    <attribute advanced="true" label="Foreign key of 'Company' link (field 'id')" name="company-id" sqlname="iCompanyId" type="long"/>
  </element>
</schema>
```

링크 정의는 조인을 구성하는 필드, 즉 대상 스키마에 해당 XPath(&quot;@id&quot;)가 있는 기본 키와 스키마에 해당 XPath(&quot;@company-id&quot;)가 있는 외래 키로 보완됩니다.

외래 키는 대상 테이블의 관련 필드와 동일한 특성을 사용하는 요소에 자동으로 추가되며, 다음과 같은 명명 규칙이 적용됩니다. 대상 스키마 이름 뒤에 관련 필드 이름(&quot;회사 ID&quot;)이 표시됩니다.

대상의 확장 스키마(&quot;cus:company&quot;):

```sql
<schema mappingType="sql" name="company" namespace="cus" xtkschema="xtk:schema">  
  <element name="company" sqltable="CusCompany" autopk="true"> 
    <dbindex name="id" unique="true">     
      <keyfield xpath="@id"/>    
    </dbindex>   
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

다음 매개 변수와 함께 &quot;cus:recipient&quot; 표에 대한 역방향 링크가 추가되었습니다.

* **이름**: 소스 스키마의 이름에서 자동으로 추론됩니다(소스 스키마의 링크 정의에 &quot;revLink&quot; 속성으로 강제 추론될 수 있음).
* **revLink**: 역방향 링크 이름
* **target**: 연결된 스키마의 키(&quot;cus:recipient&quot; 스키마)
* **바인딩되지 않음**: 링크는 1-N 카디널리티에 대한 컬렉션 요소로 선언됩니다(기본값)
* **무결성**: 기본적으로 &quot;define&quot;(소스 스키마의 링크 정의에 &quot;revIntegrity&quot; 속성으로 강제 적용할 수 있음)

## 예: 단순 링크 {#example-2}

이 예제에서는 &quot;nms:address&quot; 스키마 테이블에 대한 링크를 선언합니다. 조인은 외부 조인이며 받는 사람의 이메일 주소와 연결된 테이블(&quot;nms:address&quot;)의 &quot;@address&quot; 필드로 명시적으로 채워집니다.

```sql
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"> 
    ...
    <element integrity="neutral" label="Info about email" name="emailInfo" revIntegrity="neutral" revLink="recipient" target="nms:address" type="link" externalJoin="true">      
      <join xpath-dst="@address" xpath-src="@email"/>
    </element>
  </element>
</srcSchema>
```

## 예: 고유 카디널리티 {#example-3}

이 예제에서는 &quot;cus:extension&quot; 스키마 테이블에 대해 1-1 관계를 만듭니다.

```sql
<element integrity="own" label="Extension" name="extension" revCardinality="single" revLink="recipient" target="cus:extension" type="link"/>
```

## 예: 폴더에 대한 링크 {#example-4}

이 예제에서는 폴더(&quot;xtk:folder&quot; 스키마)에 대한 링크를 선언합니다.

```sql
<element default="DefaultFolder('nmsFolder')" label="Folder" name="folder" revDesc="Recipients in the folder" revIntegrity="own" revLabel="Recipients" target="xtk:folder" type="link"/>
```

기본값은 &quot;DefaultFolder(&#39;nmsFolder&#39;)&quot; 함수에 입력된 첫 번째 적격 매개 변수 유형 파일의 식별자를 반환합니다.

## 예: 링크에 키 만들기 {#example-5}

이 예제에서는 를 사용하는 링크(&quot;company&quot; to &quot;cus:company&quot; schema)에 키를 만듭니다. **xlink** (&quot;email&quot;) 테이블의 속성 및 필드:

```sql
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

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" sqltable="CusRecipient"> 
    <dbindex name="companyId">      
      <keyfield xpath="@company-id"/>    
    </dbindex>

    <dbindex name="companyEmail" unique="true">
      <keyfield xpath="@email"/>      
      <keyfield xpath="@company-id"/>    
    </dbindex>    

    <key name="companyEmail">      
      <keyfield xpath="@email"/>      
      <keyfield xpath="@company-id"/>    
    </key>

    <attribute desc="Email address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>
    <element label="Company" name="company" revLink="recipient" target="sfa:company" type="link">      
      <join xpath-dst="@id" xpath-src="@company-id"/>    
    </element>    
    <attribute advanced="true" label="Foreign key of link 'Company' (field 'id')" name="company-id" sqlname="iCompanyId" type="long"/>
  </element>
</schema>
```

&quot;companyEmail&quot; 이름 키의 정의가 &quot;company&quot; 링크의 외래 키로 확장되었습니다. 이 키는 두 필드 모두에서 고유한 색인을 생성합니다.