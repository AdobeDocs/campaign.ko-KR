---
title: Campaign 스키마로 작업
description: 스키마 시작
exl-id: 87af72fe-6c84-4d9a-afed-015900890cce
source-git-commit: 355b9219ffd9d481d15d2d0982d49923842cc27b
workflow-type: tm+mt
source-wordcount: '1266'
ht-degree: 5%

---

# 스키마 작업{#gs-ac-schemas}

애플리케이션에 포함된 데이터의 물리적 및 논리적 구조는 XML에 설명되어 있습니다. 이것은 Adobe Campaign에 특정된 문법을 따르는데, **스키마**.

스키마는 데이터베이스 테이블과 연결된 XML 문서입니다. 데이터 구조를 정의하고 테이블의 SQL 정의를 설명합니다.

* 테이블의 이름
* 필드
* 다른 테이블과 링크

또한 데이터를 저장하는 데 사용되는 XML 구조에 대해 설명합니다.

* 요소 및 속성
* 요소 계층
* 요소 및 속성 유형
* 기본값
* 레이블, 설명 및 기타 속성입니다.

스키마를 사용하여 데이터베이스에서 엔티티를 정의할 수 있습니다. 각 엔티티에 대한 스키마가 있습니다.

Adobe Campaign은 데이터 스키마를 사용하여 다음을 수행합니다.

* 응용 프로그램 내의 데이터 개체가 기본 데이터베이스 테이블에 연결되어 있는 방식을 정의합니다.
* Campaign 애플리케이션 내에서 서로 다른 데이터 개체 간의 링크를 정의합니다.
* 각 개체에 포함된 개별 필드를 정의하고 설명합니다.

Campaign 기본 제공 테이블 및 상호 작용에 대해 더 잘 이해하려면 다음을 참조하십시오 [이 섹션](datamodel.md).

>[!CAUTION]
>
>일부 기본 제공 Campaign 스키마에는 클라우드 데이터베이스에 연관된 스키마가 있습니다. 이러한 스키마는 **Xxl** 네임스페이스이며 수정하거나 확장할 수 없습니다.

## 스키마 구문 {#syntax-of-schemas}

스키마의 루트 요소는 다음과 같습니다 **`<srcschema>`**. 여기에는 다음 항목이 포함되어 있습니다 **`<element>`** 및 **`<attribute>`** 하위 요소를 생성하지 않습니다.

첫 번째 **`<element>`** 하위 요소는 엔티티의 루트와 일치합니다.

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">  
    <attribute name="lastName"/>
    <attribute name="email"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

>[!NOTE]
>
>엔티티의 루트 요소의 이름이 스키마와 같습니다.

![](assets/schema_and_entity.png)

다음 **`<element>`** 태그는 엔티티 요소의 이름을 정의합니다. **`<attribute>`** 스키마의 태그는 **`<element>`** 태그가 연결된 태그.

## 스키마 식별 {#identification-of-a-schema}

데이터 스키마는 해당 이름 및 네임스페이스로 식별됩니다.

네임스페이스를 사용하면 일련의 스키마를 관심 영역별로 그룹화할 수 있습니다. 예: **cus** 네임스페이스가 고객별 구성에 사용됩니다(**고객**).

>[!CAUTION]
>
>일반적으로 네임스페이스의 이름은 간결한 것이어야 하며 XML 이름 지정 규칙에 따라 인증된 문자만 포함해야 합니다.
>
>식별자는 숫자 문자로 시작하면 안 됩니다.

## 예약된 네임스페이스 {#reserved-namespaces}

특정 네임스페이스는 Adobe Campaign 애플리케이션 작업에 필요한 시스템 엔터티에 대한 설명을 위해 예약되어 있습니다. 다음 네임스페이스 **를 사용하지 않아야 합니다.** 새 스키마를 식별하려면 다음 상위/하위 사례 조합에서 다음을 수행합니다.

* **xxl**: 클라우드 데이터베이스 스키마에 예약됨
* **xtk**: 플랫폼 시스템 데이터로 예약됨
* **nl**: 애플리케이션의 전체 사용에 예약됨
* **nms**: 게재에 예약됨(수신자, 게재, 추적 등)
* **ncm**: 콘텐츠 관리에 예약됨
* **임시**: 임시 스키마에 예약됨
* **crm**: crm 커넥터 통합에 예약됨

