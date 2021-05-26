---
solution: Campaign v8
product: Adobe Campaign
title: Campaign을 Adobe Analytics과 함께 사용하기
description: Campaign 및 Adobe Analytics을 사용하여 작업하는 방법 알아보기
feature: 개요
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: 4ae0c968bd68d76d7ceffb91023d5426d6a810ea
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 2%

---

# Campaign을 Adobe Analytics과 함께 사용하기


## Adobe Analytics 커넥터

Campaign과 Analytics를 통합하도록 Adobe Analytics 커넥터를 구성할 수 있습니다.

Adobe Analytics 커넥터를 사용하면 Adobe Campaign 및 Adobe Analytics이 **Web Analytics 커넥터** 추가 기능을 통해 상호 작용할 수 있습니다. 이 통합은 이메일 이후의 사용자 동작과 관련된 세그먼트로 Analytics에서 Campaign으로 데이터를 공유합니다. 반대로 Adobe Campaign에서 Adobe Analytics - Data Connector로 제공하는 이메일 캠페인의 지표와 특성을 보냅니다.

Adobe Campaign에는 Adobe Analytics 커넥터를 사용하여 인터넷 대상자(Web Analytics)를 측정하는 방법이 있습니다. 이러한 통합 덕분에 Adobe Campaign은 마케팅 캠페인 후 하나 이상의 사이트에 대한 방문자 동작에 대한 데이터를 복구한 다음(분석 후)보기 로 재마케팅 캠페인을 실행하여 바이어로 전환할 수 있습니다. 반대로 웹 분석 도구를 사용하면 Adobe Campaign에서 지표와 캠페인 속성을 플랫폼에 전달할 수 있습니다.

각 도구의 작업 필드는 다음과 같습니다.

* **Adobe Analytics**

   * Adobe Campaign에서 시작한 이메일 캠페인을 표시합니다
   * campaign 이메일을 클릭한 후 검색한 사이트에서 수신자 동작을 세그먼트 형태로 저장합니다. 세그먼트는 포기한 제품(열람했지만 장바구니에 추가되지 않음), 구매 또는 장바구니 포기 와 관련되어 있습니다.

* **Adobe Campaign**

   * indicators 및 campaign 속성을 커넥터로 전송하고 커넥터를 웹 분석 도구에 전달합니다
   * 세그먼트 복구 및 분석
   * 리마케팅 캠페인 트리거

[이 페이지에서 Adobe Campaign 및 Adobe Analytics에 대해 자세히 알아보십시오](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html)

[!DNL :speech_balloon:]  관리되는 Cloud Services 사용자는  [Adobe](../start/campaign-faq.md#support) 에 문의하여 Adobe Analytics Data Connector를 Campaign과 통합하십시오.


## Experience Cloud 트리거

Experience Cloud 트리거 을 사용하여 파이프라인을 사용하여 Adobe Campaign과 Adobe Analytics 간에 데이터를 연결할 수 있습니다. 파이프라인은 웹 사이트에서 사용자의 작업 또는 트리거를 검색합니다. 장바구니 포기 는 트리거의 예입니다. 트리거는 Adobe Campaign에서 처리되어 거의 실시간으로 이메일을 전송합니다.

[이 페이지](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en)에서 Adobe Campaign 및 Experience Cloud 트리거에 대해 자세히 알아보십시오.

[!DNL :speech_balloon:]  관리되는 Cloud Services 사용자는  [Adobe](../start/campaign-faq.md#support) 에 문의하여 Campaign으로 Experience Cloud 트리거를 구현합니다.
