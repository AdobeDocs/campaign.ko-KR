---
title: Adobe Campaign으로 SMS 보내기
description: Campaign에서 SMS 시작
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 2%

---

# SMS 만들기 및 보내기

Adobe Campaign을 사용하여 개인화된 SMS 메시지를 보냅니다.

![](../assets/do-not-localize/book.png) 에서 SMS 채널을 시작하는 방법을 알아봅니다 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target=&quot;_blank&quot;}

>[!NOTE]
>
>또한 Adobe Campaign을 사용하면 해당 알림을 통해 모바일에 푸시 알림을 제출할 수도 있습니다 **Adobe Campaign Mobile 앱 채널(NMAC)** 선택 사항입니다. 추가 정보 [이 섹션](push.md).

## SMS 채널 구성

휴대폰에 보내려면 다음이 필요합니다.

* 커넥터와 메시지 유형을 지정하는 외부 계정입니다.

* 이 외부 계정을 참조하는 게재 템플릿입니다.

![](../assets/do-not-localize/book.png)  에서 SMS 채널을 구성하는 방법을 알아봅니다 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages){target=&quot;_blank&quot;}

SMS 전송을 시작하기 전:

* 수신자 프로필에 휴대폰 이상이 포함되어 있는지 확인하십시오.
* Adobe Campaign Classic 검토 [게재 모범 사례](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages)Campaign v8에도 적용되는 {target=&quot;_blank&quot;}.

또한 SMS 프로토콜 및 설정을 잘 알고 있어야 합니다. 에서 Adobe Campaign과 SMPP 공급자 간에 설정된 연결을 살펴봅니다 [이 문서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=en#sending-messages){target=&quot;_blank&quot;}.

## 첫 번째 SMS 게재 만들기

1. 새 게재를 만들려면 **[!UICONTROL Campaigns]** 탭, **[!UICONTROL Deliveries]** 을 클릭하고 **[!UICONTROL Create]** 기존 게재 목록 위의 단추.

   ![](assets/delivery_step_1.png)

   ![](../assets/do-not-localize/book.png) 게재를 만드는 방법에 대한 글로벌 정보는 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}.

1. SMS 게재를 보낼 관련 외부 계정을 참조하는 게재 템플릿을 선택합니다.

   ![](assets/sms-template-list.png)

   ![](../assets/do-not-localize/book.png) 에서 SMPP 외부 계정을 만드는 방법을 알아봅니다 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account){target=&quot;_blank&quot;}

   ![](../assets/do-not-localize/book.png) 에서 모바일에 전달할 게재 템플릿을 만드는 방법을 알아봅니다 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template){target=&quot;_blank&quot;}

1. 레이블, 코드 및 설명을 사용하여 게재를 식별합니다.

1. 클릭 **[!UICONTROL Continue]** 메시지 구성 창을 확인하고 표시합니다.

1. 메시지의 내용을 **[!UICONTROL Text content]** 필요에 따라 개인화 필드를 포함하는 마법사 섹션을 참조하십시오.

   ![](assets/sms-content.png)

1. 대상 모집단을 선택합니다.

SMS를 만들고 디자인하는 주요 단계는 Campaign Classic v7 설명서에 자세히 설명되어 있습니다.

* SMS 만들기

   ![](../assets/do-not-localize/book.png) [SMS 게재를 만드는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* SMS 콘텐츠 디자인

   ![](../assets/do-not-localize/book.png) [SMS 콘텐츠를 정의하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content){target=&quot;_blank&quot;}

* 이메일 대상자를 선택합니다

   ![](../assets/do-not-localize/book.png) [대상 모집단을 정의하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target=&quot;_blank&quot;}

![](../assets/do-not-localize/glass.png) 대상을 정의하는 단계는 다음과 같이 자세히 설명되어 있습니다 [이 페이지](../start/audiences.md).

## SMS 테스트

개인화로 메시지 렌더링을 보려면 **[!UICONTROL Preview]** 수신자를 선택합니다.

![](assets/sms-preview.png)

증명을 보내려면 Campaign Classic v7 설명서의 다음 섹션을 참조하십시오.

* 게재 유효성 검사 및 증명 보내기
   ![](../assets/do-not-localize/book.png) [게재의 유효성을 검사하는 주요 단계를 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}
* 시드 주소 추가
   ![](../assets/do-not-localize/book.png) [시드 주소에 대해 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target=&quot;_blank&quot;}

## SMS 게재 전송 및 모니터링

SMS를 보내고 모니터링하는 주요 단계는 Campaign Classic v7 설명서에 자세히 설명되어 있습니다.

* SMS 게재 전송, 모니터링 및 추적

   ![](../assets/do-not-localize/book.png) [SMS를 전송, 모니터링 및 추적하는 도구에 대해 알아봅니다.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* SMS 게재 문제 해결

   ![](../assets/do-not-localize/book.png) [SMS 문제 해결에 대해 알아봅니다.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages){target=&quot;_blank&quot;}
