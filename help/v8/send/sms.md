---
product: Adobe Campaign
title: Adobe Campaign으로 SMS 보내기
description: Campaign에서 SMS 시작
feature: 개요
role: Data Engineer
level: Beginner
source-git-commit: 35814053bff993d0b130bf598c8601c3f5adc407
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 3%

---

# SMS 만들기 및 보내기

Adobe Campaign을 사용하여 개인화된 SMS 메시지를 보냅니다.

[!DNL :arrow_upper_right:]  [Campaign Classic v7 설명서에서 SMS 채널을 시작하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html)

>[!NOTE]
>
>또한 Adobe Campaign을 사용하면 **Adobe Campaign 모바일 앱 채널(NMAC)** 옵션을 통해 모바일에 푸시 알림을 제출할 수 있습니다. 자세한 내용은 [이 섹션](push.md)을 참조하십시오.

## SMS 채널 구성

휴대폰에 보내려면 다음이 필요합니다.

* 커넥터와 메시지 유형을 지정하는 외부 계정입니다.

* 이 외부 계정을 참조하는 게재 템플릿입니다.

[!DNL :arrow_upper_right:]   [Campaign Classic v7 설명서에서 SMS 채널을 구성하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages)

SMS 전송을 시작하기 전:

* 수신자 프로필에 휴대폰 이상이 포함되어 있는지 확인하십시오.
* Campaign v8에도 적용되는 Adobe Campaign Classic [게재 우수 사례](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages)를 검토하십시오.

또한 SMS 프로토콜 및 설정을 잘 알고 있어야 합니다. [이 문서에서 Adobe Campaign과 SMPP 공급자 간에 설정된 연결을 살펴봅니다.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=en#sending-messages).

## 첫 번째 SMS 게재 만들기

1. 새 게재를 만들려면 **[!UICONTROL Campaigns]** 탭으로 이동하여 **[!UICONTROL Deliveries]** 을 클릭하고 기존 게재 목록 위에 있는 **[!UICONTROL Create]** 버튼을 클릭합니다.

   ![](assets/delivery_step_1.png)

   [!DNL :arrow_upper_right:] 게재를 만드는 방법에 대한 글로벌 정보는  [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages)를 참조하십시오.

1. SMS 게재를 보낼 관련 외부 계정을 참조하는 게재 템플릿을 선택합니다.

   ![](assets/sms-template-list.png)

   [!DNL :arrow_upper_right:]  [Campaign Classic v7 설명서에서 SMPP 외부 계정을 만드는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account)

   [!DNL :arrow_upper_right:]  [Campaign Classic v7 설명서에서 모바일에 전달할 게재 템플릿을 만드는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template)

1. 레이블, 코드 및 설명을 사용하여 게재를 식별합니다.

1. **[!UICONTROL Continue]** 을 클릭하여 메시지 구성 창을 확인하고 표시합니다.

1. 필요에 따라 개인화 필드를 포함하여 마법사의 **[!UICONTROL Text content]** 섹션에 메시지 콘텐츠를 입력합니다.

   ![](assets/sms-content.png)

1. 대상 모집단을 선택합니다.

SMS를 만들고 디자인하는 주요 단계는 Campaign Classic v7 설명서에 자세히 설명되어 있습니다.

* SMS 만들기

   [!DNL :arrow_upper_right:] [SMS 게재를 만드는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages)

* SMS 콘텐츠 디자인

   [!DNL :arrow_upper_right:] [SMS 콘텐츠를 정의하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content)

* 이메일 대상자를 선택합니다

   [!DNL :arrow_upper_right:] [대상 모집단을 정의하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)

[!DNL :bulb:] 대상을 정의하는 단계는  [이 페이지에 자세히 설명되어 있습니다](../start/audiences.md).

## SMS 테스트

개인화로 메시지 렌더링을 보려면 **[!UICONTROL Preview]** 을 클릭하고 수신자를 선택하십시오.

![](assets/sms-preview.png)

증명을 보내려면 Campaign Classic v7 설명서의 다음 섹션을 참조하십시오.

* 게재 유효성 검사 및 증명 보내기
   [!DNL :arrow_upper_right:] [게재의 유효성을 검사하는 주요 단계를 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
* 시드 주소 추가
   [!DNL :arrow_upper_right:] [시드 주소에 대해 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html)

## SMS 게재 전송 및 모니터링

SMS를 보내고 모니터링하는 주요 단계는 Campaign Classic v7 설명서에 자세히 설명되어 있습니다.

* SMS 게재 전송, 모니터링 및 추적

   [!DNL :arrow_upper_right:] [SMS를 전송, 모니터링 및 추적하는 도구에 대해 알아봅니다.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages)
* SMS 게재 문제 해결

   [!DNL :arrow_upper_right:] [SMS 문제 해결에 대해 알아봅니다.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages)
