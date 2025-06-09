---
title: Campaign 데이터베이스 매핑
description: Campaign 데이터베이스 매핑
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: a804d164-58bf-4b15-a48e-8cf75d793668
source-git-commit: 673298a60927902bba71fd9167c5408e538f4929
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---

# 데이터베이스 매핑{#database-mapping}

예제 스키마의 SQL 매핑은 다음 XML 문서를 제공합니다.

```sql
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

스키마의 루트 요소가 더 이상 **`<srcschema>`**&#x200B;이(가) 아닌 **`<schema>`**&#x200B;입니다.

이를 통해 소스 스키마에서 자동으로 생성되는 다른 유형의 문서(간단히 스키마라고 함)로 이동합니다. 이 스키마는 Adobe Campaign 애플리케이션에서 사용됩니다.

SQL 이름은 요소 이름과 유형에 따라 자동으로 결정됩니다.

SQL 이름 지정 규칙은 다음과 같습니다.

* 표: 스키마 네임스페이스 및 이름의 연결

  이 예제에서 테이블 이름은 **sqltable** 특성에 있는 스키마의 main 요소를 통해 입력됩니다.

  ```sql
  <element name="recipient" sqltable="CusRecipient">
  ```

* 필드: 유형에 따라 정의된 접두사가 앞에 오는 요소의 이름(정수는 &#39;i&#39;, double은 &#39;d&#39;, 문자열은 &#39;s&#39;, 날짜는 &#39;ts&#39; 등)

  입력한 각 **`<attribute>`** 및 **`<element>`**&#x200B;에 대해 **sqlname** 특성을 통해 필드 이름을 입력합니다.

  ```sql
  <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
  ```

>[!NOTE]
>
>소스 스키마에서 SQL 이름을 오버로드할 수 있습니다. 이렇게 하려면 관련 요소에서 &quot;sqltable&quot; 또는 &quot;sqlname&quot; 특성을 채웁니다.

확장 스키마에서 생성된 테이블을 생성하는 SQL 스크립트는 다음과 같습니다.

```sql
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

SQL 필드 제약 조건은 다음과 같습니다.

* 숫자 및 날짜 필드에 null 값이 없음
* 숫자 필드는 0으로 초기화됩니다.

## XML 필드 {#xml-fields}

기본적으로 형식화된 **`<attribute>`** 및 **`<element>`** 요소는 데이터 스키마 테이블의 SQL 필드에 매핑됩니다. 그러나 SQL 대신 XML로 이 필드를 참조할 수 있습니다. 즉, 모든 XML 필드의 값이 들어 있는 테이블의 메모 필드(&quot;mData&quot;)에 데이터가 저장됩니다. 이러한 데이터의 저장소는 스키마 구조를 관찰하는 XML 문서입니다.

XML의 필드를 채우려면 값이 &quot;true&quot;인 **xml** 특성을 관련 요소에 추가해야 합니다.

**예제**

* 여러 줄 주석 필드:

  ```sql
  <element name="comment" xml="true" type="memo" label="Comment"/>
  ```

* HTML 형식의 데이터 설명:

  ```sql
  <element name="description" xml="true" type="html" label="Description"/>
  ```

  html 유형을 사용하면 HTML 콘텐츠를 CDATA 태그에 저장하고 Adobe Campaign 클라이언트 인터페이스에 특별한 HTML 편집 확인을 표시할 수 있습니다.

XML 필드를 사용하면 데이터베이스의 물리적 구조를 수정할 필요 없이 필드를 추가할 수 있습니다. 또 다른 장점은 리소스(SQL 필드에 할당된 크기, 테이블당 필드 수 제한 등)를 적게 사용한다는 것입니다.
