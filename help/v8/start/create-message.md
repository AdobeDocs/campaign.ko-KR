---
product: Adobe Campaign
title: 메시지 시작
description: 메시지 시작
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 0566d40370a3e14d5205861509f7c1ae8cb4b22d
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 83%

---

# 메시지 시작{#gs-ac-audiences}

Adobe Campaign에서는 이메일, SMS, 푸시 알림 및 DM 등 크로스 채널 캠페인을 보내고, 다양한 전용 보고서를 사용하여 캠페인의 효과를 측정할 수 있습니다. 이러한 메시지는 게재를 통해 디자인되고 전송되며 각 수신자에 대해 개인화할 수 있습니다.

핵심 기능에는 타기팅, 정의 및 메시지 개인화, 커뮤니케이션 실행 및 관련 운영 보고서가 포함됩니다. 주요 기능 액세스 포인트는 게재 도우미입니다. 이 액세스 포인트는 Adobe Campaign에서 다루는 다양한 기능으로 이어집니다.

[Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=ko)에서 게재를 만드는 주요 단계를 알아볼 수 있습니다.

Adobe Campaign v8에는 다음과 같은 게재 채널이 포함되어 있습니다.

* **이메일 채널**: 이메일 게재를 사용하면 개인화된 이메일을 대상 모집단으로 보낼 수 있습니다. [이 페이지](../send/email.md)에서 자세히 알아보십시오.

* **DM 채널**: DM 게재는 대상 모집단에서 데이터를 포함하는 추출 파일을 생성할 수 있습니다.  [이 페이지](../send/direct-mail.md)에서 자세히 알아보기

* **모바일 채널**: 모바일 채널 게재는 개인화된 SMS를 대상 모집단으로 보낼 수 있습니다.  [이 페이지](../send/sms.md)에서 자세히 알아보기

* **모바일 앱 채널**:모바일 앱 게재를 사용하면 iOS 및 Android 시스템에 알림을 전송할 수 있습니다.  [이 페이지](../send/push.md)에서 자세히 알아보기

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## 메시지를 보내는 방법 선택

메시지가 만들어지고 컨텐츠가 디자인되고 테스트되면 메시지 전송 방법을 선택할 수 있습니다. Campaign은 다음과 같은 여러 가지 기능을 제공합니다.

* 주요 타겟에게 수동으로 메시지 보내기

   ![](assets/send-email.png)

   [!DNL :arrow_upper_right:]  [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html?lang=ko){target=&quot;_blank&quot;}에서 메시지를 보내는 방법을 알아봅니다

* [마케팅 캠페인](campaigns.md)에 연결된 메시지 보내기

   ![](assets/deliveries-in-a-campaign.png)

   [!DNL :arrow_upper_right:]  [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=ko){target=&quot;_blank&quot;}에서 캠페인 컨텍스트에서 메시지를 보내는 방법을 알아봅니다

* [워크플로우](../config/workflows.md)를 통해 메시지 보내기

   ![](assets/send-in-a-wf.png)

   [!DNL :arrow_upper_right:]  [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html?lang=ko){target=&quot;_blank&quot;}에서 전자 메일 게재를 자동화하는 방법을 알아봅니다

* 이벤트를 통한 [메시지 트리거](../send/transactional.md)
   [!DNL :arrow_upper_right:] [사용 사례:파일을 첨부한 트랜잭션 이메일을 보내는 방법 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=en){target=&quot;_blank&quot;}

* 메시지 예약

   ![](assets/schedule-send.png)

   [!DNL :arrow_upper_right:] [사용 사례:생일 축하 이메일을 예약하고 보내는 방법 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=ko){target=&quot;_blank&quot;}


## 개인화 추가

Adobe Campaign에서 제공하는 메시지는 다양한 방식으로 개인화할 수 있습니다.

다음을 수행할 수 있습니다.

* 동적 개인화 필드를 삽입합니다.
   [!DNL :arrow_upper_right:] 개인화 필드를 사용하는 방법: [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html?lang=ko){target=&quot;_blank&quot;}
* 사전 정의된 개인화 블록을 삽입합니다.
   [!DNL :arrow_upper_right:] 개인화 블록의 정의 및 사용 방법: [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html?lang=ko){target=&quot;_blank&quot;}
* 조건부 콘텐츠를 만듭니다.
   [!DNL :arrow_upper_right:] 조건부 콘텐츠를 삽입하는 방법: [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html?lang=ko){target=&quot;_blank&quot;}

## 트랜잭션 메시지를 보냅니다.

트랜잭션 메시지(메시지 센터)는 트리거 메시지를 관리하기 위해 고안된 캠페인 모듈입니다.

[!DNL :bulb:] 트랜잭션 메시지 기능 자세히 알아보기: [이 섹션](../dev/architecture.md#transac-msg-archi)

[!DNL :bulb:] 트랜잭션 메시지를 구성하고 보내는 자세한 단계: [이 페이지](../send/transactional.md)

[!DNL :arrow_upper_right:] 이 기능의 엔드 투 엔드 활용 사례: [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=ko){target=&quot;_blank&quot;}

## 게재 및 추적 로그

메시지를 게재한 후 마케팅 캠페인이 효율적이고 고객에게 도달하는지 확인하는 데 있어 게재 모니터링은 중요한 단계입니다. 게재 후 모니터링은 물론 게재 실패와 검역된 메시지가 어떻게 관리되는지 파악할 수 있습니다.

[!DNL :arrow_upper_right:]  [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html#sending-messages){target=&quot;_blank&quot;}에서 게재를 모니터링하는 방법을 알아봅니다


**Campaign Classic** v7 설명서의 관련 항목:

[!DNL :arrow_upper_right:]  [게재 우수 사례](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=ko){target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:]  [전자 메일](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html){target=&quot;_blank&quot;} 테스트 및 보내기

[!DNL :arrow_upper_right:]  [증명](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=ko) 보내기{target=&quot;_blank&quot;}
