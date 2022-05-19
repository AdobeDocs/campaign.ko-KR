---
title: Adobe Campaign의 향상된 MTA 정보
description: Adobe Campaign Enhanced MTA를 사용하여 전자 메일을 보내는 범위와 특성에 대해 알아봅니다
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 0fa0db62f45097755bebcbf434614c4c835d886a
workflow-type: tm+mt
source-wordcount: '972'
ht-degree: 4%

---

# 향상된 MTA 정보 {#sending-with-enhanced-mta}

다음 **Adobe Campaign Enhanced MTA** (Mail Transfer Agent)는 최적의 게재 능력, 평판, 처리량, 보고, 반송 처리, IP 램프 업 및 연결 설정 관리를 위해 업그레이드된 전송 인프라를 제공합니다.

모든 Campaign v8 고객을 위해 구현되어 확장성과 게재 처리량을 높이고 더 많은 이메일을 더 빨리 보낼 수 있습니다. 이는 인터넷 서비스 공급자의 피드백을 기반으로 이메일 전송 설정을 실시간으로 변경하는 새로운 적응형 전달 기술을 통해 달성됩니다.

## 사용 및 이점

**Enhanced MTA란 무엇입니까?**

Adobe Campaign은 SparkPost의 상업용 이메일 MTA를 실행하는 MTA(Mail Transfer Agent)를 사용합니다 **모멘텀**.

모멘텀은 보다 스마트한 반송 처리 및 보낸 사람이 최적의 받은 편지함 배달률을 달성하고 유지하는 데 도움이 되는 자동화된 게재 기능 최적화 기능을 포함하는 혁신적이고 고성능 MTA 기술을 나타냅니다.

**어떤 이점이 있습니까?**

* Enhanced MTA를 사용하면 전체 처리량 속도가 크게 증가하고 소프트 바운스 수가 크게 줄어듭니다.
* 최신 MTA 기술을 사용하여 이메일 배달을 위한 최적의 처리량 속도를 제공합니다.
* 수신한 피드백에 즉시 자동으로 적용함으로써 실시간 게재 데이터를 통해 보다 정확하고 지능적인 이메일 전달을 보장합니다.

## 향상된 MTA 특성 {#enhanced-mta-impacts}

### 반송 자격

대상 **동기** 게재 실패 오류 메시지에서 Enhanced MTA가 바운스 유형 및 자격을 결정하고 해당 정보를 Campaign에 다시 전송합니다.

Enhanced MTA는 SMTP 바운스를 자격을 부여하고 해당 자격을 Campaign 반송 이유 및 자격에 매핑된 반송 코드 형태로 Campaign에 다시 전송합니다.

