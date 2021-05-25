---
solution: Campaign v8
product: Adobe Campaign
title: Campaign 상호 작용 연산자
description: 오퍼 관리 운영자 만들기
feature: 개요
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 1%

---

# 라이브 및 디자인 환경{#live-design-environments}

상호 작용은 다음 두 가지 유형의 오퍼 환경에서 작동합니다.

* **[!UICONTROL Design]** 편집 중이며 변경할 수 있는 오퍼를 포함하는 오퍼 환경을 제공합니다. 이 오퍼는 승인 주기를 거치지 않았고 연락처에 배달되지 않았습니다.
* **[!UICONTROL Live]** 연락처에 표시될 때 승인된 오퍼를 포함하는 환경을 제공합니다. 이 환경의 오퍼는 읽기 전용입니다.

![](assets/offer_environments_overview_001.png)

각 **[!UICONTROL Design]** 환경은 **[!UICONTROL Live]** 환경에 연결됩니다. 오퍼가 완료되면 해당 컨텐츠 및 자격 규칙은 승인 주기에 적용됩니다. 이 주기가 완료되면 관련 오퍼가 자동으로 **[!UICONTROL Live]** 환경에 배포됩니다. 지금부터 배송이 가능합니다

기본적으로 Campaign에는 **[!UICONTROL Design]** 환경과 **[!UICONTROL Live]** 환경이 연결되어 있습니다. 두 환경 모두 [기본 제공 수신자 테이블](../dev/datamodel.md#ootb-profiles)을(를) 타겟팅하도록 사전 구성되어 있습니다.

>[!NOTE]
>
>수신자 테이블을 타깃팅하려면 대상 매핑 도우미를 사용하여 환경을 만들어야 합니다. [자세히 알아보기](#creating-an-offer-environment)

![](assets/offer_environments_overview_002.png)

게재 관리자는 **[!UICONTROL Live]** 환경만 보고 오퍼를 활용하여 게재할 수 있습니다. 오퍼 관리자는 **[!UICONTROL Design]** 환경을 보고 사용할 수 있으며, **[!UICONTROL Live]** 환경을 볼 수 있습니다. [자세히 알아보기](interaction-operators.md)

## 오퍼 환경 만들기 {#creating-an-offer-environment}

기본적으로 Campaign에는 수신자 테이블(식별된 오퍼)을 타겟팅하는 내장 환경이 포함되어 있습니다. 다른 테이블을 타겟팅하려면 아래 단계를 수행하십시오.

1. **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]** 로 이동하여 사용할 대상 매핑을 마우스 오른쪽 단추로 클릭하고 **[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**&#x200B;를 선택합니다.

   ![](assets/offer_env_anonymous_001.png)

1. **[!UICONTROL Next]** 을 클릭하고 **[!UICONTROL Generate a storage schema for propositions]** 옵션을 선택한 다음 **[!UICONTROL Save]** 를 클릭합니다.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >옵션이 이미 선택되어 있다면 선택을 취소하고 다시 확인합니다.

1. Adobe Campaign은 이전에 활성화된 대상 매핑의 타깃팅 정보를 사용하여 **[!UICONTROL Design]** 과 **[!UICONTROL Live]** 라는 두 개의 환경을 만듭니다. 환경은 타깃팅 정보로 미리 구성되어 있습니다.
