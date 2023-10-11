---
product: campaign
title: 크로스 채널 게재
description: 크로스 채널 게재에 대해 자세히 알아보기
feature: Workflows, Channels Activity
role: User
exl-id: fedcffcd-cf9b-4c3d-bd25-cb87dda30192
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 4%

---

# 크로스 채널 게재{#cross-channel-deliveries}

크로스 채널 게재는 다음 위치에서 사용할 수 있습니다. **[!UICONTROL Deliveries]** 탭 / [캠페인 워크플로우](campaign-workflows.md) 활동.

게재의 기반이 되는 템플릿을 선택하고 콘텐츠를 정의합니다.

다른 타겟팅 활동을 사용하여 워크플로우의 업스트림 게재를 위한 타겟을 지정할 수 있습니다.

아래 예에서는 푸시 알림 구독자를 위해 이메일 또는 SMS를 보낸 다음 1주일 후에 푸시 알림을 전송하는 워크플로우를 만드는 방법을 알아봅니다. 방법은 다음과 같습니다.

1. 캠페인 만들기.
1. 다음에서 **[!UICONTROL Targeting and workflows]** 캠페인의 탭에서 **[!UICONTROL Query]** 활동.
1. 쿼리 구성: 푸시 알림을 구독하는 수신자를 대상 차원으로 선택합니다.

   >[!NOTE]
   >
   >푸시 알림의 경우 **구독자 애플리케이션** 대상 차원.

   ![](assets/cross_channel_delivery_1.png)

1. 쿼리에 필터 조건을 추가합니다. 이 경우 휴대폰 번호 또는 이메일 주소가 있는 수신자를 선택합니다.

   ![](assets/cross_channel_delivery_2.png)

1. 추가 **[!UICONTROL Split]** 활동을 워크플로우에 추가하여 모바일 번호가 있는 수신자와 이메일 주소가 있는 수신자를 나눕니다.
1. 다음에서 **[!UICONTROL Delivery]** 탭에서 각 타겟에 대한 게재를 선택합니다.

   워크플로우에서 게재 활동을 두 번 클릭하여 클래식 게재 마법사와 동일한 방식으로 게재를 만듭니다.

   ![](assets/cross_channel_delivery_3.png)

1. 추가 및 구성 **[!UICONTROL Wait]** 활동은 수신자가 한 번에 너무 많은 게재를 받지 않도록 하기 위한 것입니다.
1. 추가 **[!UICONTROL Split]** 활동은 iOS 또는 Android 모바일 애플리케이션의 구독자를 나눕니다.

   각 운영 체제에 대한 서비스를 선택합니다.

   ![](assets/cross_channel_delivery_4.png)

1. 각 운영 체제에 대한 모바일 애플리케이션 제공을 선택하고 구성합니다.

   ![](assets/cross_channel_delivery_5.png)
