---
solution: Campaign v8
product: Adobe Campaign
title: Adobe Campaign으로 SMS 보내기
description: Campaign에서 SMS 시작
feature: 개요
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 2%

---

# SMS 만들기 및 보내기

Adobe Campaign을 사용하여 개인화된 SMS 메시지를 보냅니다.

SMS를 전송하는 주요 단계는 다음 섹션에 자세히 설명되어 있습니다.

* [Campaign Classic v7 설명서에서 SMS 채널을 구성하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages)
* [Campaign Classic v7 설명서에서 SMS 게재를 만드는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages)
* 대상을 정의하는 단계는 이 페이지](../start/audiences.md)에 자세히 설명되어 있습니다[
* [Campaign Classic v7 설명서에서 SMS 콘텐츠를 정의하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content)
* SMS를 전송, 모니터링 및 추적하는 도구는 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages)에 설명되어 있습니다
* [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages)에서 SMS 게재 문제를 해결하는 방법을 알아봅니다.

SMS 전송을 시작하기 전:

* 수신자 프로필에 휴대폰 이상이 포함되어 있는지 확인하십시오.
* Campaign v8에도 적용되는 Adobe Campaign Classic [게재 우수 사례](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages)를 검토하십시오.

또한 SMS 프로토콜 및 설정을 잘 알고 있어야 합니다. [이 문서에서 Adobe Campaign과 SMPP 공급자 간에 설정된 연결을 살펴봅니다.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=en#sending-messages)

게재를 만드는 방법에 대한 글로벌 정보는 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages)를 참조하십시오.

>[!NOTE]
>
>또한 Adobe Campaign을 사용하면 **Adobe Campaign 모바일 앱 채널(NMAC)** 옵션을 통해 모바일 터미널에 알림을 제출할 수도 있습니다.
> 
>이 작업에 대한 자세한 정보는 [이 섹션](push.md)을 참조하십시오.

:arrow_upper_right:자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html)를 참조하십시오
