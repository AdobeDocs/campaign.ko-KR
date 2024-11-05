---
title: Adobe Campaign으로 SMS 보내기
description: Campaign에서 SMS 시작
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 70af3bceee67082d6a1bb098e60fd2899dc74600
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 4%

---

# SMS 시작 {#gs-sms-channel}

Adobe Campaign을 사용하여 개인화된 SMS 메시지를 보냅니다.

>[!NOTE]
>
>Adobe Campaign을 사용하면 **NMAC(Adobe Campaign Mobile App Channel)** 옵션을 통해 모바일에서 푸시 알림을 제출할 수도 있습니다. [이 섹션](../push.md)에서 자세히 알아보십시오.

SMS의 사용 편의성과 단순성은 수십억 개의 단말기에 대한 견고성과 독보적인 호환성에 더해 매우 가치 있는 커뮤니케이션 채널입니다.

SMS를 보내는 주요 방법에는 두 가지가 있습니다.

* 휴대폰에서 수동으로 보냅니다. 사람들 간에 직접 소통하기 위해 사용하는 일반적인 방법입니다.
* 인터넷에서 보내 Adobe Campaign이 메시지를 보낼 때 사용하는 방식입니다. 이를 위해서는 인터넷에서 모바일 네트워크로 연결하는 SMS 서비스 공급자가 필요합니다.

SMS 게재를 구성, 전송 및 모니터링하는 단계는 이 설명서에서 확인할 수 있습니다.

* **SMS 채널 구성**

먼저 [중간 소싱 인프라](sms-mid-sourcing.md)에서 SMS 채널을 구성해야 합니다.

<!--The steps depend on the platform: either you have [a standalone instance](sms-standalone-instance.md) or you are in [a mid-sourcing infrastructure](sms-mid-sourcing.md).-->

이 구성의 경우 [SMPP 외부 계정 매개 변수](smpp-external-account.md) 및 [SMS 채널 특성](sms-channel.md)을 이해해야 합니다.

이 설정 후 [SMPP 연결을 확인하고 필요한 경우 문제를 해결하는 방법을 알아보세요](smpp-connection.md).

* **첫 번째 SMS 게재 만들기**

SMS 게재 구성을 시작하려면 다음을 수행하십시오.

1. 게재를 만들고 [SMS 게재 설정](sms-delivery-settings.md)을(를) 채웁니다.

1. 게재의 [콘텐츠 정의](sms-content.md),

1. [대상자를 선택하십시오](sms-audience.md).

대상자를 정의하는 단계는 [이 페이지](../../audiences/create-audiences.md)에 자세히 설명되어 있습니다.

* **SMS 확인 및 보내기**

게재 생성 후:

1. 렌더링 및 콘텐츠의 유효성을 검사하려면 [증명을 보내세요](sms-proofs.md),

1. 그런 다음 [최종 대상자에게 보내기](sms-send.md)합니다.

* **SMS 모니터링 및 추적**

전송 후 [SMS를 모니터링하고 추적하는 방법을 알아보세요](sms-monitor.md).
