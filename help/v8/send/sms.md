---
title: Adobe Campaign으로 SMS 보내기
description: Campaign에서 SMS 시작
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 2%

---

# SMS 만들기 및 보내기

Adobe Campaign을 사용하여 개인화된 SMS 메시지를 보냅니다.

에서 SMS 채널을 시작하는 방법 알아보기 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target="_blank"}

>[!NOTE]
>
>또한 Adobe Campaign을 사용하면 모바일에서 해당 페이지를 통해 푸시 알림을 제출할 수 있습니다 **Adobe Campaign 모바일 앱 채널(NMAC)** 옵션을 선택합니다. [이 섹션](push.md)에서 자세히 알아보십시오.

## SMS 채널 구성

휴대폰으로 보내려면 다음이 필요합니다.

* 커넥터 및 메시지 유형을 지정하는 외부 계정입니다.

* 이 외부 계정이 참조되는 게재 템플릿입니다.

에서 SMS 채널을 구성하는 방법 알아보기 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#sending-messages){target="_blank"}

SMS 전송을 시작하기 전에:

* 수신자 프로필에 휴대폰 이상이 포함되어 있는지 확인하십시오.
* Adobe Campaign Classic 검토 [게재 모범 사례](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html#sending-messages){target="_blank"} Campaign v8에도 적용됩니다.

또한 SMS 프로토콜 및 설정에 익숙해야 합니다. 에서 Adobe Campaign과 SMPP 공급자 간 연결 설정을 살펴봅니다. [이 문서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html#sending-messages){target="_blank"}.

## 첫 번째 SMS 게재 만들기

1. 새 게재를 만들려면 **[!UICONTROL Campaigns]** 탭을 클릭하고 **[!UICONTROL Deliveries]** 을(를) 클릭하고 **[!UICONTROL Create]** 기존 게재 목록 위에 있는 단추입니다.

   ![](assets/delivery_step_1.png)

   게재를 만드는 방법에 대한 전역 정보는 을 참조하십시오. [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html#sending-messages){target="_blank"}.

1. SMS 게재를 보낼 관련 외부 계정을 참조하는 게재 템플릿을 선택합니다.

   ![](assets/sms-template-list.png)

   에서 SMPP 외부 계정을 만드는 방법 알아보기 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#creating-an-smpp-external-account){target="_blank"}

   에서 모바일에 게재할 게재 템플릿을 만드는 방법을 알아봅니다. [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#changing-the-delivery-template){target="_blank"}

1. 레이블, 코드 및 설명을 사용하여 게재를 식별합니다.

1. 클릭 **[!UICONTROL Continue]** 을 눌러 메시지 구성 창을 확인하고 표시합니다.

1. 에 메시지 내용 입력 **[!UICONTROL Text content]** 필요한 경우 개인화 필드를 포함하는 마법사의 섹션입니다.

   ![](assets/sms-content.png)

1. 대상 모집단을 선택합니다.

SMS를 만들고 디자인하는 주요 단계는 Campaign Classic v7 설명서에 자세히 설명되어 있습니다.

* SMS 만들기

  [SMS 게재를 만드는 방법 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html#sending-messages){target="_blank"}

* SMS 콘텐츠 디자인

  [SMS 콘텐츠를 정의하는 방법 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html#defining-the-sms-content){target="_blank"}

* 이메일 대상자 선택

  [대상 모집단을 정의하는 방법 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}

대상자를 정의하는 단계는에 자세히 설명되어 있습니다. [이 페이지](../start/audiences.md).

## SMS 테스트

개인화된 메시지 렌더링을 보려면 을 클릭합니다. **[!UICONTROL Preview]** 수신자를 선택합니다.

![](assets/sms-preview.png)

증명을 보내려면 Campaign Classic v7 설명서의 다음 섹션을 참조하십시오.

* 게재 유효성 검사 및 증명 보내기
  [게재 유효성 검사를 위한 주요 단계 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=ko){target="_blank"}
* 시드 주소 추가
  [시드 주소에 대해 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target="_blank"}

## SMS 게재 보내기 및 모니터링

SMS를 보내고 모니터링하는 주요 단계는 Campaign Classic v7 설명서에 자세히 설명되어 있습니다.

* SMS 게재 보내기, 모니터링 및 추적

  [SMS 전송, 모니터링 및 추적 도구에 대해 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html#sending-messages){target="_blank"}

* SMS 게재 문제 해결

  [SMS 문제 해결에 대해 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html#sending-messages){target="_blank"}
