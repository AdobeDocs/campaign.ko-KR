---
title: Adobe Experience Cloud 솔루션으로 대상자 공유
description: Adobe Experience Cloud 솔루션으로 대상자를 공유하는 방법 알아보기
feature: Subscriptions
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: c4d30771-db5e-40be-8af6-50f0fab9f9af
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 100%

---

# Adobe Experience Cloud 솔루션으로 대상자 공유{#shared-audiences}


옵션 1: AEP 소스 및 대상

옵션 2: Adobe People/AAM

**Adobe Campaign**&#x200B;을 **People 핵심 서비스** 또는 Adobe Audience Manager와 통합할 수 있습니다. 그러면 다음을 수행할 수 있습니다:

* 다양한 Adobe Experience Cloud 솔루션의 공유 대상자/세그먼트를 Adobe Campaign으로 가져옵니다. Adobe Campaign의 목록을 통해 대상자를 가져올 수 있습니다.

* Adobe Experience Cloud 공유 대상자 양식으로 목록을 내보냅니다. 이러한 대상자는 사용하고 있는 여러 Adobe Experience Cloud 솔루션에서 사용할 수 있습니다. 대상자는 워크플로우에서 타겟팅한 후 전용 **[!UICONTROL Update shared audience]** 활동을 사용하여 내보낼 수 있습니다.

이 통합은 두 가지 유형의 Adobe Experience Cloud ID를 지원합니다:

* **방문자 ID**: 이 유형의 식별자는 Adobe Experience Cloud 방문자를 Adobe Campaign 수신자와 조정합니다.
* **선언 ID**: 이 유형의 식별자는 모든 유형의 데이터를 Adobe Campaign 데이터베이스의 요소와 조정합니다. Adobe Campaign에서는 사전 정의된 조정 키로 표시됩니다.

  >[!NOTE]
  >
  > 선언된 ID 데이터 소스는 People 핵심 서비스 통합에도 사용할 수 있습니다.
  >
  >People 핵심 서비스 통합을 사용 중이고 Audience Manager 통합을 추가하려면 Adobe Audience Manager 컨설턴트의 도움이 필요합니다. 도움을 통해 Adobe Audience Manage 컨텍스트에서 선언 ID 데이터 소스를 사용하여 전환할 때 수집된 모든 ID 동기화를 손실되지 않도록 할 수 있습니다.

보기:

[https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=ko](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=ko)

[https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=ko](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=ko)
