---
title: 트랜잭션 메시지 보내기 및 모니터링
description: 트랜잭션 메시지 보내기 및 모니터링 방법 알아보기
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 084607f6-47d8-40c0-89ba-bfbb88fc2e53
source-git-commit: c044b391c900e8ff82147f2682e2e4f91845780c
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 2%

---

# 트랜잭션 메시지 보내기 및 모니터링 {#delivery-execution}

## 메시지 보내기{#send-transactional-msg}

데이터 보강이 완료되고 게재 템플릿이 이벤트에 연결되면 게재가 실행 인스턴스에서 전송됩니다.

>[!NOTE]
>
>트랜잭션 메시지는 다른 게재보다 우선 순위가 지정됩니다.

모든 게재는 **[!UICONTROL Administration > Production > Message Center > Default > Deliveries]** 폴더를 입력합니다.

기본적으로 배달 월별로 하위 폴더로 정렬됩니다. 메시지 템플릿 속성에서 변경할 수 있습니다.

## 메시지 모니터링 {#monitor-transactional-msg}

트랜잭션 메시지를 모니터링하려면 [게재 로그](send.md).

실행 인스턴스에서 전송된 트랜잭션 게재는 기술 워크플로우( )를 통해 제어 인스턴스로 다시 동기화됩니다.**[!UICONTROL Message Center execution instance]**)을 클릭하여 제품에서 사용할 수 있습니다.

>[!NOTE]
>
>게재 주마다 이벤트 생성 날짜가 아니라 최신 이벤트 업데이트를 기반으로 이벤트를 누적합니다. 따라서 제어 인스턴스에서 트랜잭션 메시지 게재 로그를 추출할 때 로그가 업데이트되면(예를 들어, 이벤트에 대해 인바운드 바운스가 수신될 때) 각 게재 로그 ID와 연관된 게재 ID가 시간에 따라 변경될 수 있습니다.

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->

## 보고{#reporting-transactional-msg}

Adobe Campaign에서는 활동을 제어하고 실행 인스턴스의 원활한 실행을 제어할 수 있는 몇 가지 보고서를 제공합니다.

이러한 메시지 센터 보고서는 **[!UICONTROL Reports]** 의 탭 **제어 인스턴스**.

![](assets/mc-reports.png)

### 메시지 센터 이벤트 내역 {#history-events}

다음 **[!UICONTROL Message Center event history]** 보고서는 메시지 센터 모듈 활동에 대한 개요(예: 트랜잭션 메시지로 처리 및 전달된 이벤트 수)를 표시합니다.

보고서를 열면 기본적으로 표시되는 정보가 성공적으로 전송된 트랜잭션 메시지의 비율과 일치합니다. 더 많은 수준을 보려면 다양한 노드를 열고 커서를 적절한 수준에 놓아 선택할 수 있습니다.

기간별 각 이벤트 유형에 대한 데이터를 볼 수 있습니다. 다음 **[!UICONTROL Events]** 열은 컨트롤 인스턴스당 받은 이벤트 수에 해당합니다. 개인화된 트랜잭션 메시지로 변형되는 이벤트 수는 **[!UICONTROL Sent]** 열.


### 메시지 센터 처리 시간 {#processing-time}

다음 **[!UICONTROL Message Center processing time]** 보고서는 실시간 큐와 관련된 기본 표시기를 표시합니다. 이 보고서는 **[!UICONTROL Monitoring]** 탭에서 사용할 수 있습니다.

![](assets/mc-processing-time-report.png)

글로벌 통계 또는 특정 실행 인스턴스에 대한 상대적 통계를 표시하도록 선택할 수 있습니다. 채널별로 및 특정 기간 동안 데이터를 필터링할 수도 있습니다.

에 표시되는 표시기 **[!UICONTROL Indicators over the period]** 섹션은 선택한 기간 동안 계산됩니다.

