---
title: 메시지 시작
description: 메시지 시작
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 7f6c394f56d517c0a675e0fd2341bb6ef98044f0
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 29%

---

# 메시지 시작 {#gs-ac-audiences}

## 게재 채널 {#gs-ac-channels}

Adobe Campaign에서는 이메일, SMS, 푸시 알림 및 DM 등 크로스 채널 캠페인을 보내고, 다양한 전용 보고서를 사용하여 캠페인의 효과를 측정할 수 있습니다. 이러한 메시지는 게재를 통해 디자인되고 전송되며 각 수신자에 대해 개인화할 수 있습니다.

핵심 기능에는 타기팅, 정의 및 메시지 개인화, 커뮤니케이션 실행 및 관련 운영 보고서가 포함됩니다. 주요 기능 액세스 포인트는 게재 도우미입니다. 이 액세스 포인트는 Adobe Campaign에서 다루는 다양한 기능으로 이어집니다.

Adobe Campaign v8에는 다음과 같은 게재 채널이 포함되어 있습니다.

* **이메일 채널**: 이메일 게재를 사용하면 개인화된 이메일을 대상 모집단으로 보낼 수 있습니다. [자세히 알아보기](#gs-channel-email)

* **모바일 채널**: 모바일 채널 게재는 모바일 장치의 개인화된 메시지를 대상 모집단으로 보낼 수 있습니다. [자세히 알아보기](#gs-channel-sms)

* **모바일 애플리케이션 채널**: 모바일 앱 게재를 사용하면 iOS 및 Android 디바이스에 알림을 전송할 수 있습니다. [자세히 알아보기](#gs-channel-push)

* **다이렉트 메일 채널**: DM 게재는 대상 모집단에서 데이터를 포함하는 추출 파일을 생성할 수 있습니다. [자세히 알아보기](#gs-channel-direct)


  다른 채널은에 설명되어 있습니다. [이 섹션](#other-channels).

  >[!NOTE]
  >
  >사용 가능한 채널 수는 계약에 따라 다릅니다. 사용권 계약을 확인하십시오.

## 채널 선택 {#gs-channel}

### 이메일 채널 {#gs-channel-email}

다음 [이메일 채널](../send/direct-mail.md) 은 Adobe Campaign의 핵심 채널 중 하나이며, 이를 통해 특정 타겟에게 개인화된 이메일을 예약하고 보낼 수 있습니다.

다음과 같이 다양한 유형의 이메일을 보낼 수 있습니다.

* 단일 전송 이메일: 정의된 타겟에게 한 번 전송할 수 있는 이메일. 일반적으로 한 번만 작성하여 전송하는 특정 콘텐츠(뉴스레터, 프로모션 이메일 등)를 홍보하는 데 사용됩니다.
* 반복 이메일: 캠페인에서 동일한 이메일을 정기적으로 보내고 각 보내기 및 보고서를 정기적으로 집계합니다. 동일한 이메일이 전송되지만 일반적으로 전송 날짜의 적격한 타겟을 기준으로 다른 타겟으로 전송됩니다. 일반적인 예로는 생일 이메일이 있습니다. 자세한 내용은 다음을 참조하십시오. [반복 게재](../../automation/workflow/recurring-delivery.md).
* 트랜잭션 이메일: 고객의 비헤이비어에 따라 트리거되는 단일 이메일. 을(를) 참조하십시오 [트랜잭션 메시지](../send/transactional.md).

게재 사용 및 권장 사항에 대해 알아보려면 Adobe Campaign Classic 를 참조하십시오. [게재 모범 사례](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html#sending-messages){target="_blank"}

다양한 유형의 게재에 대한 자세한 내용은 [이 섹션](#types-of-deliveries).

### 모바일 채널 {#gs-channel-sms}

Adobe Campaign을 통해 다음을 제공할 수 있습니다. [SMS](../send/sms.md) 및 [LINE](../send/line.md) 모바일 메시지.

SMS 메시지의 경우, 텍스트 형식으로만 메시지를 만들고, 수정하고, 개인화할 수 있습니다. SMS 메시지를 보내기 전에 미리 볼 수도 있습니다.

LINE 메시지의 경우 텍스트나 이미지 및 링크를 보낼 수 있습니다.

휴대폰에 SMS 또는 LINE 메시지를 게재하려면 다음이 필요합니다.

* 에 구성된 외부 계정 **[!UICONTROL Mobile (SMS)]** 채널 또는 **[!UICONTROL LINE]** 채널.
* 이 외부 계정에 올바르게 연결된 SMS 또는 LINE 게재 템플릿입니다.


### 푸시 알림 채널 {#gs-channel-push}

Adobe Campaign을 사용하여 개인화되고 세그먼트화된 데이터를 보낼 수 있습니다 [푸시 알림](../send/push.md) iOS 및 Android 모바일 장치에서 전용 앱을 통해 액세스합니다. 구성 및 통합 단계를 수행하면 iOS 및 Android 게재를 만들고 Adobe Campaign을 사용하여 전송할 수 있습니다. 이미지 또는 비디오가 포함된 풍부한 알림을 디자인하여 Android 장치로 전송할 수도 있습니다.

### 다이렉트 메일 채널 {#gs-channel-direct}

[다이렉트 메일](../send/direct-mail.md) 는 DM 공급자와 공유할 외부 파일을 만들고, 개인화하고, 생성할 수 있는 오프라인 채널입니다. 이 채널을 사용하여 고객 여정의 온라인 및 오프라인 채널을 조정합니다.

Adobe Campaign은 DM 게재 준비 시 타겟팅 프로필과 선택한 연락처 정보(예를 들면 우편 주소)가 있는 파일을 생성합니다. 그런 다음 실제 전송을 처리할 DM 공급자에게 이 파일을 보낼 수 있습니다.


### 기타 채널 {#other-channels}

Adobe Campaign에는 외부 게재를 만드는 데 사용되는 전화 게재 템플릿도 포함되어 있습니다. 이 채널을 사용하면 출력 파일을 처리하는 전용 방법론을 구현할 수 있습니다. 구성 단계는 와 동일합니다 [다이렉트 메일 채널](../send/direct-mail.md).

>[!NOTE]
>
>전화 채널은 기본 제공 채널이 아닙니다. 구현을 위해서는 Adobe 컨설팅이나 Adobe 파트너가 참여해야 합니다. 자세한 내용은 Adobe 담당자에게 문의하십시오.

기타 유형 게재는 프로세스를 실행하지 않는 특정 기술 템플릿을 사용합니다. 이렇게 하면 Adobe Campaign 플랫폼 외부에서 실행되는 마케팅 작업을 관리할 수 있습니다.

이 채널에는 특정 메커니즘이 없습니다. Adobe Campaign에서 사용할 수 있는 다른 통신 채널과 마찬가지로 자체 외부 계정 라우팅 옵션, 게재 템플릿 유형 및 캠페인 워크플로우 활동이 있는 일반 채널입니다. 이 채널은 설명 목적으로만 설계되었습니다. 예를 들어 Adobe Campaign 이외의 도구에서 수행된 캠페인의 대상을 추적하려는 게재를 정의할 수 있습니다.

## 게재 유형 선택 {#types-of-deliveries}

Campaign에는 세 가지 유형의 게재 개체가 있습니다.

### 단일 게재 {#single-delivery}

A **게재** 는 한 번 실행되는 독립 실행형 게재 개체입니다. 복제하여 다시 준비할 수도 있지만, 최종 상태(취소, 정지, 종료)인 한 재사용할 수 없다.

게재 목록에서 또는 을 통해 워크플로우 내에서 게재를 만들 수 있습니다. [게재](../../automation/workflow/delivery.md) 활동.

또한 워크플로는 사용하려는 채널 유형에 따라 특정 게재 활동을 제공합니다. 이러한 활동에 대한 자세한 내용은 [이 섹션](../../automation/workflow/cross-channel-deliveries.md).

### 반복 게재 {#recurring-delivery}

A **반복 게재** 은 워크플로우의 컨텍스트에서 사용할 수 있습니다. 활동을 실행할 때마다 새 게재를 만들 수 있습니다. 이를 통해 반복 작업을 위해 새 게재를 만들 필요가 없습니다. 예를 들어, 한 달에 한 번 이 유형의 활동을 실행하면 1년 후에 12건의 게재가 완료됩니다.

반복 게재는 다음을 통해 워크플로우 내에서 만들어집니다. [반복 게재 활동](../../automation/workflow/recurring-delivery.md). 사용 중인 이 활동의 예는 이 섹션에 나와 있습니다. [타겟팅 워크플로우에서 반복 게재 만들기](../../automation/workflow/send-a-birthday-email.md).

### 지속적인 게재 {#continuous-delivery}

A **연속 게재** 은 워크플로우의 컨텍스트에서 사용할 수 있습니다. 기존 게재에 새 수신자를 추가할 수 있으므로 실행될 때마다 새 게재를 만들 필요가 없습니다.

게재의 정보(콘텐츠, 이름 등)가 변경되면 게재 실행 시 새 게재 개체가 생성됩니다. 변경된 정보가 없으면 동일한 게재 개체가 재사용되고 게재 및 추적 로그가 동일한 개체에 추가됩니다.

예를 들어, 한 달에 한 번 이 유형의 활동을 실행하면 1년 후에 한 번의 게재가 제공됩니다(게재를 변경하지 않은 경우).

연속 게재는 다음을 통해 워크플로우 내에서 생성됩니다. [지속적인 게재 활동](../../automation/workflow/continuous-delivery.md).


## 메시지를 보내는 방법 선택{#gs-send-msg}

메시지가 만들어지고 컨텐츠가 디자인되고 테스트되면 메시지 전송 방법을 선택할 수 있습니다. Campaign은 다음과 같은 여러 가지 기능을 제공합니다.

* 주요 타겟에게 수동으로 메시지 보내기

  ![](assets/send-email.png)

  [이 섹션](../send/send.md)에서 메시지를 보내는 방법을 알아봅니다.

* [마케팅 캠페인](campaigns.md)에 연결된 메시지 보내기

  ![](assets/deliveries-in-a-campaign.png)

  [이 섹션](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=ko){target="_blank"}에서는 캠페인 컨텍스트에 맞춘 메시지를 보내는 방법을 알아봅니다.

* [워크플로우](../config/workflows.md)를 통해 메시지 보내기

  ![](assets/send-in-a-wf.png)

   [이 페이지](../../automation/workflow/delivery.md)에서는 이메일 게재를 자동화하는 방법을 알아봅니다.

* 이벤트를 통한 [메시지 트리거](../send/transactional.md)

  트랜잭션 메시지(메시지 센터)는 트리거 메시지를 관리하기 위해 고안된 캠페인 모듈입니다.

  트랜잭션 메시지 기능 자세히 알아보기: [이 섹션](../architecture/architecture.md#transac-msg-archi)

  트랜잭션 메시지를 구성하고 보내는 자세한 단계: [이 페이지](../send/transactional.md)

* 메시지 예약

  ![](assets/schedule-send.png)

  에서 게재 전송을 예약하는 방법에 대해 알아봅니다. [이 페이지](../send/configure-and-send.md)

  다음도 참조하십시오 [사용 사례: 생일 축하 이메일을 예약하고 보내는 방법 알아보기](../../automation/workflow/send-a-birthday-email.md)


## 개인화 추가{#personalization}

Adobe Campaign에서 제공하는 메시지는 다양한 방식으로 개인화할 수 있습니다. [개인화 기능에 대해 자세히 알아보기](../send/personalize.md)

다음을 수행할 수 있습니다.

* 동적 개인화 필드를 삽입합니다. [자세히 알아보기](../send/personalization-fields.md)
* 사전 정의된 개인화 블록을 삽입합니다. [자세히 알아보기](../send/personalization-blocks.md)
* 조건부 콘텐츠 만들기 [자세히 알아보기](../send/conditions.md)


## 게재 및 추적 로그{#gs-tracking-logs}

메시지를 게재한 후 마케팅 캠페인이 효율적이고 고객에게 도달하는지 확인하는 데 있어 게재 모니터링은 중요한 단계입니다. 게재 후 모니터링은 물론 게재 실패와 검역된 메시지가 어떻게 관리되는지 파악할 수 있습니다.

[Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=ko#sending-messages){target="_blank"}에서 게재를 모니터링하는 방법을 알아봅니다.

