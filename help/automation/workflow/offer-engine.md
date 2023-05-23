---
product: campaign
title: 오퍼 엔진
description: 오퍼 엔진
feature: Workflows, Interaction
exl-id: d77858e1-3cd5-4372-b1bc-ea4b518c958d
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 4%

---

# 오퍼 엔진{#offer-engine}

다음 **[!UICONTROL Offer engine]** 활동을 사용하면 게재 전에 오퍼 엔진에 대한 호출을 정의할 수 있습니다.

이 활동은 게재 전에 엔진에서 계산한 오퍼로 인바운드 모집단 데이터를 보강하여 엔진 호출을 사용한 보강 활동과 동일한 원리로 작동합니다.

![](assets/int_offerengine_activity2.png)

쿼리를 구성한 후(이 참조) [섹션](query.md)):

1. 추가 및 열기 **[!UICONTROL Offer engine]** 활동.
1. 사용 가능한 다양한 필드를 완료하여 오퍼 엔진 매개 변수(오퍼 공간, 카테고리 또는 테마, 연락 날짜, 유지할 오퍼 수)에 대한 호출을 지정합니다. 엔진은 이러한 매개 변수에 따라 추가할 오퍼를 자동으로 계산합니다.

   >[!CAUTION]
   >
   >이 활동을 사용하는 경우 게재에 사용된 오퍼 제안만 저장됩니다.

   ![](assets/int_offerengine_activity1.png)

1. 그런 다음 선택한 채널에 해당하는 게재 활동을 구성합니다. 을(를) 참조하십시오 [크로스 채널 게재](cross-channel-deliveries.md).
