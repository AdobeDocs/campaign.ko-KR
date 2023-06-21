---
title: Campaign 및 Adobe Experience Platform 작업
description: Campaign을 Adobe Experience Platform과 함께 사용하는 방법에 대해 알아보기
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: f8c4e05ba2fc97d981fb31f9b11c5de1dcc1ff6e
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# Campaign 및 Adobe Experience Platform 작업

Adobe Campaign 관리 Cloud Service 대상 및 소스 커넥터를 사용하면 Adobe Campaign과 Adobe Experience Platform 간의 원활한 통합을 수행할 수 있습니다.

* Adobe Campaign Managed Cloud Services 사용 **대상 연결** 활성화를 위해 Experience Platform 세그먼트를 Adobe Campaign에 보내려면 다음 작업을 수행하십시오.

  이렇게 하려면 새 Adobe Campaign Managed Cloud Services을 구성합니다 **대상 연결** 세그먼트/대상자를 활성화하고 해당 데이터를 Adobe Campaign으로 전송합니다. 사용할 Campaign 인스턴스에 대한 세부 정보를 제공하고, 대상에 대해 활성화할 세그먼트를 선택한 다음 Campaign으로 내보낼 속성을 구성합니다. [Adobe Campaign Managed Cloud Services 대상 연결을 만드는 방법을 알아봅니다](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

  ![](assets/aep-destination.png){width="800" align="center"}

* Adobe Campaign Managed Cloud Services 사용 **소스 연결** Adobe Campaign 게재 및 추적 로그를 Adobe Experience Platform으로 보내려면

  이렇게 하려면 새 Adobe Campaign Managed Cloud Services을 구성합니다 **소스 연결** Adobe 이벤트를 Experience Platform에 수집합니다. 사용할 Campaign 인스턴스 및 스키마에 대한 세부 정보를 제공하고, 데이터를 수집해야 하는 데이터 세트를 선택한 다음 검색할 필드를 구성합니다. [Adobe Campaign Managed Cloud Services 소스 연결을 만드는 방법을 알아봅니다](https://www.adobe.com/go/sources-campaign-ui-en)

  ![](assets/aep-logs.png){width="800" align="center"}
