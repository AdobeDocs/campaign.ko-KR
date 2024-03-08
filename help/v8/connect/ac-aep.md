---
title: Adobe Experience Platform에서 대상자 및 프로필 속성 공유 및 동기화
description: Adobe Experience Platform 대상자 및 프로필 속성을 Campaign과 동기화하는 방법 알아보기
feature: Experience Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: ea37b72efd03afb212c060f809b6ba077b996701
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---

# Adobe Experience Platform과 대상자 공유 및 동기화 {#gs-ac-aep}

Adobe Campaign 관리 Cloud Service 대상 및 소스 커넥터를 사용하면 Adobe Campaign과 Adobe Experience Platform 간의 원활한 통합을 수행할 수 있습니다. 이 통합을 통해 다음과 같은 작업을 수행할 수 있습니다.

* Adobe Experience Platform 대상자를 Adobe Campaign으로 보내고, 분석 목적으로 게재 및 추적 로그를 Adobe Experience Platform으로 다시 보냅니다.
* Adobe Experience Platform 프로필 속성을 Adobe Campaign으로 가져오고 정기적으로 업데이트할 수 있도록 동기화 프로세스를 준비하십시오.

## Campaign에 Adobe Experience Platform 대상 보내기 {#audiences}

Adobe Experience Platform 대상을 Adobe Campaign으로 보내고 게재 및 추적 로그를 다시 보내는 주요 단계는 다음과 같습니다.

* Adobe Campaign Managed Cloud Services 사용 **대상 연결** Adobe Campaign으로 Experience Platform 세그먼트를 보내려면 다음을 수행하십시오.

   1. Adobe Experience Platform 대상 카탈로그에 액세스하고 새 를 만듭니다 **[!UICONTROL Adobe Campaign Managed Cloud Services]** 연결.
   1. 사용 및 선택할 Campaign 인스턴스에 대한 세부 정보를 제공합니다. **[!UICONTROL Audience sync]** 동기화 유형으로 선택해야 합니다.

      ![](assets/aep-audience-sync.png){width="800" align="center"}

   1. Adobe Campaign으로 전송할 세그먼트를 선택하십시오.
   1. 대상에서 내보낼 속성을 구성합니다.
   1. 흐름이 구성되면 선택한 대상을 Adobe Campaign에 활성화할 수 있습니다.

      ![](assets/aep-destination.png){width="800" align="center"}

  대상을 구성하는 방법에 대한 자세한 내용은에서 확인할 수 있습니다 [Adobe Campaign Managed Cloud Services 연결 설명서](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en){target="_blank"}

* Adobe Campaign Managed Cloud Services 사용 **소스 연결** Adobe Campaign 게재 및 추적 로그를 Adobe Experience Platform으로 보내려면

  이렇게 하려면 새 Adobe Campaign Managed Cloud Services을 구성합니다 **소스 연결** Adobe 이벤트를 Experience Platform에 수집합니다. 사용할 Campaign 인스턴스 및 스키마에 대한 세부 정보를 제공하고, 데이터를 수집해야 하는 데이터 세트를 선택한 다음 검색할 필드를 구성합니다. [Adobe Campaign Managed Cloud Services 소스 연결을 만드는 방법을 알아봅니다](https://www.adobe.com/go/sources-campaign-ui-en)

  ![](assets/aep-logs.png){width="800" align="center"}

## Adobe Experience Platform과 Adobe Campaign 간 프로필 속성 동기화 {#profile}

Adobe Campaign을 Adobe Experience Platform과 연결하면 Adobe Experience Platform의 프로필에 연결된 추가 프로필 속성을 가져올 수 있으며 Adobe Campaign 데이터베이스에서 업데이트되도록 동기화 프로세스를 유지할 수 있습니다.

예를 들어 Adobe Experience Platform에서 옵트인 및 옵트아웃 값을 캡처한다고 가정해 보겠습니다. 이 연결을 사용하면 이러한 값을 Adobe Campaign으로 가져오고 정기적으로 업데이트되도록 동기화 프로세스를 유지할 수 있습니다.

>[!NOTE]
>
>프로필 속성 동기화는 Adobe Campaign 데이터베이스에 이미 있는 프로필에 사용할 수 있습니다.

Adobe Experience Platform 프로필 속성을 Adobe Campaign과 동기화하는 주요 단계는 다음과 같습니다.

1. Adobe Experience Platform 대상 카탈로그에 액세스하고 새 를 만듭니다 **[!UICONTROL Adobe Campaign Managed Cloud Services]** 연결.
1. 사용 및 선택할 Campaign 인스턴스에 대한 세부 정보를 제공합니다. **[!UICONTROL Profile sync (Update only)]** 동기화 유형으로 선택해야 합니다.

   ![](assets/aep-profile-sync.png){width="800" align="center"}

1. Adobe Campaign 데이터베이스로 업데이트할 프로필을 타겟팅하는 세그먼트를 선택합니다.
1. Adobe Campaign으로 업데이트할 프로필 속성을 구성합니다.
1. 흐름이 구성되면 선택한 프로필 속성이 Adobe Campaign과 동기화되고 대상에 구성된 세그먼트에서 타겟팅한 모든 프로필에 대해 업데이트됩니다.

대상을 구성하는 방법에 대한 자세한 내용은에서 확인할 수 있습니다 [Adobe Campaign Managed Cloud Services 연결 설명서](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en){target="_blank"}