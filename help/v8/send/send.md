---
title: 이메일 보내기 및 모니터링
description: Adobe Campaign을 사용하여 전자 메일을 보내는 범위와 특성에 대해 알아봅니다
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 9fa6666532a6943c438268d7ea832f0908588208
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 3%

---


# 이메일 보내기 및 모니터링

게재를 구성하고 전송할 준비가 되면 게재 분석을 실행했는지 확인하십시오.

![](../assets/do-not-localize/book.png) [자세한 내용은 Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#confirming-delivery)를 참조하십시오{target=&quot;_blank&quot;}

완료되면 게재를 확인하여 메시지 게재를 시작합니다.

다음을 수행할 수도 있습니다.

* 을 사용하여 나중으로 게재를 예약합니다. [배달 옵션을 연기합니다.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#scheduling-the-delivery-sending){target=&quot;_blank&quot;},
* 을 사용하여 여러 배치로 보내기 [다중 전파](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#sending-using-multiple-waves){target=&quot;_blank&quot;}.

에서 게재 실행을 추적합니다 **배달** 탭으로서, 이 게재의 세부 사항 또는 게재 목록을 통해 액세스할 수 있습니다.

## 이메일 모니터링

전송되면 게재 대시보드에서 게재 상태를 확인하고 게재 로그 및 보고서에 액세스하여 메시지가 올바르게 전송되었는지 확인합니다.

![](../assets/do-not-localize/book.png) [자세한 내용은 Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html)를 참조하십시오{target=&quot;_blank&quot;}


## Campaign MTA {#mta}

Campaign v8 MTA(Mail Transfer Agent)는 최적의 게재 기능, 평판, 처리량, 보고, 반송 처리, IP 램프 업 및 연결 설정 관리를 위한 동급 최강의 전송 인프라를 제공합니다.

모든 Campaign v8 고객이 이용할 수 있으므로 확장성, 높은 게재 처리량 및 더 많은 이메일을 더 빨리 보낼 수 있습니다. 이는 인터넷 서비스 공급자의 피드백을 기반으로 이메일 전송 설정을 실시간으로 변경하는 새로운 적응형 전달 기술을 통해 달성됩니다.

### 이점

Adobe Campaign은 SparkPost의 상업용 이메일 MTA를 실행하는 MTA(Mail Transfer Agent)를 사용합니다 **모멘텀**.

모멘텀은 보다 스마트한 반송 처리 및 보낸 사람이 최적의 받은 편지함 배달률을 달성하고 유지하는 데 도움이 되는 자동화된 게재 기능 최적화 기능을 포함하는 혁신적이고 고성능 MTA 기술을 나타냅니다.

* MTA를 사용하면 전체 처리량 속도를 크게 높이고 소프트 바운스 수를 크게 줄일 수 있습니다.
* 최신 MTA 기술을 사용하여 이메일 배달을 위한 최적의 처리량 속도를 제공합니다.
* 수신한 피드백에 즉시 자동으로 적용함으로써 실시간 게재 데이터를 통해 보다 정확하고 지능적인 이메일 전달을 보장합니다.

### 반송 자격

대상 **동기** 게재 실패 오류 메시지에서 MTA는 바운스 유형 및 자격을 결정하고 해당 정보를 Campaign으로 다시 전송합니다.

MTA는 SMTP 바운스를 자격을 부여하고 해당 자격을 Campaign 바운스 이유 및 자격에 매핑된 바운스 코드 형태로 Campaign에 다시 전송합니다.

>[!NOTE]
>
>현재 **비동기** 바운스는 를 통해 inMail 프로세스에 의해 검증됩니다. **[!UICONTROL Inbound email]** 규칙. 자세한 내용은 [Adobe Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}. <!--Refer to [bounce mail qualification](delivery-failures.md#bounce-mail-qualification)-->

에서 게재 실패에 대해 자세히 알아보기 [이 섹션](delivery-failures.md).


### 특정 MX 규칙

MX 규칙(Mail eXchanger)은 전송 서버와 수신 서버 간의 통신을 관리하는 규칙입니다.

MTA에는 자체 MX 규칙을 사용하여 사용자의 과거 전자 메일 신뢰도를 기반으로, 전자 메일을 전송하는 도메인에서 오는 실시간 피드백에 따라 도메인별로 처리량을 사용자 정의할 수 있습니다.

### DKIM 서명

Domain Keys Identified Mail(DKIM)은 위조 발신자 주소(일반적으로 스푸핑)를 감지하는 데 사용되는 인증 방법입니다.

Adobe Campaign에서 DKIM 이메일 인증 서명은 MTA에 의해 수행됩니다.

에서 DKIM에 대해 자세히 알아보십시오 [Adobe 게재 가능성 모범 사례 안내서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target=&quot;_blank&quot;}.

## 이메일 피드백 서비스 {#email-feedback-service}

EFS(이메일 피드백 서비스) 기능을 사용하면 피드백이 MTA에서 직접 캡처되므로 각 이메일의 상태가 정확하게 보고됩니다.

게재를 시작하면 에는 변경 사항이 없습니다 **[!UICONTROL Success]** 메시지가 Campaign에서 MTA로 성공적으로 전달될 때의 백분율입니다.

게재 로그에는 **[!UICONTROL Taken into account by the service provider]** 타겟팅된 각 주소의 상태입니다.

메시지가 실제로 타겟팅된 프로필에 전달되고, MTA에서 이 정보가 실시간으로 다시 보고되면 게재 로그에 **[!UICONTROL Sent]** 메시지를 성공적으로 받은 각 주소의 상태입니다. 다음 **[!UICONTROL Success]** 백분율이 게재의 각 성공에따라 증가합니다.

하드 바운스 메시지가 MTA에서 다시 보고되면 로그 상태는 **[!UICONTROL Taken into account by the service provider]** to **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

소프트 바운스 메시지가 MTA에서 다시 보고되면 로그 상태가 변경되지 않고 유지됩니다(**[!UICONTROL Taken into account by the service provider]**): 유일한 [오류 원인](delivery-failures.md#delivery-failure-reasons) 업데이트됨<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. 다음 **[!UICONTROL Success]** 백분율은 변경되지 않은 상태로 유지됩니다. 그런 다음 소프트 바운스 메시지가 게재 동안 다시 시도됩니다 [유효 기간](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}:

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
| 메시지가 Campaign에서 MTA로 성공적으로 전달되었습니다 | **[!UICONTROL Success]** 백분율이 표시되지 않음(0%에서 시작) | 서비스 공급자가 고려함 |
| MTA에서 하드 바운스 메시지가 다시 보고됩니다 | 에서 변경 없음 **[!UICONTROL Success]** 백분율 | 실패 |
| 소프트 바운스 메시지는 MTA에서 다시 보고됩니다 | 에서 변경 없음 **[!UICONTROL Success]** 백분율 | 서비스 공급자가 고려함 |
| 소프트 바운스 메시지 다시 시도 성공 | **[!UICONTROL Success]** 백분율이 그에 따라 증가함 | 전송됨 |
| 소프트 바운스 메시지 다시 시도 실패 | 에서 변경 없음 **[!UICONTROL Success]** 백분율 | 실패 |
