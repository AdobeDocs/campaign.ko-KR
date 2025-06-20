---
title: 메시지 시작
description: 메시지 시작
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: a523e76d-776c-47d3-9c15-34241cee1092
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 73%

---

# 메시지 시작하기 {#gs-ac-msg}

Adobe Campaign에서는 이메일, SMS, 푸시 알림 및 DM 등 크로스 채널 캠페인을 보내고, 다양한 전용 보고서를 사용하여 캠페인의 효과를 측정할 수 있습니다. 이러한 메시지는 게재를 통해 디자인되고 전송되며 각 수신자에 대해 개인화할 수 있습니다.

핵심 기능에는 타기팅, 정의 및 메시지 개인화, 커뮤니케이션 실행 및 관련 운영 보고서가 포함됩니다.

## 활용 사례 {#gs-ac-delivery}

메시지를 보내려면 게재를 만들어야 합니다. 게재 만들기 모드는 사용 사례에 따라 다릅니다.

>[!NOTE]
>
>게재를 만들 때 템플릿을 선택해야 합니다. 각 채널에 기본 템플릿을 사용할 수 있습니다. [이 페이지](../send/create-templates.md)에서 게재 템플릿에 대해 자세히 알아보세요.

1. **일회성 메시지** - 대상자에게 일회성 메시지를 보낼 수 있습니다. [이 섹션](create-message.md)에서 첫 번째 메시지를 보내는 방법을 알아보세요.

   ![](assets/send-email.png)

1. **마케팅 캠페인의 메시지** - [마케팅 캠페인](campaigns.md)의 컨텍스트에서 메시지를 보내고, 승인 프로세스를 정의하고, 통합 대시보드에서 메시지를 보내고, 추적할 수 있습니다. [이 섹션](../../automation/campaigns/marketing-campaign-deliveries.md)에서 방법을 알아보세요.

   ![](assets/deliveries-in-a-campaign.png)

1. **워크플로우의 메시지** - [워크플로우](../config/workflows.md)를 통해 메시지를 보내고 게재를 자동화할 수 있습니다. [이 페이지](../../automation/workflow/delivery.md)에서 방법을 알아보세요.

   ![](assets/send-in-a-wf.png)

1. **트리거된 메시지** - 이벤트에서 [메시지를 트리거](../send/transactional.md)할 수 있습니다. 트랜잭션 메시지(메시지 센터)는 트리거 메시지를 관리하기 위해 고안된 캠페인 모듈입니다. 트랜잭션 메시지를 구성하고 보내는 자세한 단계: [이 페이지](../send/transactional.md)

## 커뮤니케이션 채널 {#gs-channel}

Adobe Campaign v8에는 아래 나열된 게재 채널이 포함되어 있습니다. 환경에서 사용할 수 있는 채널은 계약에 따라 다릅니다. 사용권 계약을 확인하십시오.

* **이메일 채널**: 이메일 게재를 통해 대상 집단에 개인화된 이메일을 전송할 수 있습니다. [자세히 알아보기](../send/email.md)

* **모바일 채널**: 모바일 채널 게재를 통해 대상 집단에 개인화된 모바일 디바이스 메시지를 전송할 수 있습니다. 모바일에서 [SMS](../send/sms/sms.md) 및 [LINE](../send/line.md) 메시지를 보낼 수 있습니다.

* **모바일 응용 프로그램 채널**: Adobe Campaign을 사용하여 전용 앱을 통해 iOS 및 Android 모바일 장치에서 개인화되고 세그먼트화된 [푸시 알림](../send/push.md)을 보낼 수 있습니다. 구성 및 통합 단계를 수행한 뒤에는 iOS 및 Android 게재를 만들고 Adobe Campaign을 사용하여 전송할 수 있습니다. 이미지 또는 비디오가 포함된 리치 알림을 디자인하여 Android 디바이스로 전송할 수도 있습니다.

* **DM 채널**: [DM](../send/direct-mail.md)은(는) DM 공급자와 공유할 외부 파일을 만들고, 개인화하고, 생성할 수 있는 오프라인 채널입니다. 이 채널을 고객 여정의 온라인 및 오프라인 채널 오케스트레이션에 사용할 수 있습니다.

  Adobe Campaign은 DM 게재 준비 시 타겟팅된 프로필과 선택한 연락처 정보(예를 들면 우편 주소)가 있는 파일을 생성합니다. 그 이후에는 이 파일을 다이렉트 메일 공급자에게 보내서 실제 전송을 처리하도록 할 수 있습니다.


