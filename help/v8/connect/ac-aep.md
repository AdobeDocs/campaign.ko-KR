---
title: Campaign을 Adobe Experience Platform과 함께 사용하기
description: Campaign 및 Adobe Experience Platform을 사용하여 작업하는 방법 알아보기
feature: Platform Integration
role: Data Engineer
level: Beginner
source-git-commit: 9bea7904ea4507083d2cf45193877e7a2539d0c7
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# Campaign을 Adobe Experience Platform과 함께 사용하기

Adobe Campaign 관리 Cloud Service 대상 및 소스 커넥터를 사용하면 Adobe Campaign과 Adobe Experience Platform 간에 원활하게 통합할 수 있습니다.

* 사용 **Adobe Campaign Managed Cloud Services** 활성화를 위해 Experience Platform 세그먼트를 Adobe Campaign에 전송하는 대상 연결

   ![](assets/aep-destination.png)

* 사용 **Adobe Campaign Managed Cloud Services** Adobe Campaign 게재 및 추적 로그를 Adobe Experience Platform에 보내기 위한 소스 연결입니다.

   ![](assets/aep-logs.png)

Adobe Experience Platform에서 이 통합을 구성하는 단계는 다음과 같습니다.

1. 세그먼트/대상을 활성화하고 해당 데이터를 Adobe Campaign으로 보내도록 새 Adobe Campaign Managed Cloud Services 대상 연결을 구성합니다.

   사용할 Campaign 인스턴스에 대한 세부 사항을 제공하고 대상에 대해 활성화할 세그먼트를 선택한 다음 Campaign에 내보낼 속성을 구성합니다.

   [Adobe Campaign Managed Cloud Services 대상 연결을 만드는 방법을 알아봅니다](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

1. Campaign 이벤트를 Adobe Experience Platform으로 수집하기 위한 새 Adobe Campaign Managed Cloud Services 소스 연결을 구성합니다.

   Campaign 인스턴스 및 사용할 스키마에 대한 세부 정보를 제공하고, 데이터를 수집할 데이터 세트를 선택한 다음 검색할 필드를 구성합니다.

   [Adobe Campaign Managed Cloud Services 소스 연결을 만드는 방법을 알아봅니다](https://www.adobe.com/go/sources-campaign-ui-en)
