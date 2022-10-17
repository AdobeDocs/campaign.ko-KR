---
title: Adobe Experience Cloud 솔루션과 대상 공유
description: Adobe Experience Cloud 솔루션과 대상을 공유하는 방법을 알아봅니다
feature: Subscriptions
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: ec46a6f41d640b11306a88d6a966f81f8c2e43e0
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 5%

---

# Adobe Experience Cloud 솔루션과 대상 공유{#shared-audiences}


옵션 1: AEP 소스 및 대상

옵션 2: Adobe 사람/AAM

통합할 수 있습니다 **Adobe Campaign** with **사용자 핵심 서비스** 또는 Adobe Audience Manager. 그런 다음 다음을 수행할 수 있습니다.

* 다른 Adobe Experience Cloud 솔루션의 공유 대상/세그먼트를 Adobe Campaign에 가져옵니다. Adobe Campaign의 목록을 통해 대상을 가져올 수 있습니다.

* Adobe Experience Cloud 공유 대상자 형태로 목록을 내보냅니다. 이러한 대상은 사용하는 다양한 Adobe Experience Cloud 솔루션에서 사용할 수 있습니다. 워크플로우에서 타겟팅 후 전용 을 사용하여 대상을 내보낼 수 있습니다 **[!UICONTROL Update shared audience]** 활동.

이 통합은 두 가지 유형의 Adobe Experience Cloud ID를 지원합니다.

* **방문자 ID**: 이 유형의 식별자는 Adobe Experience Cloud 방문자를 Adobe Campaign 수신자와 조정합니다.
* **선언된 ID**: 이 유형의 식별자는 모든 유형의 데이터를 Adobe Campaign 데이터베이스의 요소와 조정합니다. 이 키는 Adobe Campaign에 사전 정의된 조정 키로 표시됩니다.

   >[!NOTE]
   >
   > 선언된 ID 데이터 소스는 People 핵심 서비스 통합에도 사용할 수 있습니다.
   >
   >People 핵심 서비스 통합을 사용하고 있으며 Audience Manager 통합을 추가하려면 Adobe Audience Manager 컨텍스트에서 선언된 ID 데이터 소스를 사용하여 전환할 때 수집된 모든 ID 동기화를 유실하지 않도록 Adobe Audience Manager 컨설턴트의 도움이 필요합니다.

보기:

[https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=en](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=en)

[https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=en](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=en)
