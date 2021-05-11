---
solution: Campaign
product: Adobe Campaign
title: 메시지 시작
description: 메시지 시작
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
translation-type: tm+mt
source-git-commit: 3fe4156149e9ff8724dd1ff5fc17b538e6055ef8
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 3%

---

# 메시지 시작하기{#gs-ac-audiences}

Adobe Campaign을 사용하면 이메일, SMS, LINE 메시지, 푸시 알림 및 다이렉트 메일을 비롯한 크로스 채널 캠페인을 전송할 수 있으며 다양한 전용 보고서를 사용하여 효과를 측정할 수 있습니다. 이러한 메시지는 배달을 통해 디자인되고 전송되며 각 수신자에 대해 개인화할 수 있습니다.

핵심 기능에는 타깃팅, 정의 및 메시지 개인화, 커뮤니케이션 실행 및 관련 운영 보고서가 포함됩니다. 주요 기능 액세스 포인트는 배달 도우미입니다. 이 액세스 포인트는 Adobe Campaign에서 다루는 다양한 기능으로 이어집니다.

[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html)에서 배달을 만드는 주요 단계를 알아봅니다.

Adobe Campaign v8에는 다음과 같은 전달 채널이 포함되어 있습니다.

* **이메일 채널**:이메일 배달을 사용하면 개인화된 이메일을 타겟 모집단으로 보낼 수 있습니다. [이 페이지](../send/email.md)에서 자세히 알아보십시오.

* **DM 채널**:직접 메일 배달에서는 대상 모집단에서 데이터를 포함하는 추출 파일을 생성할 수 있습니다.  [이 페이지](../send/direct-mail.md)에서 자세히 알아보기

* **모바일 채널**:모바일 채널을 통해 전달하면 개인화된 SMS를 대상 모집단으로 보낼 수 있습니다.  [이 페이지](../send/sms.md)에서 자세히 알아보기

* **모바일 애플리케이션 채널**:모바일 앱 게재를 사용하면 iOS 및 Android 시스템에 알림을 전송할 수 있습니다.  [이 페이지](../send/push.md)에서 자세히 알아보기

* **LINE 채널**:LINE 배달 기능을 사용하면 모든 스마트폰에서 사용할 수 있는 인스턴트 메시징 애플리케이션인 LINE에서 메시지를 보낼 수 있습니다. [이 페이지](../send/line.md)에서 자세히 알아보기

## 메시지를 보내는 방법 선택

메시지가 만들어지고 컨텐츠가 디자인되고 테스트되면 메시지 전송 방법을 선택할 수 있습니다. Campaign은 다음과 같은 일련의 기능을 제공합니다.

* 메시지를 수동으로 기본 타겟으로 보내기
:arrow_upper_right:[메시지를 보내는 방법 학습](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)
* [마케팅 캠페인](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html)에 연결된 메시지 보내기
:arrow_upper_right:[캠페인](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html) 컨텍스트에서 메시지를 보내는 방법을 알아봅니다.
* [워크플로](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)를 통해 메시지 보내기
:arrow_upper_right:[이메일 배달 자동화 방법 학습](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html)
* [이벤트](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html) 에서 메시지 트리거: arrow_upper_right: [사용 사례:첨부 파일이 포함된 트랜잭션 이메일을 보내는 방법에 대해 알아봅니다.](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html)
* 메시지 예약
:arrow_upper_right:[사용 사례:생일 이메일 예약 및 보내는 방법 학습](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?)


## 개인화 추가

Adobe Campaign에서 제공하는 메시지는 다양한 방식으로 개인화할 수 있습니다.

다음을 수행할 수 있습니다.

* 동적 개인화 필드를 삽입합니다.
:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)에서 개인화 필드를 사용하는 방법에 대해 알아봅니다.
* 사전 정의된 개인화 블록 삽입.
:arrow_upper_right:개인화 블록이란 무엇이고, 이를 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html)에서 사용하는 방법에 대해 알아봅니다.
* 조건부 콘텐츠 만들기 :arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html)에 조건부 컨텐트를 삽입하는 방법에 대해 알아봅니다.

## 트랜잭션 메시지 보내기

트랜잭션 메시지(메시지 센터)는 트리거 메시지를 관리하기 위해 고안된 캠페인 모듈입니다.

: 전구:[이 섹션](../dev/architecture.md#transac-msg-archi)의 트랜잭션 메시지 기능에 대한 자세한 내용

: 전구:트랜잭션 메시지를 구성하고 전송하는 단계는 [이 페이지](../send/transactional.md)에 자세히 설명되어 있습니다.

:arrow_upper_right:이 기능을 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=en#transactional-messaging)의 엔드 투 엔드 사용 사례에서 알아봅니다.

## 배달 및 추적 로그

마케팅 캠페인이 효율적이고 고객에게 도달하는지 확인하는 데 있어 배송 모니터링은 중요한 단계입니다. 배송 후 모니터링은 물론 배달 실패와 검역소가 어떻게 관리되는지 파악할 수 있습니다.

:arrow_upper_right:[이 섹션에서 배달을 모니터링하는 방법 학습](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages)


**관련 항목**

:arrow_upper_right: [배달 우수 사례](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html)

:arrow_upper_right: [테스트 및 이메일](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html) 보내기

:arrow_upper_right: [교정본을 보내기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
