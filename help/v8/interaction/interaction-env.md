---
title: Campaign 상호 작용 환경
description: Campaign 상호 작용을 위한 환경을 만드는 방법을 알아봅니다
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 31f38870-1781-4185-9022-d4fd6a31c94a
source-git-commit: 213a10fea36b3b08c1dd8525084d212e191b2fc7
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 2%

---

# 환경 작업{#work-with-environments}

## 라이브 및 디자인 환경{#live-design-environments}

상호 작용은 다음 두 가지 유형의 오퍼 환경에서 작동합니다.

* **[!UICONTROL Design]** 편집 중이며 변경할 수 있는 오퍼를 포함하는 오퍼 환경을 제공합니다. 이 오퍼는 승인 주기를 거치지 않았고 연락처에 배달되지 않았습니다.
* **[!UICONTROL Live]** 연락처에 표시될 때 승인된 오퍼를 포함하는 환경을 제공합니다. 이 환경의 오퍼는 읽기 전용입니다.

![](assets/offer_environments_overview_001.png)

각 **[!UICONTROL Design]** 환경이 **[!UICONTROL Live]** 환경. 오퍼가 완료되면 해당 컨텐츠 및 자격 규칙은 승인 주기에 적용됩니다. 이 주기가 완료되면 관련 오퍼가 자동으로 **[!UICONTROL Live]** 환경. 지금부터 배송이 가능합니다

기본적으로 Campaign에는 **[!UICONTROL Design]** 환경 및 **[!UICONTROL Live]** 환경에 연결된 환경. 두 환경은 모두 를 타겟으로 미리 구성되어 있습니다 [기본 제공 수신자 테이블](../dev/datamodel.md#ootb-profiles).

>[!NOTE]
>
>수신자 테이블을 타깃팅하려면 대상 매핑 도우미를 사용하여 환경을 만들어야 합니다. [자세히 알아보기](#creating-an-offer-environment)

![](assets/offer_environments_overview_002.png)

게재 관리자는 **[!UICONTROL Live]** 환경 및 활용 오퍼를 게재할 수 있습니다. 오퍼 관리자는 **[!UICONTROL Design]** 환경 및 보기 **[!UICONTROL Live]** 환경. [자세히 알아보기](interaction-operators.md)

## 익명의 상호 작용을 위한 환경 만들기{#create-an-offer-environment}

기본적으로 Campaign에는 수신자 테이블(식별된 오퍼)을 타겟팅하는 내장 환경이 포함되어 있습니다. 인바운드 상호 작용을 위해 웹 사이트를 방문하는 익명 프로필 등 다른 테이블을 타겟팅하려면 구성을 업데이트해야 합니다.

아래의 단계를 수행하십시오.

1. 찾아보기 **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]**&#x200B;를 클릭하고, 사용할 대상 매핑을 마우스 오른쪽 단추로 클릭하고 를 선택합니다 **[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**.

   ![](assets/offer_env_anonymous_001.png)

1. 클릭 **[!UICONTROL Next]**&#x200B;에서 을(를) 선택합니다. **[!UICONTROL Generate a storage schema for propositions]** 옵션을 선택하고 **[!UICONTROL Save]**.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >옵션이 이미 선택되어 있다면 선택을 취소하고 다시 확인합니다.

1. Adobe Campaign은 두 가지 환경을 만듭니다. **[!UICONTROL Design]** 및 **[!UICONTROL Live]** - 이전에 활성화된 target 매핑의 타깃팅 정보 포함. 환경은 타깃팅 정보로 미리 구성되어 있습니다.

활성화한 경우 **[!UICONTROL Visitor]** 매핑, **[!UICONTROL Environment dedicated to incoming anonymous interactions]** 이 상자는 환경의 **[!UICONTROL General]** 탭.

이 옵션을 사용하면 특히 환경 오퍼 공간을 구성할 때 익명의 상호 작용 특정 기능을 활성화할 수 있습니다. 식별된&quot; 환경에서 &quot;익명&quot; 환경으로 전환할 수 있는 옵션을 구성할 수도 있습니다.

예를 들어, 수신자 환경 오퍼 공간(식별된 연락처)을 방문자 환경(식별되지 않은 연락처)과 일치하는 오퍼 공간과 연결할 수 있습니다. 이러한 방식으로 연락처가 식별되는지 여부에 따라 연락처에서 다른 오퍼를 사용할 수 있습니다. 자세한 내용은 [오퍼 공간 만들기](interaction-offer-spaces.md).

![](assets/offer_env_anonymous_003.png)

>[!NOTE]
>
>인바운드 채널에서 익명의 상호 작용에 대한 자세한 내용은 [익명의 상호 작용](anonymous-interactions.md).
