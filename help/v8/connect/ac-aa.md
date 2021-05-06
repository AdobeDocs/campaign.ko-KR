---
solution: Campaign Classic
product: campaign
title: Campaign 및 Adobe Analytics을 사용한 작업
description: Adobe Campaign 및 Adobe Analytics을 사용하여 작업하는 방법 살펴보기
feature: 개요
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
translation-type: tm+mt
source-git-commit: c2d066ca2f935455861c3d6747c9805c847f2e0d
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 3%

---

# Campaign 및 Adobe Analytics을 사용한 작업

## Experience Cloud 트리거

Experience Cloud 트리거를 사용하여 파이프라인을 사용하여 Adobe Campaign과 Adobe Analytics 간에 데이터를 연결할 수 있습니다. 파이프라인은 웹 사이트에서 사용자의 작업 또는 트리거를 검색합니다. 장바구니 포기는 트리거의 예입니다. 트리거는 Adobe Campaign에서 처리되어 거의 실시간으로 이메일을 전송합니다.

:speech_bal풍선:관리 Cloud Services 사용자는 [Adobe](../start/support.md#support)에 연락하여 캠페인에 Experience Cloud 트리거를 구현합니다.

## Adobe Analytics 데이터 커넥터

새 통합으로 업데이트하려면

Adobe Analytics 데이터 커넥터를 구성하여 캠페인 및 분석을 통합할 수도 있습니다.

데이터 커넥터(이전의 Adobe Genesis)을 사용하면 Adobe Campaign 및 Adobe Analytics이 **웹 분석 커넥터** 패키지를 통해 상호 작용할 수 있습니다. 이 통합은 이메일 후의 사용자 행동과 관련된 세그먼트로 Analytics에서 Campaign으로 데이터를 공유합니다. 반대로, Adobe Campaign이 제공하는 이메일 캠페인의 지표와 특성을 Adobe Analytics - 데이터 커넥터로 전송합니다.

이러한 통합 덕분에 Adobe Campaign은 마케팅 캠페인 이후 하나 이상의 사이트에 대한 방문자 행동 데이터를 복구할 수 있고 (분석 후) 리마케팅 캠페인을 실행함으로써 이러한 데이터를 구매자로 전환할 수 있습니다. 반대로 웹 분석 도구를 사용하면 Adobe Campaign에서 지표와 캠페인 속성을 해당 플랫폼에 전달할 수 있습니다.

각 도구의 작업 필드는 다음과 같습니다.

* Adobe Analytics:

   * Adobe Campaign에서 시작한 이메일 캠페인을 표시합니다.
   * 세그먼트 형태로 캠페인 이메일을 클릭한 후 이동한 사이트에 수신자 동작을 저장합니다. 세그먼트는 중단된 제품(장바구니에 표시되지만 장바구니에 추가되지는 않음), 구매 또는 장바구니 포기 등과 관련되어 있습니다.

* Adobe Campaign:

   * 표시기 및 캠페인 속성을 커넥터로 전송하고 이 커넥터는 웹 분석 도구로 전달합니다.
   * 세그먼트 복구 및 분석
   * 재마케팅 캠페인 트리거

https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html?lang=en#technical-workflows-of-web-analytics-processes을 참조하십시오.

:speech_bal풍선:관리 Cloud Services 사용자는 [Adobe](../start/support.md#support)에 연락하여 Adobe Analytics 데이터 커넥터를 캠페인에 통합합니다.

