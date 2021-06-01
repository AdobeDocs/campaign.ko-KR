---
product: Adobe Campaign
title: PI 보기 제한
description: PI 보기를 제한하는 방법 알아보기
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---

# PI 보기 제한{#restricting-pii-view}

## 개요 {#overview}

마케팅 사용자가 데이터 레코드에 액세스할 수 있어야 하지만 개인 이름, 성 또는 이메일 주소와 같은 수신자 개인 정보(API)를 보지 않으려는 경우 아래 지침을 적용하여 개인 정보를 보호하고 일반 캠페인 운영자가 데이터를 잘못 사용하지 않도록 하십시오.

## 구현 {#implementation}

요소나 속성에 적용할 수 있는 특정 속성이 스키마에 추가되어 기존 속성 **[!UICONTROL visibleIf]** 을 보완합니다. 이 속성은 다음과 같습니다.**[!UICONTROL accessibleIf]** . 현재 사용자 컨텍스트와 관련된 XTK 표현식을 포함하는 경우 예를 들어 **[!UICONTROL HasNamedRight]** 또는 **[!UICONTROL $(login)]** 을 활용할 수 있습니다.

수신인 스키마 확장의 샘플은 이러한 사용을 아래에 보여 줍니다.

```
<srcSchema desc="Recipient table (profiles" entitySchema="xtk:srcSchema" extendedSchema="xxl:nmsRecipientXl"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient"
           name="recipient" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Recipient table (profiles" img="xxl:recipient.png" label="Recipients"
           labelSingular="Recipient" name="recipient">
    <attribute name="firstName" accessibleIf="$(login)=='admin'"/>
    <attribute name="lastName" visibleIf="$(login)=='admin'"/>
    <attribute name="email" accessibleIf="$(login)=='admin'"/>
  </element>
</srcSchema>
```

기본 속성은 다음과 같습니다.

* **[!UICONTROL visibleIf]** :는 메타데이터에서 필드를 숨기므로 스키마 보기, 열 선택 또는 표현식 빌더 내에서 액세스할 수 없습니다. 하지만 이렇게 해도 데이터가 숨기지 않고, 필드 이름을 표현식에 수동으로 입력하면 값이 표시됩니다.
* **[!UICONTROL accessibleIf]** :결과 쿼리의 데이터를 숨깁니다(빈 값으로 바꾸기). visibleIf 가 비어 있으면 **[!UICONTROL accessibleIf]** 과 동일한 표현식을 받게 됩니다.

다음은 Campaign에서 이 속성을 사용할 때의 결과입니다.

* 콘솔에서 일반 쿼리 편집기를 사용하여 데이터가 표시되지 않습니다.
* 데이터는 개요 목록 및 레코드 목록(콘솔)에 표시되지 않습니다.
* 데이터는 세부 보기에서 읽기 전용이 됩니다.
* 데이터는 필터 내에서만 사용할 수 있습니다(즉, 일부 이분법 전략을 사용하여 값을 추측할 수 있음).
* 제한된 필드를 사용하여 빌드된 모든 표현식은 다음과 같이 제한됩니다.lower(@email)은 가능한 @email.
* 워크플로우에서 타겟팅된 모집단에 제한된 열을 전환의 추가 열로 추가할 수 있지만 Adobe Campaign 사용자는 여전히 액세스할 수 없습니다.
* 대상 모집단을 그룹(목록)에 저장할 때 저장된 필드의 특성은 데이터 소스와 동일합니다.
* 기본적으로 데이터는 JS 코드에 액세스할 수 없습니다.

## Recommendations {#recommendations}

각 게재에서 이메일 주소는 **[!UICONTROL broadLog]** 및 **[!UICONTROL forecastLog]** 테이블에 복사됩니다.따라서 이러한 필드도 보호해야 합니다.

다음은 이를 구현하는 로그 테이블 확장 샘플입니다.

```
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:broadLogRcp" img="nms:broadLog.png"
           label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:broadLog.png" label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema desc="Delivery messages being prepared." entitySchema="xtk:srcSchema"
           extendedSchema="nms:tmpBroadcast" img="" label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Delivery messages being prepared." label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:excludeLogRcp" img="nms:excludeLog.png"
           label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:excludeLog.png" label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
```

>[!CAUTION]
>
>이 제한 사항은 기술 전문가가 아닌 사용자에게만 적용되며 데이터를 격리하지 않습니다.관련 권한이 있는 기술 사용자는 데이터를 검색할 수 있습니다.