>[!NOTE]
>
>현재 **비동기** 바운스 수는 Enhanced MTA에 의해 검증되지 않지만 **[!UICONTROL Inbound email]** 규칙. 자세한 내용은 [Adobe Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}. <!--Refer to [bounce mail qualification](delivery-failures.md#bounce-mail-qualification)-->

에서 게재 실패에 대해 자세히 알아보기 [이 섹션](delivery-failures.md).

### 유효 기간

Campaign 게재의 유효 기간 설정은 **3.5일 이하**. Campaign에서 3.5일 이상의 값을 정의하면 고려되지 않습니다.

예를 들어 유효 기간이 Campaign에서 기본값 5일로 설정된 경우 소프트 바운스 메시지는 Enhanced MTA 다시 시도 큐로 전환되고 해당 메시지가 Enhanced MTA에 도달한 후 최대 3.5일 동안 다시 시도됩니다. 이 경우 Campaign에 설정된 값은 사용되지 않습니다.

메시지가 3.5일 동안 Enhanced MTA 큐에 있고 게재에 실패하면 시간이 초과되고 게재 로그에서 해당 상태가 **[!UICONTROL Sent]**&#x200B;에서 **[!UICONTROL Failed]**(으)로 업데이트됩니다.

유효 기간에 대한 자세한 내용은 [Adobe Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}.

### 다시 시도

소프트 바운스 다시 시도 및 그 사이의 시간은 메시지의 이메일 도메인에서 돌아오는 바운스 응답의 유형과 심각도를 기반으로 Enhanced MTA에 의해 결정됩니다.

>[!NOTE]
>
>게재 속성의 다시 시도 설정은 Campaign에서 사용하지 않습니다.

에서 다시 시도하는 방법에 대해 자세히 알아보기 [이 섹션](delivery-failures.md#retries).

### 특정 MX 규칙

MX 규칙(Mail eXchanger)은 전송 서버와 수신 서버 간의 통신을 관리하는 규칙입니다.

Enhanced MTA에는 자체 MX 규칙을 사용하여 사용자의 과거 전자 메일 신뢰도를 기반으로, 전자 메일을 전송하는 도메인에서 오는 실시간 피드백에 따라 도메인별로 처리량을 사용자 정의할 수 있습니다.

### DKIM 서명

Domain Keys Identified Mail(DKIM)은 위조 발신자 주소(일반적으로 스푸핑)를 감지하는 데 사용되는 인증 방법입니다.

Adobe Campaign에서 DKIM 전자 메일 인증 서명은 Enhanced MTA에 의해 수행됩니다.

에서 DKIM에 대해 자세히 알아보십시오 [Adobe 게재 가능성 모범 사례 안내서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target=&quot;_blank&quot;}.

## 이메일 피드백 서비스 {#email-feedback-service}

피드백을 Enhanced MTA(메시지 전송 에이전트)에서 직접 캡처하므로 EFS(이메일 피드백 서비스) 기능을 사용하면 각 이메일의 상태가 정확하게 보고됩니다.

게재를 시작하면 에는 변경 사항이 없습니다 **[!UICONTROL Success]** 메시지가 Campaign에서 Enhanced MTA로 성공적으로 중계되는 경우의 백분율입니다.

게재 로그에는 **[!UICONTROL Taken into account by the service provider]** 타겟팅된 각 주소의 상태입니다.

메시지가 실제로 타겟팅된 프로필에 전달되고, Enhanced MTA에서 이 정보가 실시간으로 다시 보고되면 게재 로그에는 **[!UICONTROL Sent]** 메시지를 성공적으로 받은 각 주소의 상태입니다. 다음 **[!UICONTROL Success]** 백분율이 게재의 각 성공에따라 증가합니다.

하드 바운스 메시지가 향상된 MTA에서 다시 보고되면 로그 상태가 **[!UICONTROL Taken into account by the service provider]** to **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

소프트 바운스 메시지가 Enhanced MTA에서 다시 보고되면 로그 상태가 변경되지 않은 상태로 유지됩니다(**[!UICONTROL Taken into account by the service provider]**): 유일한 [오류 원인](delivery-failures.md#delivery-failure-reasons) 업데이트됨<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. 다음 **[!UICONTROL Success]** 백분율은 변경되지 않은 상태로 유지됩니다. 그런 다음 소프트 바운스 메시지가 게재 동안 다시 시도됩니다 [유효 기간](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}:

* 유효 기간이 끝나기 전에 재시도가 성공하면 메시지 상태가 **[!UICONTROL Sent]** 그리고 **[!UICONTROL Success]** 백분율이 그에 따라 증가합니다.

* 그렇지 않으면 상태가 **[!UICONTROL Failed]**. 다음 **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->백분율은 변경되지 않은 상태로 유지됩니다.

>[!NOTE]
>
>하드 및 소프트 바운스에 대한 자세한 내용은 [이 섹션](delivery-failures.md#delivery-failure-reasons).
>
>일시적 게재 실패 후 다시 시도하는 방법에 대한 자세한 내용은 [이 섹션](delivery-failures.md#retries).

아래 표는 EFS 기능을 사용하여 전송 프로세스의 각 단계에서 KPI 및 전송 로그 상태를 업데이트하는 방법을 보여줍니다.

| 전송 프로세스의 단계 | KPI 요약 | 전송 로그 상태 |
|--- |--- |--- |
| 메시지가 Campaign에서 Enhanced MTA로 성공적으로 전달되었습니다 | **[!UICONTROL Success]** 백분율이 표시되지 않음(0%에서 시작) | 서비스 공급자가 고려함 |
| 하드 바운스 메시지가 향상된 MTA에서 다시 보고됩니다 | 에서 변경 없음 **[!UICONTROL Success]** 백분율 | 실패 |
| 소프트 바운스 메시지는 Enhanced MTA에서 다시 보고됩니다 | 에서 변경 없음 **[!UICONTROL Success]** 백분율 | 서비스 공급자가 고려함 |
| 소프트 바운스 메시지 다시 시도 성공 | **[!UICONTROL Success]** 백분율이 그에 따라 증가함 | 전송됨 |
| 소프트 바운스 메시지 다시 시도 실패 | 에서 변경 없음 **[!UICONTROL Success]** 백분율 | 실패 |
