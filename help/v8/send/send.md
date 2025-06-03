---
title: 이메일 전송 및 모니터링
description: Adobe Campaign을 사용하여 이메일을 전송하는 범위와 특성에 대해 알아봅니다
feature: Email
role: Data Engineer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 2%

---


# 이메일 전송 및 모니터링  {#send-and-monitor-emails}

게재가 구성되어 전송할 준비가 되면 게재 분석을 실행했는지 확인합니다. [자세히 알아보기](delivery-analysis.md)

완료되면 게재를 확인하여 메시지 게재를 시작합니다.

이 게재의 세부 정보 또는 게재 목록을 통해 액세스할 수 있는 **게재** 탭에서 게재 실행을 추적합니다.

## 이메일 모니터링 {#email-monitoring}

메시지가 전송되면 **게재 대시보드**&#x200B;에서 게재 상태를 확인하고 게재 로그 및 보고서에 액세스하여 메시지가 올바르게 전송되었는지 확인하십시오.

게재 대시보드에서 처리된 메시지 및 게재 감사 로그를 확인할 수 있습니다. 게재 로그에서 메시지 상태를 제어할 수도 있습니다.

>[!NOTE]
>
>게재 상태는 실시간으로 표시되지 않습니다. 전자 메일 피드백 서비스 [에 대한 자세한 내용은 이 섹션](#email-feedback-service)을 참조하세요.


[Campaign Classic v7 설명서에서 게재 모니터링에 대해 자세히 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target="_blank"}

## 캠페인 MTA {#mta}

Campaign v8 MTA(Mail Transfer Agent)는 최적의 전달성, 신뢰도, 처리량, 보고, 바운스 처리, IP 램프 업 및 연결 설정 관리를 가능하게 하는 동급 최고의 전송 인프라를 제공합니다.

모든 Campaign v8 고객이 사용할 수 있는 이 제품은 확장성과 높은 게재 처리량을 보장하며 더 많은 이메일을 더 빨리 보낼 수 있습니다. 이는 인터넷 서비스 공급자의 피드백을 기반으로 이메일 전송 설정을 실시간으로 변경하는 새로운 적응형 전달 기술로 달성할 수 있습니다.

### 이점

Adobe Campaign은 SparkPost의 상업용 이메일 MTA(**모멘텀**)을 실행하는 MTA(메일 전송 에이전트)를 사용합니다.

모멘텀은 발송자가 최적의 받은 편지함 게재 비율을 달성하고 유지하는 데 도움이 되는 자동화된 게재 능력 최적화 기능과 더 스마트한 바운스 처리를 포함하는 혁신적인 고성능 MTA 기술을 나타냅니다.

* MTA는 전체 처리량 속도의 대폭적인 증가와 소프트 바운스의 대폭적인 감소를 허용한다.
* 최신 MTA 기술을 사용하여 이메일 게재에 최적의 처리량 속도를 제공합니다.
* 또한 수신되는 피드백에 즉시 자동으로 적용되므로 실시간 게재 데이터를 통해 보다 정확하고 지능적인 이메일 게재를 보장합니다.

### 바운스 자격 조건

**동기** 게재 실패 오류 메시지의 경우 MTA가 바운스 유형 및 자격을 결정하고 해당 정보를 Campaign으로 다시 보냅니다.

MTA는 SMTP 바운스를 인증하고 캠페인 바운스 사유 및 자격에 매핑된 바운스 코드 형태로 해당 자격을 Campaign으로 다시 보냅니다.

>[!NOTE]
>
>현재 **비동기** 바운스는 **[!UICONTROL Inbound email]** 규칙을 통해 inMail 프로세스에 의해 검증됩니다.

[이 섹션](delivery-failures.md)에서 게재 실패에 대해 자세히 알아보세요.


### 특정 MX 규칙

MX 규칙(Mail eXchanger)은 보내는 서버와 받는 서버 간의 통신을 관리하는 규칙입니다.

MTA에는 자체 MX 규칙이 있어 사용자의 과거 전자 메일 신뢰도와 전자 메일을 보내는 도메인에서 오는 실시간 피드백에 따라 도메인별로 처리량을 사용자 지정할 수 있습니다.

### DKIM 서명

Domain Keys Identified Mail(DKIM)는 위조된 발신자 주소(일반적으로 스푸핑이라고 함)를 감지하는 데 사용되는 인증 방법입니다.

Adobe Campaign에서 DKIM 이메일 인증 서명은 MTA에 의해 수행됩니다.

DKIM에 대한 자세한 내용은 [Adobe 게재 모범 사례 안내서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target="_blank"}를 참조하세요.

## 이메일 피드백 서비스 {#email-feedback-service}

EFS(Campaign Email Feedback Service)는 Adobe Campaign을 통해 전송되는 각 이메일 게재의 상태를 보고합니다.

게재가 시작되면 메시지가 Campaign에서 MTA로 성공적으로 릴레이될 때 **[!UICONTROL Success]** 백분율에 변화가 없습니다. 게재 로그에 각 대상 주소의 **[!UICONTROL Taken into account by the service provider]** 상태가 표시됩니다.

메시지가 타겟팅된 프로필에 실제로 전달되고 MTA에서 이 정보가 실시간으로 보고되면 게재 로그에 메시지를 성공적으로 받은 각 주소의 **[!UICONTROL Sent]** 상태가 표시됩니다. **[!UICONTROL Success]** 비율은 각각의 성공적인 게재에 따라 증가합니다.

하드 바운스 메시지가 MTA에서 다시 보고되면 로그 상태가 **[!UICONTROL Taken into account by the service provider]**&#x200B;에서 **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->(으)로 변경됩니다.

소프트 바운싱 메시지가 MTA에서 다시 보고되면 로그 상태가 변경되지 않은 상태로 유지됩니다(**[!UICONTROL Taken into account by the service provider]**). [오류 이유](delivery-failures.md#delivery-failure-reasons)만 업데이트됩니다<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. **[!UICONTROL Success]** 비율은 변경되지 않습니다. 그런 다음 소프트 바운싱 메시지가 게재 [유효 기간](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"} 동안 다시 시도됩니다.

* 유효 기간이 끝나기 전에 다시 시도하면 메시지 상태가 **[!UICONTROL Sent]**(으)로 변경되고 **[!UICONTROL Success]** 비율이 적절하게 증가합니다.

* 그렇지 않으면 상태가 **[!UICONTROL Failed]**(으)로 변경됩니다. **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** --> 비율은 변경되지 않습니다.

>[!NOTE]
>
>하드 및 소프트 바운스에 대한 자세한 내용은 [이 섹션](delivery-failures.md#delivery-failure-reasons)을 참조하세요.
>
>일시적 게재 실패 후 다시 시도에 대한 자세한 내용은 [이 섹션](delivery-failures.md#retries)을 참조하세요.

아래 표는 전송 프로세스의 각 단계에서 KPI 및 전송 로그 상태를 업데이트하는 방법을 보여 줍니다.

| 전송 프로세스의 단계 | KPI 요약 | 전송 로그 상태 |
|--- |--- |--- |
| 메시지가 Campaign에서 MTA로 정상적으로 중계됨 | **[!UICONTROL Success]** 백분율이 표시되지 않습니다(0%에서 시작). | 서비스 제공자의 고려 |
| 하드 바운스 메시지가 MTA에서 다시 보고됨 | **[!UICONTROL Success]** 백분율 변경 없음 | 실패 |
| 소프트 바운싱 메시지는 MTA에서 다시 보고됨 | **[!UICONTROL Success]** 백분율 변경 없음 | 서비스 제공자의 고려 |
| 소프트 바운싱 메시지 다시 시도 성공 | **[!UICONTROL Success]** 비율이 이에 따라 증가함 | 전송됨 |
| 소프트 바운싱 메시지 다시 시도 실패 | **[!UICONTROL Success]** 백분율 변경 없음 | 실패 |