스키마의 ID 키는 네임스페이스와 콜론으로 구분하여 이름을 사용하여 작성된 문자열입니다. 예: **nms:recipient**.

## Campaign 스키마 만들기 또는 확장 {#create-or-extend-schemas}

수신자 테이블(nms:recipient)과 같은 Campaign의 핵심 데이터 스키마 중 하나에 필드나 다른 요소를 추가하려면 해당 스키마를 확장해야 합니다.

![](../assets/do-not-localize/glass.png) 자세한 내용은 [스키마 확장](extend-schema.md).

Adobe Campaign(예: 계약 테이블)에 존재하지 않는 완전히 새로운 유형의 데이터를 추가하려면 사용자 지정 스키마를 직접 생성할 수 있습니다.

![](../assets/do-not-localize/glass.png) 자세한 내용은 [새 스키마 만들기](create-schema.md).

![](assets/schemaextension_1.png)


작업할 스키마를 만들거나 확장하면, 다음과 같은 순서로 XML 콘텐츠 요소를 정의하는 것이 좋습니다.

## 열거형 {#enumerations}

열거형은 스키마의 기본 요소 앞에 먼저 정의됩니다. 이 필드를 사용하면 사용자가 주어진 필드에 대해 갖는 선택 사항을 제한하기 위해 목록에 값을 표시할 수 있습니다.

예제:

```
<enumeration basetype="byte" name="exTransactionTypeEnum" default="store">
<value label="Website" name="web" value="0"/>
<value label="Call Center" name="phone" value="1"/>
<value label="In Store" name="store" value="2"/>
</enumeration>
```

그런 다음 필드를 정의할 때 다음과 같이 이 열거형을 사용할 수 있습니다.

```
<attribute desc="Type of Transaction" label="Transaction Type" name="transactionType" 
type="string" enum="exTransactionTypeEnum"/>
```

>[!NOTE]
>
>사용자 관리 열거형(일반적으로 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** ) 를 사용하여 주어진 필드에 대한 값을 지정합니다. 이러한 열거형은 효과적으로 전역 열거형이며, 작업 중인 특정 스키마 외부에서 열거형을 사용할 수 있는 경우 더 나은 선택입니다.

<!--
## Index {#index} 

In the context of a [FDA Snowflake deployment](../architecture/fda-deployment.md), you need to declare indexes. Indexes are the first elements declared in the main element of the schema. 

They can be unique or not, and reference one or more fields.

Examples:

```
<dbindex name="email" unique="true">
  <keyfield xpath="@email"/>
</dbindex>
```

```
<dbindex name="lastNameAndZip">
  <keyfield xpath="@lastName"/>
  <keyfield xpath="location/@zipCode"/>
</dbindex>
```

The **xpath** attribute points to the field in your schema that you wish to index.

>[!IMPORTANT]
>
>It is important to remember that the SQL query read performance gains provided by indexes also come with a performance hit on writing records. The indexes should therefore be used with precaution.

