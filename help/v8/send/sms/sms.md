---
title: Adobe Campaign으로 SMS 보내기
description: Campaign에서 SMS 시작
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: bb77b915f50b31d8d91e25da6fa86aa15b03bba4
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 17%

---

# SMS 시작 {#gs-sms-channel}

Adobe Campaign을 사용하면 모바일에서 개인화된 SMS를 제공할 수 있습니다.

SMS 메시지의 경우 텍스트 포맷으로만 메시지를 만들고 수정하고 개인화할 수 있습니다. SMS 메시지를 보내기 전에 미리 볼 수도 있습니다.

>[!NOTE]
>
>Adobe Campaign을 사용하여 [LINE](../../send/line.md) 메시지와 텍스트 및/또는 이미지 및 링크를 보낼 수도 있습니다.

Adobe Campaign을 사용하여 휴대폰에 SMS를 게재하려면 다음이 필요합니다.

* **[!UICONTROL Mobile (SMS)]** 채널 또는 **[!UICONTROL LINE]** 채널에 구성된 외부 계정.
* 이 외부 계정에 올바르게 연결된 SMS 게재 템플릿입니다.

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