* **기타 채널**: Adobe Campaign에는 외부 게재를 만드는 데 사용되는 전화 게재 템플릿도 포함되어 있습니다. 이 채널을 사용하는 경우 출력 파일을 처리하기 위한 전용 방법론을 구현해야 합니다. 구성 단계는 [다이렉트 메일 채널](../send/direct-mail.md)과 동일합니다.

  >[!NOTE]
  >
  >전화 채널은 기본 제공 채널이 아닙니다. 구현하려면 Adobe Consulting 서비스를 받거나 Adobe 파트너가 참여해야 합니다. 자세한 내용은 Adobe 담당자에게 문의하십시오.

  ‘기타’ 유형 게재는 프로세스를 실행하지 않는 특정 기술 템플릿을 사용합니다. 그래서 Adobe Campaign 플랫폼 외부에서 실행되는 마케팅 액션을 관리할 수 있습니다.

  이 채널에 특수한 메커니즘이 있는 것은 아닙니다. Adobe Campaign에서 사용할 수 있는 다른 커뮤니케이션 채널과 마찬가지로 자체 외부 계정 라우팅 옵션, 게재 템플릿 유형, 캠페인 워크플로 활동이 있는 일반적인 채널입니다. 이 채널은 단순 설명 목적으로 설계되었습니다. 예를 들어 Adobe Campaign 이외의 도구에서 수행한 캠페인의 대상을 추적하기 위한 게재를 정의하는 데 사용할 수 있습니다.

## 게재 유형 {#types-of-deliveries}

Campaign에는 세 가지 유형의 게재 개체가 있습니다.

### 단일 게재 {#single-delivery}

**게재**&#x200B;는 한 번 실행되는 독립 실행형 게재 개체입니다. 복제하여 다시 준비할 수도 있지만, 최종 상태(취소됨, 중지됨, 완료됨)에서는 재사용할 수 없습니다.

게재를 만들려면 게재 목록에서 만들거나, [게재](../../automation/workflow/delivery.md) 활동을 통해 워크플로 내에서 만들 수 있습니다.

또한 워크플로는 사용할 채널 유형에 따라 특정한 게재 활동을 제공합니다. 이 활동에 대한 자세한 정보는 [이 섹션](../../automation/workflow/cross-channel-deliveries.md)을 참조하십시오.

### 반복 게재 {#recurring-delivery}

**반복 게재**&#x200B;는 워크플로 컨텍스트에서 사용할 수 있습니다. 활동을 실행할 때마다 새 게재를 만들 수 있는 방법입니다. 그러면 반복 작업 때문에 새 게재를 만들 필요가 없습니다. 예를 들어, 한 달에 한 번 이 유형의 활동을 실행하면 1년 후에는 게재가 12개 존재하게 됩니다.

반복 게재는 [반복 게재 활동](../../automation/workflow/recurring-delivery.md)을 통해 워크플로 내에 만들어집니다. 이 활동을 사용하는 예시는 [타기팅 워크플로에서 반복 게재 만들기](../../automation/workflow/send-a-birthday-email.md) 섹션에 나와 있습니다.

### 지속적인 게재 {#continuous-delivery}

**지속적인 게재**&#x200B;는 워크플로 컨텍스트에서 사용할 수 있습니다. 기존 게재에 새 수신자를 추가할 수 있으므로 게재를 실행할 때마다 새로운 게재를 만들 필요가 없습니다.

게재에 있는 정보(콘텐츠, 이름 등)가 변경되면 게재 실행 시 새 게재 개체를 만듭니다. 변경된 정보가 없으면 동일한 게재 개체를 재사용하고 게재 및 추적 로그를 동일한 개체에 추가합니다.

예를 들어 한 달에 한 번 이 유형의 활동을 실행하면 1년 후에도 게재가 한 개만 존재합니다(게재를 변경하지 않은 경우).

지속적인 게재는 워크플로 내에서 [지속적인 게재 활동](../../automation/workflow/continuous-delivery.md)을 통해 만들어집니다.

## Personalization 기능 {#personalization}

Adobe Campaign에서 제공하는 메시지는 다양한 방식으로 개인화할 수 있습니다. [개인화 기능에 대해 자세히 알아보기](../send/personalize.md)

다음을 수행할 수 있습니다.

* 동적 개인화 필드를 삽입합니다. [자세히 알아보기](../send/personalization-fields.md)
* 사전 정의된 개인화 블록을 삽입합니다. [자세히 알아보기](../send/personalization-blocks.md)
* 조건부 콘텐츠 만들기 [자세히 알아보기](../send/conditions.md)


## 추적 및 모니터링 {#gs-tracking-logs}

메시지를 게재한 후 마케팅 캠페인이 효율적이고 고객에게 도달하는지 확인하는 데 있어 게재 모니터링은 중요한 단계입니다. 게재 후 모니터링은 물론 게재 실패와 검역된 메시지가 어떻게 관리되는지 파악할 수 있습니다.

게재 모니터링 방법: [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=ko#sending-messages){target="_blank"}
