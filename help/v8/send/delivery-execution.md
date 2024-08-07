---
title: 트랜잭션 메시지 보내기 및 모니터링
description: 트랜잭션 메시지를 보내고 모니터링하는 방법 알아보기
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 084607f6-47d8-40c0-89ba-bfbb88fc2e53
source-git-commit: c044b391c900e8ff82147f2682e2e4f91845780c
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 1%

---

# 트랜잭션 메시지 보내기 및 모니터링 {#delivery-execution}

## 메시지 보내기{#send-transactional-msg}

데이터 보강이 완료되고 게재 템플릿이 이벤트에 연결되면 게재가 실행 인스턴스에서 전송됩니다.

>[!NOTE]
>
>트랜잭션 메시지는 다른 게재보다 우선 순위가 높습니다.

모든 게재는 **[!UICONTROL Administration > Production > Message Center > Default > Deliveries]** 폴더에 그룹화됩니다.

기본적으로 게재 월별로 하위 폴더로 정렬됩니다. 메시지 템플릿 속성에서 변경할 수 있습니다.

## 메시지 모니터링 {#monitor-transactional-msg}

트랜잭션 메시지를 모니터링하려면 [게재 로그](send.md)를 확인하세요.

실행 인스턴스에서 보낸 트랜잭션 게재는 매시간 실행되는 기술 워크플로우(**[!UICONTROL Message Center execution instance]**)를 통해 컨트롤 인스턴스로 다시 동기화됩니다.

>[!NOTE]
>
>매주 게재는 이벤트 생성 날짜가 아닌 최신 이벤트 업데이트를 기준으로 이벤트를 누적합니다. 따라서 제어 인스턴스에서 트랜잭션 메시지 게재 로그를 추출할 때 로그가 업데이트되면 각 게재 로그 ID와 연관된 게재 ID가 시간에 따라 변경될 수 있습니다(예: 이벤트에 대한 인바운드 바운스가 수신되면).

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->

## 보고{#reporting-transactional-msg}

Adobe Campaign에서는 실행 인스턴스의 활동 및 원활한 실행을 제어할 수 있는 몇 가지 보고서를 제공합니다.

이러한 메시지 센터 보고서는 **제어 인스턴스**&#x200B;의 **[!UICONTROL Reports]** 탭에서 액세스할 수 있습니다.

![](assets/mc-reports.png)

### 메시지 센터 이벤트 내역 {#history-events}

**[!UICONTROL Message Center event history]** 보고서에는 트랜잭션 메시지로 처리 및 전달된 이벤트 수와 같은 메시지 센터 모듈 작업의 개요가 표시됩니다.

보고서가 열릴 때 기본적으로 표시되는 정보는 성공적으로 전송된 트랜잭션 메시지의 비율과 일치합니다. 더 많은 레벨을 보려면 다양한 노드를 열고 커서를 해당 레벨에 놓아 선택할 수 있습니다.

기간별로 각 이벤트 유형과 관련된 데이터를 볼 수 있습니다. **[!UICONTROL Events]** 열은 컨트롤 인스턴스당 받은 이벤트 수에 해당합니다. 개인화된 트랜잭션 메시지로 변환된 이벤트 수는 **[!UICONTROL Sent]** 열에 자세히 설명되어 있습니다.


### 메시지 센터 처리 시간 {#processing-time}

**[!UICONTROL Message Center processing time]** 보고서에는 실시간 큐와 관련된 기본 지표가 표시됩니다. 이 보고서는 컨트롤 인스턴스의 **[!UICONTROL Monitoring]** 탭을 통해서도 액세스할 수 있습니다.

![](assets/mc-processing-time-report.png)

전역 통계를 표시하거나 특정 실행 인스턴스와 관련된 통계를 표시하도록 선택할 수 있습니다. 또한 특정 기간 동안 채널 및 을 기준으로 데이터를 필터링할 수도 있습니다.

**[!UICONTROL Indicators over the period]** 섹션에 표시된 지표는 선택한 기간 동안 계산됩니다.

