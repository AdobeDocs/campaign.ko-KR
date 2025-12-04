---
title: 캠페인 모니터링 개요
description: 게재, 워크플로우 및 Campaign 인스턴스를 모니터링하는 방법 알아보기
feature: Monitoring
role: User
level: Beginner
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 2%

---

# 캠페인 모니터링 개요 {#monitor-campaign}

Adobe Campaign은 프로세스, 게재 및 환경을 모니터링하여 최적의 성능을 보장하고 문제를 사전에 해결할 수 있는 포괄적인 기능 세트를 제공합니다.

>[!NOTE]
>
>Campaign 관리자는 [Campaign Campaign 컨트롤 패널](#control-panel)을(를) 사용하여 인스턴스를 모니터링하고, 성능을 관리하고, 셀프서비스 기능으로 설정을 구성할 수도 있습니다.

## 게재 모니터링 {#monitor-deliveries}

게재가 전송된 후 게재를 모니터링하는 것은 마케팅 캠페인이 효율적이고 고객에게 도달하는지 확인하는 중요한 단계입니다. 게재를 보낸 후 게재 상태를 모니터링하고 게재 대시보드에서 주요 지표를 추적할 수 있습니다. 대시보드는 게재 로그, 제외 로그, 추적 로그 및 기타 모니터링 기능에 대한 액세스를 제공하여 모든 채널에서 게재 성능을 분석하는 데 도움이 됩니다.

**전자 메일 게재** - 전자 메일 게재 상태를 모니터링하고, 주요 지표를 추적하고, 자세한 로그에 액세스합니다. [Campaign UI에서 게재 모니터링](../send/delivery-dashboard.md), [게재 상태](../send/delivery-statuses.md) 및 [이메일 게재 모니터링](../send/send.md#email-monitoring)에 대해 자세히 알아보세요.

**SMS 게재** - SMS 게재 상태를 추적하고 SMS 게재 대시보드에서 주요 지표를 모니터링합니다. [SMS 모니터링](../send/sms/sms-monitor.md)에 대해 자세히 알아보세요.

**푸시 알림** - 푸시 알림 게재를 모니터링하여 모바일 앱 사용자에게 효과적으로 전달되도록 합니다. [푸시 알림 모니터링](../send/push.md#push-test)에 대해 자세히 알아보세요.

**트랜잭션 메시지** - 이벤트에 의해 트리거된 메시지의 경우 이벤트 처리 상태, 메시지 실행 및 게재 상태를 모니터링합니다. [트랜잭션 메시지 모니터링](../send/delivery-execution.md#monitor-messages)에 대해 자세히 알아보세요.

**게재 실패** - 깨끗한 데이터베이스를 유지 관리하고 배달 가능성을 높이기 위해 게재 실패 이유를 이해하는 것이 중요합니다. 게재 실패는 하드 바운스, 소프트 바운스 및 무시된 메시지로 분류됩니다. [게재 실패 및 격리](../send/delivery-failures.md)에 대해 자세히 알아보세요.

## 게재 기능 모니터링 {#monitor-deliverability}

게재 가능성 모니터링은 메시지가 수신자의 받은 편지함에 도달하는지 확인하고 스팸 필터를 방지하는 데 도움이 됩니다. Adobe Campaign은 게재 보고서, 받은 편지함 렌더링, SpamAssassin 테스트 및 브로드캐스트 통계를 포함하여 게재 가능성을 모니터링하고 개선하는 여러 기본 제공 도구를 제공합니다. 깔끔한 이메일 목록 유지, 보낸 사람의 신뢰도 모니터링 및 전송 도메인 인증과 같은 게재 가능성 모범 사례를 따르는 것이 우수한 게재율을 유지하는 데 중요합니다.

[게재 가능성 모니터링 도구](../send/monitoring-deliverability.md) 및 [게재 가능성 모범 사례](../send/about-deliverability.md)에 대해 자세히 알아보세요.

## 워크플로 모니터링 {#monitor-workflows}

워크플로우는 마케팅 캠페인 및 데이터 처리를 자동화하는 데 필수적입니다. 워크플로우 실행 모니터링은 다음 작업에 유용합니다.

* 워크플로우가 정상적으로 완료되었는지 확인
* 오류 식별 및 해결
* 워크플로우 성능 최적화

### 워크플로우 모니터링 기능 {#workflow-monitoring}

**다음 워크플로우 요소 모니터링:**

**워크플로 실행 상태** - 워크플로가 실행 중인지, 일시 중지되었는지, 실패했는지 또는 완료되었는지 추적합니다. [워크플로우 실행에 대해 자세히 알아보기](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=ko){target="_blank"}

**활동 실행 로그** - 각 워크플로우 활동에 대한 자세한 로그에 액세스하여 문제를 해결하고 성능을 최적화합니다.

**워크플로우 Heatmap** - 워크플로우 실행 패턴을 시각화하고 병목 현상을 식별하며 동시 워크플로우를 모니터링합니다. 워크플로우 HeatMap은 Campaign 관리자가 사용할 수 있습니다. [워크플로우 Heatmap에 대해 자세히 알아보기](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/heatmap.html?lang=ko){target="_blank"}

**워크플로 기록** - 시간에 따른 모든 워크플로 실행 및 수정 사항을 추적하여 워크플로 동작 및 성능을 파악합니다.

## 인스턴스 모니터링 {#monitor-instance}

인스턴스 모니터링은 Adobe Campaign 환경의 상태와 성능을 확인하는 데 도움이 됩니다.

### 감사 추적 {#audit-trail}

감사 추적 셀프서비스 인터페이스를 사용하면 Adobe Campaign 인스턴스 내에서 수행된 변경 사항을 모니터링할 수 있습니다. 감사 추적은 인스턴스 내에서 발생하는 작업 및 이벤트의 포괄적인 목록을 실시간으로 캡처합니다.

**감사 추적 사용 대상:**

* **구성 요소 변경 내용 추적**: 워크플로, 스키마, 옵션 및 기타 구성 요소에 발생한 결과 모니터링
* **변경한 사람 식별**: 특정 요소를 마지막으로 업데이트한 사람과 업데이트 시기 확인
* **사용자 작업 이해**: 문제 해결 또는 감사를 위해 인스턴스에서 사용자가 수행한 작업을 검토합니다
* **준수 유지**: 준수 및 보안을 위해 모든 구성 변경 내용을 추적합니다.

감사 추적은 Campaign 클라이언트 콘솔을 통해 액세스할 수 있으며 사용자가 수행한 작업에 대한 자세한 정보를 제공합니다.

[감사 추적](../reporting/audit-trail.md)에 대해 자세히 알아보기

### 성능 모니터링 {#performance-monitoring}

Campaign v8은 인스턴스 성능을 추적하고 최적의 작업을 보장하는 몇 가지 모니터링 기능을 제공합니다.

**데이터베이스 모니터링** - Campaign 컨트롤 패널을 통해 데이터베이스 사용량 및 용량을 모니터링하여 최적의 성능과 저장소 관리를 보장합니다. [데이터베이스 모니터링에 대해 자세히 알아보기](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html?lang=ko){target="_blank"}

**활성 프로필 모니터링** - 계약 제한에 대해 활성 프로필 사용을 추적하여 규정 준수를 유지하고 리소스 할당을 최적화합니다. [활성 프로필에 대해 자세히 알아보기](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=ko){target="_blank"}

**워크플로 모니터링** - 워크플로 실행 상태를 모니터링하여 오래 실행되는 워크플로를 식별하고 모든 기술 워크플로가 올바르게 실행되는지 확인합니다. [기술 워크플로우에 대해 자세히 알아보기](#technical-workflows)

**게재 처리량 및 대기 시간** - Campaign 컨트롤 패널을 통한 트랜잭션 통신에 대한 게재 처리량(시간당 전송된 메시지) 및 대기 시간을 추적합니다. [처리량 모니터링에 대해 자세히 알아보기](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html?lang=ko){target="_blank"}

>[!NOTE]
>
>Campaign v8 관리 클라우드 서비스의 경우 서버 인프라(CPU, 메모리, 디스크)는 Adobe에서 모니터링하고 관리합니다.

### 기술 워크플로 {#technical-workflows}

기술 워크플로우는 Campaign 인스턴스를 유지 관리하기 위해 백그라운드에서 실행되는 필수 프로세스입니다.

**기술 워크플로우 모니터링:**

* 일정에 따라 실행
* 오류 없이 성공적으로 완료
* 데이터를 올바르게 처리 중

**모니터링할 주요 기술 워크플로우:**

| 워크플로 | 목적 |
|----------|---------|
| **추적** | 이메일 게재의 추적 데이터를 처리합니다. |
| **정리** | 이전 데이터 및 로그를 제거하여 데이터베이스 성능 유지 |
| **게재 기능 업데이트** | 게재 가능성 규칙 및 스팸 필터 패턴 업데이트 |
| **데이터베이스 정리** | 이전 게재 및 추적 로그 제거 |

[기술 워크플로우](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=ko){target="_blank"}에 대해 자세히 알아보기

### Campaign 컨트롤 패널 {#control-panel}

Campaign Campaign 컨트롤 패널은 관리자가 Campaign 인스턴스를 모니터링하고 관리할 수 있는 셀프서비스 기능을 제공합니다.

| 모니터링 유형 | 기능 |
|-----------------|--------------|
| **성능** | 활성 프로필 사용량 추적, 데이터베이스 사용량 및 용량 모니터링, 워크플로우 실행 상태 보기, 게재 처리량 및 지연 모니터링 |
| **인프라** | SFTP 스토리지 용량 모니터링, 하위 도메인 구성 추적, SSL 인증서 만료 모니터링, IP 허용 목록 관리 |
| **인스턴스** | 빌드 버전 및 설치된 패키지 보기, 시스템 구성 모니터링, 승인된 외부 도메인 관리 |

[Campaign 컨트롤 패널](../config/self-service.md) 및 [Campaign 컨트롤 패널 성능 모니터링](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=ko){target="_blank"}에 대해 자세히 알아보기

>[!NOTE]
>
>Campaign v8 Managed Cloud Services의 경우 Adobe은 서버 인프라, 운영 체제 및 애플리케이션 계층을 모니터링하고 관리합니다. 이 페이지 및 Campaign 컨트롤 패널에 설명된 모니터링 기능을 사용하여 인스턴스 성능, 워크플로우 및 게재를 모니터링할 수 있습니다.

## 추적 및 보고 {#tracking-reporting}

### 메시지 추적 {#message-tracking}

수신자 행동을 추적하고 캠페인의 효과를 측정합니다.

* **열기**: 받는 사람이 전자 메일을 열 때 추적
* **클릭 수**: 받는 사람이 클릭하는 링크 모니터링
* **구독 취소**: 옵트아웃 요청 추적
* **미러 페이지 보기**: 브라우저에서 메일을 보는 수신자 수 확인

[메시지 추적](../send/tracking.md)에 대해 자세히 알아보기

### 게재 보고서 {#delivery-reports}

Adobe Campaign은 게재 성과를 분석할 수 있는 포괄적인 보고서 세트를 제공합니다.

* **게재 요약**: 전송, 게재 및 실패 개요
* **추적 표시기**: 열기, 클릭 수 및 클릭스루 비율
* **URL 및 클릭 스트림**: 게재에서 가장 많이 사용되는 링크
* **핫 클릭**: 받는 사람이 전자 메일을 클릭한 위치를 시각적으로 표시합니다.

[게재 보고서](../reporting/delivery-reports.md)에 대해 자세히 알아보기

### 전반적 보고서 {#global-reports}

글로벌 보고서에 액세스하여 모든 캠페인 및 게재의 성과를 분석할 수 있습니다.

* **게재 처리량**: 시간 경과에 따라 전송된 메시지
* **게재 불가 및 바운스**: 실패한 게재 분석
* **사용자 활동**: 모든 캠페인에서 열기, 클릭, 구독 취소

[글로벌 보고서](../reporting/global-reports.md)에 대해 자세히 알아보기

## 관련 항목 {#related-topics}

* [게재 모범 사례](delivery-best-practices.md)
* [격리 관리](../send/quarantines.md)
* [게재 구성 및 보내기](../send/configure-and-send.md)
* [보고 시작](../reporting/gs-reporting.md)

