---
title: 캠페인 트랜잭션 메시지
description: 트랜잭션 메시지 시작
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
source-git-commit: f75b95faa570d7c3f59fd8fb15692d3c3cbe0d36
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 0%

---

# 트랜잭션 메시지 시작{#send-transactional-messages}

트랜잭션 메시지(메시지 센터)는 트리거 메시지를 관리하기 위해 고안된 캠페인 모듈입니다. 이러한 알림은 정보 시스템에서 트리거된 이벤트에서 생성되며 송장, 주문 확인, 배송 확인, 암호 변경, 제품 불가능 알림, 계정 명세서, 웹 사이트 계정 생성 등이 될 수 있습니다.

>[!NOTE]
>
>Managed Cloud Services 사용자는 [Adobe에 문의](../start/campaign-faq.md#support){target="_blank"}하여 환경에서 Campaign 트랜잭션 메시지를 구성하세요.

트랜잭션 메시지는 다음을 전송하는 데 사용됩니다.

* 주문 확인 또는 암호 재설정 등의 알림
* 고객 행동에 대한 개별 실시간 응답
* 비프로모션 콘텐츠

트랜잭션 메시지 설정은 [이 섹션](../config/transactional-msg-settings.md)에 자세히 설명되어 있습니다.

[이 페이지](../architecture/architecture.md#transac-msg-archi)의 트랜잭션 메시지 아키텍처를 이해합니다.

## 트랜잭션 메시지 작동 원리 {#transactional-messaging-operating-principle}

Adobe Campaign 트랜잭션 메시지 모듈은 변경할 이벤트를 개인화된 트랜잭션 메시지로 반환하는 정보 시스템에 통합됩니다. 이러한 메시지는 이메일, SMS 또는 푸시 알림을 통해 개별적으로 또는 일괄적으로 전송할 수 있습니다.

예를 들어 고객이 제품을 구매할 수 있는 웹 사이트를 보유한 회사라고 가정해 보겠습니다.

Adobe Campaign을 사용하면 장바구니에 제품을 추가한 고객에게 알림 이메일을 보낼 수 있습니다. 둘 중 한 명이 구매(캠페인 이벤트를 트리거하는 외부 이벤트)를 수행하지 않고 웹 사이트를 떠나면 장바구니 포기 이메일이 자동으로 전송됩니다(트랜잭션 메시지 게재).

이를 실행하는 주요 단계는 아래에 자세히 설명되어 있습니다.

1. [이벤트 형식을 만듭니다](#create-event-types).
1. [메시지 템플릿을 만들고 디자인합니다](transactional-template.md#create-message-template). 이 단계에서 메시지에 이벤트를 연결해야 합니다.
1. [메시지를 테스트합니다](transactional-template.md#test-message-template).
1. [메시지 템플릿을 게시](transactional-template.md#publish-message-template)합니다.

트랜잭션 메시지 템플릿을 디자인하고 게시하면 해당 이벤트가 트리거되면 PushEvent 및 PushEvents [SOAP 메서드](../send/event-description.md)를 통해 관련 데이터가 Campaign으로 전송되고 대상 수신자에게 게재가 전송됩니다.

## 이벤트 유형 만들기 {#create-event-types}

각 이벤트를 개인화된 메시지로 변경하려면 먼저 **이벤트 유형**&#x200B;을 만들어야 합니다.

[메시지 템플릿을 만들](#create-message-template) 때 보낼 메시지와 일치하는 이벤트 유형을 선택합니다.

>[!CAUTION]
>
>메시지 템플릿에서 이벤트 유형을 사용하려면 먼저 이벤트 유형을 만들어야 합니다.

Adobe Campaign에서 처리할 이벤트 유형을 만들려면 아래 단계를 수행합니다.

1. Campaign 탐색기의 **[!UICONTROL Administration > Platform > Enumerations]** 폴더를 찾습니다.
1. 목록에서 **[!UICONTROL Event type]** 열거형을 선택합니다.
1. 열거형 값을 만들려면 **[!UICONTROL Add]**&#x200B;을(를) 클릭합니다. 주문 확인, 암호 변경, 주문 게재 변경 등이 될 수 있습니다.

   ![](assets/messagecenter_eventtype_enum_001.png)

   >[!CAUTION]
   >
   >각 이벤트 형식은 **[!UICONTROL Event type]** 열거형의 값과 일치해야 합니다.

1. 항목별 목록 값이 생성되면 로그오프한 후 인스턴스에 다시 로그온하여 생성을 유효화합니다.

>[!NOTE]
>
>[열거형](../config/enumerations.md)에 대해 자세히 알아보세요.

다음 단계에서는 [트랜잭션 메시지용 템플릿을 만들고 게시](transactional-template.md)하는 방법을 알아봅니다.