* **[!UICONTROL Average queuing time]**: 메시지 센터에서 이벤트를 성공적으로 처리한 평균 시간입니다. 처리 시간만 고려합니다.
* **[!UICONTROL Average message sending time (s)]**: 메시지 센터에서 이벤트를 성공적으로 처리한 평균 시간입니다. mta 배달 시간만 고려합니다.
* **[!UICONTROL Average processing time (s)]**: 메시지 센터에서 이벤트를 성공적으로 처리한 평균 시간입니다. 계산에는 처리 시간 및 데이터 전송 시간이 고려됩니다.
* **[!UICONTROL Maximum number of queued events]**: 지정된 시간에 메시지 센터 큐에 있는 최대 이벤트 수입니다.
* **[!UICONTROL Minimum number of queued events]**: 지정된 시간에 메시지 센터 큐에 있는 최소 이벤트 수입니다.
* **[!UICONTROL Average number of queued events]**: 지정된 시간에 메시지 센터 큐에 있는 평균 이벤트 수입니다.

>[!NOTE]
>
>Adobe Campaign 배포 마법사에서 경고(주황색) 및 경고(빨간색) 표시기 임계값을 구성할 수 있습니다. 을(를) 참조하십시오. [임계값 모니터링](#thresholds).



### 메시지 센터 서비스 수준 {#service-level}

다음 **[!UICONTROL Message Center service level]** 보고서에는 오류 분류뿐만 아니라 트랜잭션 메시지와 관련된 게재 통계가 표시됩니다. 오류 유형을 클릭하여 세부 정보를 표시할 수 있습니다.

이 보고서는 **[!UICONTROL Monitoring]** 탭에서 사용할 수 있습니다.

글로벌 통계 또는 특정 실행 인스턴스에 대한 상대적 통계를 표시하도록 선택할 수 있습니다. 채널별로 및 특정 기간 동안 데이터를 필터링할 수도 있습니다.

에 표시되는 표시기 **[!UICONTROL Indicators over the period]** 섹션은 선택한 기간 동안 계산됩니다.

* **[!UICONTROL Incoming (throughput event/h)]**: 메시지 센터 큐에 입력된 평균 시간별 이벤트 수
* **[!UICONTROL Incoming (event vol)]**: 메시지 센터 큐에 입력한 이벤트 수입니다.
* **[!UICONTROL Outgoing (throughput msg/h)]**: 성공적으로 보내는 메시지 센터 이벤트(게재에서 보낸)의 평균 시간별 수입니다.
* **[!UICONTROL Outgoing (msg vol)]**: 발신 성공 메시지 센터 이벤트 수(게재에서 전송됨).
* **[!UICONTROL Average sending time (seconds)]**: 성공적으로 처리된 이벤트에 대한 메시지 센터에서 보낸 평균 시간입니다. 계산에는 처리 시간 및 데이터 전송 시간이 고려됩니다.
* **[!UICONTROL Error rate]**: 오류가 있는 이벤트 수를 메시지 센터 큐에 입력한 이벤트 수와 비교한 것입니다. 다음 오류가 고려됩니다. 라우팅 오류, 만료된 이벤트(큐에 너무 오래 있는 이벤트), 게재 오류, 게재에 의해 무시된 배달(격리 등)

>[!NOTE]
>
>Adobe Campaign 배포 마법사에서 경고(주황색) 및 경고(빨간색) 표시기 임계값을 구성할 수 있습니다. 을(를) 참조하십시오. [임계값 모니터링](#thresholds).

### 임계값 모니터링 {#thresholds}

표시기에 나타나는 경고(주황색) 및 경고(빨간색) 임계값을 구성할 수 있습니다 **메시지 센터 서비스 수준** 및 **메시지 센터 처리 시간** 보고서.

이렇게 하려면 아래 단계를 수행합니다:

1. 에서 배포 마법사를 엽니다. **실행 인스턴스**&#x200B;로 이동하여 **[!UICONTROL Message Center]** 페이지.
1. 임계값을 변경하려면 화살표를 사용합니다.

   ![](assets/mc-thresholds.png)