For more on indexes, refer to the [Indexed fields](database-mapping.md#indexed-fields) section.

-->

## 키 {#keys}

모든 테이블에는 하나 이상의 키가 있어야 하며, 종종 를 사용하여 스키마의 기본 요소에 자동으로 설정됩니다 **자동** 속성 설정 **true**.

또한 [엔터프라이즈(FFDA) 배포](../architecture/enterprise-deployment.md)를 사용하려면 **@autouuid** 다음으로 설정 **true**.

기본 키는 **내부** 속성을 사용합니다.

예제:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

이 예에서 **@autopk** 또는 **@autouuid** 속성은 &quot;id&quot;라는 기본 기본 기본 키를 만듭니다. 우리는 고유한 &quot;houseid&quot; 기본 키를 지정하고 있습니다.

>[!CAUTION]
>
>새 스키마를 만들거나 스키마 확장 중에 전체 스키마에 대해 동일한 기본 키 시퀀스 값(@pkSequence)을 유지해야 합니다.

![](../assets/do-not-localize/glass.png) 의 키에 대해 자세히 알아보기 [이 섹션](database-mapping.md#management-of-keys).

## 속성(필드) {#attributes--fields-}

속성을 사용하면 데이터 개체를 구성하는 필드를 정의할 수 있습니다. 를 사용할 수 있습니다 **[!UICONTROL Insert]** 스키마 편집 도구 모음의 단추를 눌러 빈 속성 템플릿을 커서가 있는 XML에 놓습니다. 추가 정보 [이 섹션](create-schema.md).

![](assets/schemaextension_2.png)

전체 속성 목록은 `<attribute>` 요소 섹션 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=en#content-model). 다음은 보다 일반적으로 사용되는 속성 중 일부입니다. **@advanced**, **@dataPolicy**, **@default**, **@desc**, **@enum**, **@expr**, **@label**, **@length**, **@name**, **@notNull**, **@required**, **@ref**, **@xml**, **@type**.

![](../assets/do-not-localize/book.png) 각 속성에 대한 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic).

### 예제 {#examples}

기본값 정의 예:

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

공통 속성을 필수로 표시된 필드의 템플릿으로 사용하는 예:

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

을 사용하여 숨겨진 계산된 필드의 예 **@advanced** attribute:

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

SQL 필드에 저장되고 XML 필드의 예로서 **@dataPolicy** 속성을 사용합니다.

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>대부분의 특성이 데이터베이스의 물리적 필드에 1-1 카디널리티에 따라 연결되어 있지만 XML 필드나 계산된 필드의 경우에는 그렇지 않습니다.\
>XML 필드는 테이블의 메모 필드(&quot;mData&quot;)에 저장됩니다.\
>그러나 계산 필드는 쿼리가 시작될 때마다 동적으로 만들어지므로 응용 프로그램 계층에만 있습니다.

## 링크 {#links}

링크는 스키마의 기본 요소에 있는 마지막 요소 중 일부입니다. 인스턴스에 있는 여러 스키마가 서로 관련되는 방식을 정의합니다.

링크는 를 포함하는 스키마에서 선언됩니다 **외래 키** 연결된 테이블의

카디널리티는 다음 세 가지 유형이 있습니다. 1-1, 1-N 및 N-N 기본적으로 사용되는 1-N 유형입니다.

### 예제 {#examples-1}

수신자 테이블(기본 스키마)과 사용자 지정 트랜잭션 테이블 간 1-N 링크의 예:

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

사용자 지정 스키마 &quot;Car&quot;(&quot;cus&quot; 네임스페이스에서)와 수신자 테이블 간의 1-1 링크의 예:

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

수신자 테이블과 기본 키가 아닌 전자 메일 주소를 기반으로 하는 주소 테이블 간의 외부 조인의 예:

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

여기서 &quot;xpath-dst&quot;는 대상 스키마의 기본 키에 해당하고 &quot;xpath-src&quot;는 소스 스키마의 외부 키에 해당합니다.

## 감사 추적 {#audit-trail}

스키마 하단에 포함할 수 있는 유용한 요소 중 하나는 추적 요소(감사 추적)입니다.

아래 예를 사용하여 테이블의 모든 데이터에 대해 생성 날짜, 데이터를 생성한 사용자, 날짜 및 마지막으로 수정한 작성자와 관련된 필드를 포함할 수 있습니다.

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## 데이터베이스 구조 업데이트 {#updating-the-database-structure}

변경 사항이 완료되고 저장되면 SQL 구조에 영향을 줄 수 있는 모든 변경 사항을 데이터베이스에 적용해야 합니다. 이렇게 하려면 데이터베이스 업데이트 도우미를 사용합니다.

![](assets/schemaextension_3.png)

이 작업에 대한 자세한 정보는 [이 섹션](update-database-structure.md)을 참조하십시오.

>[!NOTE]
>
>수정 사항이 데이터베이스 구조에 영향을 주지 않는 경우 스키마를 다시 생성하기만 하면 됩니다. 이렇게 하려면 업데이트할 스키마를 선택하고 마우스 오른쪽 버튼을 클릭한 다음 을(를) 선택합니다 **[!UICONTROL Actions > Regenerate selected schemas...]** .
