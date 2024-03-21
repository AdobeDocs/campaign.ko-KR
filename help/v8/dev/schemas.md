---
title: Campaign 스키마 작업
description: 스키마 시작하기
feature: Schema Extension, Configuration, Data Model
role: Developer
level: Intermediate, Experienced
exl-id: 87af72fe-6c84-4d9a-afed-015900890cce
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 5%

---

# 스키마 작업{#gs-ac-schemas}

애플리케이션에 포함된 데이터의 물리적 및 논리적 구조는 XML에 설명되어 있습니다. 라고 하는 Adobe Campaign 고유의 문법을 따릅니다. **스키마**.

스키마는 데이터베이스 테이블과 연관된 XML 문서입니다. 데이터 구조를 정의하고 테이블의 SQL 정의를 설명합니다.

* 테이블 이름
* 필드
* 다른 테이블과의 링크

또한 데이터를 저장하는 데 사용되는 XML 구조에 대해서도 설명합니다.

* 요소 및 속성
* 요소의 계층
* 요소 및 속성 유형
* 기본값
* 레이블, 설명 및 기타 등록 정보.

스키마를 사용하면 데이터베이스에서 엔티티를 정의할 수 있습니다. 각 엔티티에 대한 스키마가 있습니다.

Adobe Campaign은 데이터 스키마를 사용하여 다음을 수행합니다.

* 응용 프로그램 내의 데이터 개체가 기본 데이터베이스 테이블에 연결되는 방식을 정의합니다.
* Campaign 애플리케이션 내에서 서로 다른 데이터 개체 간의 링크를 정의합니다.
* 각 개체에 포함된 개별 필드를 정의하고 설명합니다.

Campaign 기본 제공 테이블과 상호 작용에 대한 자세한 내용은 을(를) 참조하십시오. [이 섹션](datamodel.md).

>[!CAUTION]
>
>일부 기본 제공 Campaign 스키마에는 클라우드 데이터베이스에 연결된 스키마가 있습니다. 이러한 스키마는 **Xxl** 네임스페이스이며, 수정하거나 확장해서는 안 됩니다.

## 스키마 구문 {#syntax-of-schemas}

스키마의 루트 요소는 **`<srcschema>`**. 여기에는 **`<element>`** 및 **`<attribute>`** 하위 요소.

첫 번째 **`<element>`** 하위 요소는 엔티티 루트와 일치합니다.

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
>엔티티의 루트 요소는 스키마와 동일한 이름을 갖습니다.

![](assets/schema_and_entity.png)

다음 **`<element>`** 태그는 엔티티 요소의 이름을 정의합니다. **`<attribute>`** 스키마 태그는 의 속성 이름을 정의합니다. **`<element>`** 태그가 연결되어 있습니다.

## 스키마 식별 {#identification-of-a-schema}

데이터 스키마는 이름 및 네임스페이스로 식별됩니다.

네임스페이스를 사용하면 관심 영역별로 스키마 세트를 그룹화할 수 있습니다. 예를 들어 **cus** 네임스페이스는 고객별 구성(**고객**).

>[!CAUTION]
>
>기본적으로 네임스페이스 이름은 간결해야 하며 XML 이름 지정 규칙에 따라 승인된 문자만 포함해야 합니다.
>
>식별자는 숫자로 시작할 수 없습니다.

## 예약된 네임스페이스 {#reserved-namespaces}

특정 네임스페이스는 Adobe Campaign 애플리케이션 작업에 필요한 시스템 엔터티의 설명을 위해 예약되어 있습니다. 다음 네임스페이스 **은(는) 을(를) 사용할 수 없습니다.** 대문자/소문자 조합에서 새 스키마를 식별하려면 다음을 수행하십시오.

* **xxl**: 클라우드 데이터베이스 스키마에 예약됨
* **xtk**: 플랫폼 시스템 데이터에 예약됨
* **nl**: 애플리케이션의 전체 사용을 위해 예약됨
* **nms**: 게재(수신자, 게재, 추적 등)에 예약됨
* **ncm**: 콘텐츠 관리에 예약됨
* **임시**: 임시 스키마에 예약됨
* **crm**: CRM 커넥터 통합에 예약됨

스키마의 식별 키는 네임스페이스와 콜론으로 구분된 이름을 사용하여 빌드된 문자열입니다. 예: **nms:recipient**.

## Campaign 스키마 만들기 또는 확장 {#create-or-extend-schemas}

수신자 테이블(nms:recipient)과 같이, Campaign의 핵심 데이터 스키마 중 하나에 필드나 다른 요소를 추가하려면 해당 스키마를 확장해야 합니다.

자세한 내용은 다음을 참조하십시오. [스키마 확장](extend-schema.md).

Adobe Campaign에 존재하지 않는 완전히 새로운 유형의 데이터(예: 계약 테이블)를 추가하려면 사용자 지정 스키마를 직접 만들 수 있습니다.

자세한 내용은 다음을 참조하십시오. [새 스키마 만들기](create-schema.md).

![](assets/schemaextension_1.png)


작업할 스키마를 만들거나 확장한 후에는 아래에 표시된 것과 동일한 순서로 해당 XML 콘텐츠 요소를 정의하는 것이 가장 좋습니다.

## 열거형 {#enumerations}

먼저 스키마의 주 요소 앞에 열거형을 정의합니다. 값을 목록에 표시하여 주어진 필드에 대해 사용자가 선택할 수 있는 사항을 제한할 수 있습니다.

예:

```
<enumeration basetype="byte" name="exTransactionTypeEnum" default="store">
<value label="Website" name="web" value="0"/>
<value label="Call Center" name="phone" value="1"/>
<value label="In Store" name="store" value="2"/>
</enumeration>
```