* **[!UICONTROL Average queuing time]**: 메시지 센터에서 보낸 이벤트를 성공적으로 처리한 평균 시간입니다. 처리 시간만 고려됩니다.
* **[!UICONTROL Average message sending time (s)]**: 메시지 센터에서 보낸 이벤트를 성공적으로 처리한 평균 시간입니다. mta 게재 시간만 고려합니다.
* **[!UICONTROL Average processing time (s)]**: 메시지 센터에서 보낸 이벤트를 성공적으로 처리한 평균 시간입니다. 계산에는 처리 시간과 mta 전송 시간이 고려됩니다.
* **[!UICONTROL Maximum number of queued events]**: 지정된 시점에 메시지 센터 큐에 있는 최대 이벤트 수입니다.
* **[!UICONTROL Minimum number of queued events]**: 지정된 시점에 메시지 센터 큐에 있는 최소 이벤트 수입니다.
* **[!UICONTROL Average number of queued events]**: 특정 시점에 메시지 센터 큐에 있는 평균 이벤트 수입니다.

>[!NOTE]
>
>경고(주황색) 및 경고(빨간색) 표시기 임계값은 Adobe Campaign 배포 마법사에서 구성할 수 있습니다. [임계값 모니터링](#thresholds)을 참조하세요.



### 메시지 센터 서비스 수준 {#service-level}

**[!UICONTROL Message Center service level]** 보고서에는 트랜잭션 메시지와 관련된 게재 통계와 오류 분류가 표시됩니다. 오류 유형을 클릭하여 세부 정보를 표시할 수 있습니다.

이 보고서는 컨트롤 인스턴스의 **[!UICONTROL Monitoring]** 탭을 통해서도 액세스할 수 있습니다.

전역 통계를 표시하거나 특정 실행 인스턴스와 관련된 통계를 표시하도록 선택할 수 있습니다. 또한 특정 기간 동안 채널 및 을 기준으로 데이터를 필터링할 수도 있습니다.

**[!UICONTROL Indicators over the period]** 섹션에 표시된 지표는 선택한 기간 동안 계산됩니다.

* **[!UICONTROL Incoming (throughput event/h)]**: 메시지 센터 대기열에 입력한 평균 시간당 이벤트 수입니다.
* **[!UICONTROL Incoming (event vol)]**: 메시지 센터 큐에 입력한 이벤트 수입니다.
* **[!UICONTROL Outgoing (throughput msg/h)]**: 성공한 송신 메시지 센터 이벤트의 평균 시간당 수입니다(게재에서 전송됨).
* **[!UICONTROL Outgoing (msg vol)]**: 성공한 송신 메시지 센터 이벤트 수(게재에서 전송함).
* **[!UICONTROL Average sending time (seconds)]**: 메시지 센터에서 성공적으로 처리된 이벤트에 걸린 평균 시간입니다. 계산에는 처리 시간과 mta 전송 시간이 고려됩니다.
* **[!UICONTROL Error rate]**: 오류가 있는 이벤트 수와 메시지 센터 대기열에 입력한 이벤트 수가 비교됩니다. 라우팅 오류, 만료된 이벤트(큐에 너무 오래 있는 이벤트), 게재 오류, 게재에서 무시된 오류(격리 등) 등이 고려됩니다.

>[!NOTE]
>
>경고(주황색) 및 경고(빨간색) 표시기 임계값은 Adobe Campaign 배포 마법사에서 구성할 수 있습니다. [임계값 모니터링](#thresholds)을 참조하세요.

### 임계값 모니터링 {#thresholds}

**메시지 센터 서비스 수준** 및 **메시지 센터 처리 시간** 보고서에 표시되는 표시기의 경고(주황색) 및 경고(빨간색) 임계값을 구성할 수 있습니다.

이렇게 하려면 아래 단계를 수행합니다.

1. **실행 인스턴스**&#x200B;에서 배포 마법사를 열고 **[!UICONTROL Message Center]** 페이지로 이동합니다.
1. 화살표를 사용하여 임계값을 변경합니다.

   ![](assets/mc-thresholds.png)
