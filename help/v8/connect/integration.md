---
title: 솔루션과 Campaign 연결
description: Campaign을 솔루션과 연결하는 방법에 대해 알아보기
feature: Overview
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 14%

---

# 솔루션과 Campaign 연결{#gs-ac-connectors}

Campaign 인스턴스를 Adobe Experience Cloud 솔루션과 연결하여 기능을 결합할 수 있습니다.

Adobe Campaign에는 외부 애플리케이션과 통신하고, 데이터베이스 엔진에 연결하고, 데이터를 공유 및 동기화할 수 있는 여러 개의 커넥터가 포함되어 있습니다.

## Adobe 솔루션 활용 {#gs-ac-integration}

구현을 현대화하고 모든 Adobe Experience Cloud 기능을 활용합니다.

![](../assets/do-not-localize/speech.png)  관리 Cloud Services 사용자로, [연락처 Adobe](../start/campaign-faq.md#support) Adobe Experience Cloud 서비스 및 솔루션을 사용하여 Campaign을 연결할 수 있습니다.

Campaign v8은 다음과 연결할 수 있습니다.

* [Adobe Experience Cloud Real-Time CDP](../connect/ac-rtcdp.md)
* [Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journeys/using/action-journeys/acc-action.html?lang=en).

   엔드 투 엔드 사용 사례 를 참조하십시오 [여기](https://experienceleague.adobe.com/docs/journeys/using/use-cases-journeys/campaign-classic-use-case.html?lang=ko).

* [Adobe Analytics](../connect/ac-aa.md)
* [Adobe Experience Manager](../connect/ac-aem.md)
* [Adobe Experience Cloud 트리거](../connect/ac-triggers.md)
* [Adobe Target](../connect/ac-at.md)

또한 **대상자** 및 **assets** 자산 공유 및 대상 공유 기능이 있는 Experience Cloud 솔루션 간에 공유할 수 있습니다.

![](../assets/do-not-localize/book.png) 추가 정보 **대상 공유** 에서 Campaign과 Experience Cloud 솔루션 간 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/audience-sharing/sharing-audiences-with-adobe-experience-cloud.html?lang=en#integrating-with-adobe-experience-cloud)

![](../assets/do-not-localize/book.png) 추가 정보 **자산 공유** 에서 Campaign과 Experience Cloud 솔루션 간 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/asset-sharing/sharing-assets-with-adobe-experience-cloud.html?lang=en#integrating-with-adobe-experience-cloud)

## CRM 커넥터{#gs-crm-connectors}

Adobe Campaign 플랫폼을 **CRM 타사 시스템** 및 데이터를 동기화합니다. 연락처, 계정, 구매 등

채널 간 통신에서 CRM 데이터 활성화: crm 시스템에서 Adobe Campaign으로 연락처를 전달하고 Adobe Campaign에서 CRM 시스템으로 캠페인 데이터를 다시 공유하는 방법을 알아봅니다.
CRM 커넥터를 사용하면 빠르고 손쉽게 데이터를 통합할 수 있습니다. Adobe Campaign은 CRM에서 사용할 수 있는 테이블을 수집하고 선택하는 전용 도우미를 제공합니다. 이렇게 하면 시스템 전체에서 항상 데이터가 최신 상태로 유지되도록 양방향 동기화를 보장합니다.

![](../assets/do-not-localize/glass.png) 에서 Microsoft Dynamics 365 및 Salesforce.com과 Campaign을 통합하는 방법을 알아봅니다. [이 페이지](crm.md)

## FDA(Federated Data Access){#gs-fda}

FDA 커넥터(Federated Data Access)를 사용하여 Campaign을 하나 이상 연결합니다 **외부 데이터베이스** 및 Campaign Cloud 데이터베이스 데이터에 영향을 주지 않고 데이터베이스에 저장된 정보를 처리합니다.

![](../assets/do-not-localize/glass.png)[ 이 페이지](fda.md)에서 자세히 알아보십시오


<!--
## Integrate with social media

Use the **Managing social networks (Social Marketing)** option to interact with customers and prospects via Twitter.

* Send messages on Twitter: Adobe Campaign lets you post messages directly to your twitter account. You can also send direct messages to all your followers.
* Collect new contacts: Adobe Campaign can automatically recovers the profile data, which enables you to carry out targeting campaigns and, when possible, to implement cross-channel strategies.

![](../assets/do-not-localize/glass.png) Learn how to set up and use Campaign Social Marketing in [this page](../connect/ac-tw.md).

![](../assets/do-not-localize/glass.png) Learn how to create Twitter posts and send direct messages to your followers in [this page](../send/twitter.md).
-->