필드를 정의할 때 다음과 같이 이 열거형을 사용할 수 있습니다.

```
<attribute desc="Type of Transaction" label="Transaction Type" name="transactionType" 
type="string" enum="exTransactionTypeEnum"/>
```

>[!NOTE]
>
>사용자 관리 열거형을 사용할 수도 있습니다(일반적으로 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** )을 클릭하여 특정 필드의 값을 지정합니다. 이러한 열거형은 효과적으로 전역 열거형이며, 작업 중인 특정 스키마 외부에서 열거형을 사용할 수 있는 경우 더 나은 선택입니다.

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

모든 테이블에는 하나 이상의 키가 있어야 하며, 종종 를 사용하여 스키마의 기본 요소에 자동으로 설정됩니다. **autopk** 속성이 로 설정됨 **true**.

또한 의 컨텍스트에서 [엔터프라이즈(FFDA) 배포](../architecture/enterprise-deployment.md), 사용 **@autouuid** 및 설정 **true**.

기본 키는 다음을 사용하여 정의할 수도 있습니다. **내부** 특성.

예:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

이 예제에서는 를 허용하는 대신 **@autopk** 또는 **@autouuid** attribute 고유한 &quot;householdId&quot; 기본 키를 지정하는 &quot;id&quot;라는 기본 기본 키를 만듭니다.

>[!CAUTION]
>
>새 스키마를 생성하거나 스키마 확장 중에 전체 스키마에 대해 동일한 기본 키 시퀀스 값(@pkSequence)을 유지해야 합니다.

의 키에 대해 자세히 알아보기 [이 섹션](database-mapping.md#management-of-keys).

## 속성(필드) {#attributes--fields-}

속성을 사용하면 데이터 개체를 구성하는 필드를 정의할 수 있습니다. 다음을 사용할 수 있습니다. **[!UICONTROL Insert]** 빈 속성 템플릿을 커서가 있는 XML에 끌어 놓기 위한 스키마 편집 도구 모음의 단추입니다. [이 섹션](create-schema.md)에서 자세히 알아보십시오.

![](assets/schemaextension_2.png)

속성의 전체 목록은 `<attribute>` 의 요소 섹션 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html#content-model). 다음은 가장 일반적으로 사용되는 속성 중 일부입니다. **@advanced**, **@dataPolicy**, **@default**, **@desc**, **@enum**, **@expr**, **@label**, **@length**, **@name**, **@notNull**, **@required**, **@ref**, **@xml**, **@type**.

각 속성에 대한 자세한 내용은 의 속성 설명을 참조하십시오 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html#configuring-campaign-classic).

### 예제 {#examples}

기본값을 정의하는 예:

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

필수로 표시된 필드의 템플릿으로 공통 속성을 사용하는 예:

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

를 사용하여 숨겨진 계산된 필드의 예 **@advanced** 특성:

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

SQL 필드에 저장되며 **@dataPolicy** 특성.

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>대부분의 속성은 데이터베이스의 실제 필드에 1-1 카디널리티에 따라 연결되어 있지만 XML 필드 또는 계산된 필드의 경우에는 그렇지 않습니다.\
>XML 필드는 테이블의 메모 필드(&quot;mData&quot;)에 저장됩니다.\
>그러나 계산된 필드는 쿼리가 시작될 때마다 동적으로 생성되므로 응용 프로그램 레이어에만 존재합니다.

## 링크 {#links}

링크는 스키마의 기본 요소에 있는 마지막 요소 중 일부입니다. 인스턴스의 모든 스키마가 서로 관련되는 방식을 정의합니다.

링크는 를 포함하는 스키마에서 선언됩니다. **외래 키** 연결된 테이블의

카디널리티에는 1-1, 1-N, N-N의 세 가지 유형이 있습니다. 기본적으로 사용되는 1-N 유형입니다.

### 예제 {#examples-1}

수신자 테이블(기본 스키마)과 사용자 지정 트랜잭션 테이블 간의 1-N 링크의 예는 다음과 같습니다.

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

사용자 지정 스키마 &quot;Car&quot;(&quot;cus&quot; 네임스페이스)와 수신자 테이블 간의 1-1 링크의 예:

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

기본 키가 아닌 이메일 주소를 기반으로 수신자 테이블과 주소 테이블 간의 외부 조인 예:

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

여기서 &quot;xpath-dst&quot;는 대상 스키마의 기본 키에 해당하고 &quot;xpath-src&quot;는 소스 스키마의 외래 키에 해당합니다.

## 감사 추적 {#audit-trail}

스키마 하단에 포함할 수 있는 한 가지 유용한 요소는 추적 요소(감사 추적)입니다.

아래 예를 사용하여 생성 날짜, 데이터를 생성한 사용자, 날짜 및 테이블의 모든 데이터에 대한 마지막 수정 작성자와 관련된 필드를 포함할 수 있습니다.

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## 데이터베이스 구조 업데이트 {#updating-the-database-structure}

변경 사항이 완료되고 저장되면 SQL 구조에 영향을 줄 수 있는 모든 변경 사항을 데이터베이스에 적용해야 합니다. 이렇게 하려면 Database Update Assistant를 사용합니다.

![](assets/schemaextension_3.png)

이 작업에 대한 자세한 정보는 [이 섹션](update-database-structure.md)을 참조하십시오.

>[!NOTE]
>
>수정 사항이 데이터베이스 구조에 영향을 주지 않으면 스키마만 재생성하면 됩니다. 이렇게 하려면 업데이트할 스키마를 선택하고 마우스 오른쪽 버튼을 클릭한 다음 을(를) 선택합니다 **[!UICONTROL Actions > Regenerate selected schemas...]**.
