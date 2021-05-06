---
solution: Campaign Classic
product: campaign
title: Adobe Campaign으로 SMS 보내기
description: Campaign에서 SMS 시작하기
feature: 개요
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 1eab5e9c54f2653b4b8ca9a7c2c4b06231980ed5
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 2%

---

# SMS 만들기 및 보내기

Adobe Campaign을 사용하여 개인화된 SMS 메시지를 보낼 수 있습니다.

SMS를 보내는 주요 단계는 다음 섹션에 자세히 설명되어 있습니다.

* [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages)에서 SMS 채널을 구성하는 방법에 대해 알아봅니다.
* [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages)에서 SMS 배달을 만드는 방법에 대해 알아봅니다.
* 대상을 정의하는 단계는 이 페이지](../start/audiences.md)에 자세히 [입니다.
* [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content)에서 SMS 컨텐츠를 정의하는 방법을 알아봅니다.
* SMS를 전송, 모니터링 및 추적하는 도구는 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages)에 설명되어 있습니다.
* [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages)에서 SMS 배달 문제를 해결하는 방법에 대해 알아봅니다.

SMS 전송을 시작하기 전:

* 받는 사람 프로필에 휴대폰이 하나 이상 포함되어 있는지 확인합니다.
* Campaign v8에도 적용되는 Adobe Campaign Classic [배달 모범 사례](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages)를 읽어 보십시오.

또한 SMS 프로토콜 및 설정에 익숙해야 합니다. [이 문서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=en#sending-messages)에서 Adobe Campaign과 SMPP 공급자 사이에 설정된 연결을 살펴보십시오.

배달을 만드는 방법에 대한 글로벌 정보는 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages)를 참조하십시오.

>[!NOTE]
>
>또한 Adobe Campaign에서는 **Adobe Campaign Mobile App Channel(NMAC)** 옵션을 통해 모바일 터미널에서 알림을 제출할 수 있습니다.
> 
>이 작업에 대한 자세한 정보는 [이 섹션](push.md)을 참조하십시오.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html)에서 자세한 내용
