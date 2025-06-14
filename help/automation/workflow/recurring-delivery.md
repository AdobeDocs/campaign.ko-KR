---
product: campaign
title: 반복 게재
description: 반복 게재 워크플로우 활동에 대해 자세히 알아보기
feature: Workflows
role: User, Data Engineer
version: Campaign v8, Campaign Classic v7
exl-id: 27308b0d-cbfc-4bc6-9061-d771ceac95fd
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 13%

---

# 반복 게재{#recurring-delivery}



**[!UICONTROL Recurring delivery]** 활동을 사용하면 캠페인에 관련된 게재 템플릿 발생을 구성할 수 있습니다.

![](assets/do-not-localize/how-to-video.png) [비디오에서 이 기능 살펴보기](#recurring-delivery-video)

이 활동은 캠페인에 있는 **[!UICONTROL Targeting and workflows]** 탭에서만 사용할 수 있습니다.

방법은 다음과 같습니다.

1. 활동의 기반이 될 게재 템플릿을 선택합니다.

   ![](assets/recurring_delivery_001.png)

1. 게재 템플릿을 구성합니다.

이 활동에 대한 구성 프로세스는 사용 가능한 옵션 측면에서 게재 템플릿을 만드는 프로세스와 유사합니다.

사용 중인 이 활동의 예를 보려면 이 [섹션](send-a-birthday-email.md#creating-a-recurring-delivery-in-a-targeting-workflow)을 참조하세요.

## 반복 게재를 설정하는 방법

**반복 게재**&#x200B;은(는) 실행될 때마다 새 게재 인스턴스를 만듭니다. 예를 들어 워크플로를 일주일에 한 번 실행하도록 예약하면 1년 후 52회 게재가 됩니다. 즉, 광범위한 로그 및 추적 로그가 각 게재 인스턴스에 의해 구분됩니다.

![반복 게재](assets/delivery_recurring.jpg)

반복 게재의 실행을 중지하려면 캠페인을 완전히 취소하거나 실행 중인 워크플로우를 중지해야 합니다. 캠페인 대시보드에서 게재를 중지하면 게재 발생만 중지됩니다. 각 워크플로우 실행 시 반복 게재의 다음 인스턴스가 계속 생성됩니다.

>[!NOTE]
>
>**[!UICONTROL Recurring delivery]** 유형 활동에서 증명을 보낼 수 없습니다.
> 
>캠페인 워크플로우를 통해 직접 게재를 만들려면 미리 구성된 채널별 활동(예: **[!UICONTROL Email delivery]**)을 사용하십시오.

## 튜토리얼 비디오 (#recurring-delivery-video)

이 비디오에서는 반복 게재 및 예약 활동을 구성하는 방법을 설명합니다.

>[!VIDEO](https://video.tv.adobe.com/v/27507?quality=12&captions=kor)

추가 캠페인 사용 방법 비디오를 [여기](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html?lang=ko){target="_blank"}에서 사용할 수 있습니다.
