---
solution: Campaign Classic
product: campaign
title: 캠페인 스키마 사용
description: 스키마 시작하기
translation-type: tm+mt
source-git-commit: 779542ab70f0bf3812358884c698203bab98d1ce
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 6%

---

# 스키마 작업{#gs-ac-schemas}

Adobe Campaign은 데이터 스키마를 사용하여 다음을 수행합니다.

* 애플리케이션 내의 데이터 개체가 기본 데이터베이스 테이블에 연결되어 있는 방식을 정의합니다.
* Campaign 애플리케이션 내에서 서로 다른 데이터 개체 간의 링크를 정의합니다.
* 각 개체에 포함된 개별 필드를 정의하고 설명합니다.

Campaign 내장 테이블 및 그 상호 작용에 대한 자세한 내용은 [이 섹션](datamodel.md)을 참조하십시오.

## 캠페인 스키마 만들기 또는 확장 {#create-or-extend-schemas}

받는 사람 테이블(nms:recipient)과 같은 Campaign의 핵심 데이터 스키마 중 하나에 필드나 다른 요소를 추가하려면 해당 스키마를 확장해야 합니다.

: 전구:자세한 내용은 [스키마 확장](extend-schema.md)을 참조하십시오.

Adobe Campaign에 존재하지 않는 완전히 새로운 유형의 데이터(예: 계약 테이블)를 추가하려면 사용자 정의 스키마를 직접 만들 수 있습니다.

: 전구:자세한 내용은 [새 스키마 만들기](create-schema.md)를 참조하십시오.

![](assets/schemaextension_1.png)

작업하기 위한 스키마를 만들거나 확장한 후에는 아래에 나타나는 것과 동일한 순서로 XML 내용 요소를 정의하는 것이 좋습니다.

## 열거형 {#enumerations}

열거형은 스키마의 주 요소 앞에 먼저 정의됩니다. 사용자가 주어진 필드에 대해 갖는 선택 사항을 제한하기 위해 목록에 값을 표시할 수 있습니다.

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
>사용자 관리 열거형(일반적으로 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** 아래)을 사용하여 지정된 필드의 값을 지정할 수도 있습니다. 이러한 열거형은 효과적으로 전역 열거형이며, 작업 중인 특정 스키마 외부에서 열거형을 사용할 수 있을 경우 더 나은 선택입니다.

## 키 {#keys}

모든 테이블에는 적어도 하나의 키가 있어야 하며, 일반적으로 **@autouuid=true** 특성이 &quot;true&quot;로 설정된 경우 스키마의 기본 요소에 자동으로 설정됩니다.

기본 키는 **internal** 특성을 사용하여 정의할 수도 있습니다.

예제:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

이 예제에서는 **@autouuid** 특성이 &quot;id&quot;라는 기본 기본 기본 키를 만드는 대신 고유한 &quot;houseinId&quot; 기본 키를 지정합니다.

>[!CAUTION]
>
>새 스키마를 만들거나 스키마 확장 중에 전체 스키마에 대해 동일한 기본 키 시퀀스 값(@pkSequence)을 유지해야 합니다.

: 전구:[이 섹션](database-mapping.md#management-of-keys)에서 키에 대해 자세히 알아보십시오.

## 속성(필드) {#attributes--fields-}

속성을 사용하면 데이터 객체를 구성하는 필드를 정의할 수 있습니다. 스키마 에디션 도구 모음의 **[!UICONTROL Insert]** 단추를 사용하여 커서가 있는 XML에 빈 속성 템플릿을 놓을 수 있습니다. [이 섹션](create-schema.md)에서 자세히 알아보십시오.

![](assets/schemaextension_2.png)

속성의 전체 목록은 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=en#content-model) 섹션의 `<attribute>` 요소 섹션에서 사용할 수 있습니다. 다음은 보다 일반적으로 사용되는 속성 중 일부를 설명해 놓은 것입니다.**@advanced**, **@dataPolicy**, **@default**, **@desc**@enum **,**@expr **>,**@label **,** 4/>@length **,**@name **,**@notNull **,**@required **,**@ref **,**@xml&lt;a222 5/>, **@type**.****

:arrow_upper_right:각 속성에 대한 자세한 내용은 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic)의 속성 설명을 참조하십시오.

### 예제 {#examples}

기본값을 정의하는 예:

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

필수로 표시된 필드의 템플릿으로 공통 속성을 사용하는 예:

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

**@advanced** 특성을 사용하여 숨겨진 계산된 필드의 예:

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

SQL 필드에 저장되고 **@dataPolicy** 특성이 있는 XML 필드의 예입니다.

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>대부분의 속성은 데이터베이스의 물리적 필드에 1-1 카디널리티에 따라 연결되어 있지만 XML 필드나 계산된 필드의 경우에는 그렇지 않습니다.\
>XML 필드는 표의 메모 필드(&quot;mData&quot;)에 저장됩니다.\
>그러나 계산된 필드는 쿼리가 시작될 때마다 동적으로 만들어지므로 응용 프로그램 레이어에만 있습니다.

## 링크 {#links}

링크는 스키마의 기본 요소에 있는 마지막 요소 중 일부입니다. 인스턴스의 서로 다른 모든 스키마가 서로 연관되는 방식을 정의합니다.

링크가 연결되어 있는 테이블의 **외래 키**&#x200B;가 포함된 스키마에서 링크가 선언됩니다.

기수 유형은 다음과 같다.1-1, 1-N 및 N-N.기본적으로 사용되는 1-N 유형입니다.

### 예제 {#examples-1}

받는 사람 테이블(기본 스키마)과 사용자 지정 트랜잭션 테이블 간 1-N 링크의 예:

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

사용자 정의 스키마 &quot;Car&quot;(&quot;cus&quot; 네임스페이스)와 받는 사람 테이블 간 1-1 링크의 예:

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

받는 사람 테이블과 기본 키가 아닌 이메일 주소를 기반으로 한 주소 테이블 간의 외부 조인의 예:

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

여기서 &quot;xpath-dst&quot;는 대상 스키마의 기본 키에 해당하고 &quot;xpath-src&quot;는 소스 스키마의 외래 키에 해당합니다.

## 감사 추적 {#audit-trail}

스키마 아래쪽에 포함할 유용한 요소 중 하나는 추적 요소(감사 추적)입니다.

아래 예를 사용하여 작성 날짜, 데이터를 만든 사용자, 날짜 및 테이블의 모든 데이터에 대한 마지막 수정 내용 작성자와 관련된 필드를 포함할 수 있습니다.

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## 데이터베이스 구조 업데이트 {#updating-the-database-structure}

변경 사항이 완료되고 저장되면 SQL 구조에 영향을 줄 수 있는 변경 사항을 데이터베이스에 적용해야 합니다. 이렇게 하려면 데이터베이스 업데이트 도우미를 사용합니다.

![](assets/schemaextension_3.png)

이 작업에 대한 자세한 정보는 [이 섹션](update-database-structure.md)을 참조하십시오.

>[!NOTE]
>
>수정 내용이 데이터베이스 구조에 영향을 주지 않는 경우 스키마를 다시 생성해야 합니다. 업데이트하려면 업데이트할 스키마를 선택하고 마우스 오른쪽 단추를 클릭한 후 **[!UICONTROL Actions > Regenerate selected schemas...]** 을 선택합니다.

