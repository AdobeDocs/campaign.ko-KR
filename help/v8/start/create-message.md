---
solution: Campaign v8
product: Adobe Campaign
title: 메시지 시작
description: 메시지 시작
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 4%

---

# 메시지 시작{#gs-ac-audiences}

Adobe Campaign을 사용하면 이메일, SMS, 푸시 알림 및 DM을 비롯한 크로스 채널 캠페인을 전송할 수 있으며 다양한 전용 보고서를 사용하여 효과를 측정할 수 있습니다. 이러한 메시지는 게재를 통해 디자인되고 전송되며 각 수신자에 대해 개인화할 수 있습니다.

핵심 기능에는 메시지 타겟팅, 정의 및 개인화, 커뮤니케이션 실행 및 관련 운영 보고서가 포함됩니다. 기본 기능 액세스 포인트는 게재 도우미입니다. 이 액세스 포인트는 Adobe Campaign에서 다루는 여러 기능으로 이어집니다.

[Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html)에서 게재를 만드는 주요 단계를 알아봅니다.

Adobe Campaign v8에는 다음과 같은 전달 채널이 포함되어 있습니다.

* **이메일 채널**:이메일 게재를 사용하면 개인화된 이메일을 타겟 모집단으로 보낼 수 있습니다. 자세한 내용은 [이 페이지](../send/email.md)를 참조하십시오.

* **DM 채널**:dm 게재를 사용하면 대상 모집단에 대한 데이터가 포함된 추출 파일을 생성할 수 있습니다.  자세한 내용은 [이 페이지](../send/direct-mail.md)를 참조하십시오

* **모바일 채널**:모바일 채널의 게재를 사용하면 개인화된 SMS를 대상 모집단으로 보낼 수 있습니다.  자세한 내용은 [이 페이지](../send/sms.md)를 참조하십시오

* **모바일 애플리케이션 채널**:모바일 앱 게재를 사용하면 iOS 및 Android 시스템에 알림을 전송할 수 있습니다.  자세한 내용은 [이 페이지](../send/push.md)를 참조하십시오

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## 메시지 전송 방법 선택

메시지를 만들고 콘텐츠를 디자인하고 테스트하면 보낼 방법을 선택할 수 있습니다. Campaign은 다음과 같은 기능을 제공합니다.

* 주요 타겟에게 수동으로 메시지 보내기
:[!DNL :arrow_upper_right:]:[메시지 보내는 방법 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)
* [마케팅 캠페인](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html)에 연결된 메시지 보내기
:[!DNL :arrow_upper_right:]:[캠페인 컨텍스트에서 메시지를 보내는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html).
* [워크플로우](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)를 통해 메시지 보내기
:[!DNL :arrow_upper_right:]:[이메일 게재 자동화 방법 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html)
* [이벤트](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html) 에서 메시지 트리거:[!DNL :arrow_upper_right:]: [사용 사례:첨부 파일과 함께 트랜잭션 전자 메일을 보내는 방법 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html)
* 메시지 예약
:[!DNL :arrow_upper_right:]:[사용 사례:생일 전자 메일](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?) 예약 및 전송 방법을 알아봅니다.


## 개인화 추가

Adobe Campaign에서 전달하는 메시지는 다양한 방법으로 개인화할 수 있습니다.

다음을 수행할 수 있습니다.

* 동적 개인화 필드를 삽입합니다.
:[!DNL :arrow_upper_right:]:[Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)에서 개인화 필드를 사용하는 방법을 알아봅니다
* 사전 정의된 개인화 블록 삽입.
:[!DNL :arrow_upper_right:]:개인화 블록이란 무엇이고 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html)에서 사용하는 방법을 알아봅니다
* 조건부 콘텐츠 만들기 :[!DNL :arrow_upper_right:]:[Campaign Classic v7 설명서에 조건부 콘텐츠를 삽입하는 방법 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html)

## 트랜잭션 메시지 보내기

트랜잭션 메시지(메시지 센터)는 트리거 메시지를 관리하기 위해 설계된 캠페인 모듈입니다.

[!DNL :bulb:] 트랜잭션 메시지 기능에 대한 자세한 내용은  [이 섹션을 참조하십시오](../dev/architecture.md#transac-msg-archi)

[!DNL :bulb:] 트랜잭션 메시지를 구성하고 전송하는 단계는  [이 페이지에 자세히 설명되어 있습니다](../send/transactional.md)

:[!DNL :arrow_upper_right:]:[Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=en#transactional-messaging)의 엔드 투 엔드 사용 사례에서 이 기능을 살펴보십시오

## 게재 및 추적 로그

게재가 전송된 후 게재를 모니터링하는 것은 마케팅 캠페인이 효율적이고 고객에게 도달하도록 하는 주요 단계입니다. 게재를 보낸 후 모니터링할 수 있을 뿐만 아니라 게재 실패와 격리를 관리하는 방법을 이해할 수 있습니다.

:[!DNL :arrow_upper_right:]:[이 섹션에서 게재를 모니터링하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages)


**관련 항목**

:[!DNL :arrow_upper_right:]:  [게재 모범 사례](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html)

:[!DNL :arrow_upper_right:]: [테스트 및 이메일 보내기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

:[!DNL :arrow_upper_right:]: [증명 보내기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
