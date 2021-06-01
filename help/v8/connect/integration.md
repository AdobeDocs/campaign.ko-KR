---
product: Adobe Campaign
title: 마케팅 캠페인 시작
description: 마케팅 캠페인 시작
feature: 개요
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 13%

---

# Campaign을 솔루션{#gs-ac-connectors}과 연결

Campaign 인스턴스를 Adobe Experience Cloud 솔루션과 연결하여 기능을 결합할 수 있습니다.

Adobe Campaign에는 외부 애플리케이션과 통신하고, 데이터베이스 엔진에 연결하고, 데이터를 공유 및 동기화할 수 있는 여러 개의 커넥터가 포함되어 있습니다.

## Adobe 솔루션 활용 {#gs-ac-integration}

구현을 현대화하고 모든 Adobe Experience Cloud 기능을 활용합니다.

[!DNL :speech_balloon:] 관리 Cloud Services 사용자는  [Adobe](../start/campaign-faq.md#support) 에 문의하여 Campaign을 Adobe Experience Cloud 서비스 및 솔루션과 연결하십시오. IMS(Adobe Identity Management 서비스)를 구현해야 합니다. [자세히 알아보기](../start/connect.md#connect-ims)

Campaign v8은 다음과 연결할 수 있습니다.

* [Adobe Journey Orchestration](https://experienceleague.adobe.com/docs/journeys/using/action-journeys/acc-action.html?lang=en)
* [실시간 CDP](../connect/ac-rtcdp.md)
* [Adobe Analytics](../connect/ac-aa.md)
* [Adobe Experience Manager](../connect/ac-aem.md)
* [Adobe Experience Cloud 트리거](../connect/ac-triggers.md)
* [Adobe Target](../connect/ac-at.md)

자산 공유 및 대상 공유 기능을 사용하여 Experience Cloud 솔루션에서 **대상** 및 **자산**&#x200B;을 결합할 수도 있습니다.

[!DNL :arrow_upper_right:]  **Campaign Classic v7** 설명서에서 Campaign과  [Experience Cloud 솔루션 간의 대상 공유에 대해 자세히 알아보십시오](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/audience-sharing/sharing-audiences-with-adobe-experience-cloud.html?lang=en#integrating-with-adobe-experience-cloud)

[!DNL :arrow_upper_right:]  **Campaign Classic v7** 설명서에서 Campaign과  [Experience Cloud 솔루션 간의 자산 공유에 대해 자세히 알아보십시오](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/asset-sharing/sharing-assets-with-adobe-experience-cloud.html?lang=en#integrating-with-adobe-experience-cloud)

## CRM 커넥터{#gs-crm-connectors}

Adobe Campaign 플랫폼을 **CRM 타사 시스템**&#x200B;에 연결하고 데이터를 동기화할 수 있습니다.연락처, 계정, 구매 등

채널 간 통신에서 CRM 데이터 활성화:crm 시스템에서 Adobe Campaign으로 연락처를 전달하고 Adobe Campaign에서 CRM 시스템으로 캠페인 데이터를 다시 공유하는 방법을 알아봅니다.
CRM 커넥터를 사용하면 빠르고 손쉽게 데이터를 통합할 수 있습니다.Adobe Campaign은 CRM에서 사용할 수 있는 테이블을 수집하고 선택하는 전용 도우미를 제공합니다. 이렇게 하면 시스템 전체에서 항상 데이터가 최신 상태로 유지되도록 양방향 동기화를 보장합니다.

[!DNL :bulb:] 이 페이지에서 Campaign을 Microsoft Dynamics 365 및 Salesforce.com과 통합하는  [방법을 알아봅니다](crm.md)

## FDA(Federated Data Access){#gs-fda}

FDA 커넥터(Federated Data Access)를 사용하여 Campaign을 하나 이상의 **외부 데이터베이스**&#x200B;에 연결하고 Campaign Cloud 데이터베이스 데이터에 영향을 주지 않고 Campaign에 저장된 정보를 처리합니다.

[!DNL :bulb:][ 이 페이지](fda.md)에서 자세히 알아보기


<!-- 
 ## Integrate with social media

Use the **Managing social networks (Social Marketing)** option to interact with customers and prospects via Twitter.

* Send messages - Use Adobe Campaign Social Marketing to send messages on Twitter. Adobe Campaign lets you post messages directly to your twitter account. You can also send direct messages to all your followers.

* Collect new contacts - Adobe Campaign Social Marketing also makes it easy to acquire new contacts via Facebook: contact users and ask them if they want to share their profile information. If they accept, Adobe Campaign automatically recovers the data, which enables you to carry out targeting campaigns and, when possible, to implement cross-channel strategies.

[!DNL :bulb:] Learn how to set up and use Campaign Social Marketing in [this section](../connect/ac-tw.md) -->