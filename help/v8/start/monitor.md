---
title: 캠페인 모니터링 개요
description: 게재, 워크플로우 및 Campaign 인스턴스를 모니터링하는 방법 알아보기
feature: Monitoring
role: User
level: Beginner
exl-id: 2ad585f2-19bc-4391-8a19-9e892dbe01a3
TQID: https://experienceleague.adobe.com/PjU1EFX5x4iB3yRsShGBWoR0k1D2-EI90-ss0FTcexE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 6cf587ecc9cc1e4cf9b3de0d2067e0c4562afe01
workflow-type: tm+mt
source-wordcount: 2206
ht-degree: 1%

---

# 캠페인 모니터링 개요 {#monitor-campaign}

Adobe Campaign은 개별 메시지가 전달되었는지 여부부터 워크플로우가 실패한 이유, 인스턴스가 남겨 둔 데이터베이스 용량까지 모든 수준에서 가시성을 제공합니다. 이 페이지는 모든 모니터링 기능을 매핑하므로 주의가 필요한 경우 살펴볼 위치를 알 수 있습니다.

>[!NOTE]
>
>Campaign 관리자는 [Campaign Campaign 컨트롤 패널](#control-panel)을(를) 사용하여 인스턴스를 모니터링하고, 성능을 관리하고, 셀프서비스 기능으로 설정을 구성할 수도 있습니다.

>[!TIP]
>
>**어디서부터 시작할지 알 수 없습니까?**
>
>- 마케터가 캠페인 → [게재 모니터링](#monitor-deliveries)을 확인합니다.
>- 워크플로우 문제 해결 →[워크플로우 모니터링](#monitor-workflows)
>- 관리자가 인스턴스 상태를 확인하고 →0&rbrace;인스턴스 모니터링[&#128279;](#monitor-instance)

## 게재 모니터링 {#monitor-deliveries}

게재가 전송된 후 게재를 모니터링하는 것은 마케팅 캠페인이 효율적이고 고객에게 도달하는지 확인하는 중요한 단계입니다. 게재를 보낸 후 게재 상태를 모니터링하고 게재 대시보드에서 주요 지표를 추적할 수 있습니다. 대시보드는 게재 로그, 제외 로그, 추적 로그 및 기타 모니터링 기능에 대한 액세스를 제공하여 모든 채널에서 게재 성능을 분석하는 데 도움이 됩니다.

>[!NOTE]
>
>Campaign을 처음 사용하십니까?**&#x200B;**&#x200B;게재 대시보드는 일상적인 화면입니다. 보낸 게재를 열고 **로그** 탭을 클릭하면 메시지를 받은 수신자, 제외된 이유, 클릭하거나 연 사람을 확인할 수 있습니다.

**전자 메일 게재** - 전자 메일 게재 상태를 모니터링하고, 주요 지표를 추적하고, 자세한 로그에 액세스합니다. [Campaign UI에서 게재 모니터링](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/send/monitor/delivery-dashboard), [게재 상태](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/send/monitor/delivery-statuses) 및 [이메일 게재 모니터링](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/send/emails/send#email-monitoring)에 대해 자세히 알아보세요.

**SMS 게재** - SMS 게재 상태를 추적하고 SMS 게재 대시보드에서 주요 지표를 모니터링합니다. [SMS 모니터링](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/send/sms/sms-monitor)에 대해 자세히 알아보세요.

**푸시 알림** - 푸시 알림 게재를 모니터링하여 모바일 앱 사용자에게 효과적으로 전달되도록 합니다. [푸시 알림 모니터링](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/send/push/push#push-test)에 대해 자세히 알아보세요.

**트랜잭션 메시지** - 이벤트에 의해 트리거된 메시지의 경우 이벤트 처리 상태, 메시지 실행 및 게재 상태를 모니터링합니다. [트랜잭션 메시지 모니터링](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/send/real-time/event/delivery-execution#monitor-messages)에 대해 자세히 알아보세요.

**게재 실패** - 깨끗한 데이터베이스를 유지 관리하고 배달 가능성을 높이기 위해 게재 실패 이유를 이해하는 것이 중요합니다. 게재 실패는 세 가지 유형으로 분류됩니다. 차이를 이해하면 수행할 작업을 결정하는 데 도움이 됩니다.

| 실패 유형 | 의미 | Campaign 기능 |
| --- | --- | --- |
| **하드 바운스** | 주소가 영구적으로 유효하지 않습니다(존재하지 않음, 도메인 알 수 없음). | 연락처는 자동으로 격리됩니다. 이후 게재에서 타겟팅되지 않습니다. |
| **소프트 바운스** | 일시적인 문제(전체 사서함, 서버를 일시적으로 사용할 수 없음) | 구성된 기간 동안 Campaign에서 자동으로 다시 시도 |
| **무시됨** | 보내기 전에 주소가 이미 격리되었거나 차단 목록에 추가하다에 격리되었습니다. | 시도가 없습니다. 바운스와 별도로 계산됩니다. |

[게재 실패 및 격리](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/send/monitor/delivery-failures)에 대해 자세히 알아보세요.

## 게재 기능 모니터링 {#monitor-deliverability}

>[!NOTE]
>
>&quot;게재됨&quot;으로 카운트된 메시지는 수신 서버에서 수락되었음을 의미합니다. 받은 편지함 배치는 보장하지 않습니다. 게재 가능성 모니터링은 전송 도메인 인증, IP 신뢰도 및 이메일 콘텐츠가 받은 편지함 공급자 표준을 충족하는지 여부를 알려줍니다.

게재 가능성 모니터링은 메시지가 수신자의 받은 편지함에 도달하는지 확인하고 스팸 필터를 방지하는 데 도움이 됩니다. Adobe Campaign은 게재 보고서, 받은 편지함 렌더링, SpamAssassin 테스트 및 브로드캐스트 통계를 포함하여 게재 가능성을 모니터링하고 개선하는 여러 기본 제공 도구를 제공합니다. 깔끔한 이메일 목록 유지, 보낸 사람의 신뢰도 모니터링 및 전송 도메인 인증과 같은 게재 가능성 모범 사례를 따르는 것이 우수한 게재율을 유지하는 데 중요합니다.

[게재 가능성 모니터링 도구](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/send/deliverability-management/monitoring-deliverability) 및 [게재 가능성 모범 사례](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/send/deliverability-management/about-deliverability)에 대해 자세히 알아보세요.

## 워크플로 모니터링 {#monitor-workflows}

워크플로우는 마케팅 캠페인 및 데이터 처리를 자동화하는 데 필수적입니다. 워크플로우 실행 모니터링은 다음 작업에 유용합니다.

- 워크플로우가 정상적으로 완료되었는지 확인
- 오류 식별 및 해결
- 워크플로우 성능 최적화

>[!TIP]
>
>워크플로우에 **실패** 상태가 표시되면 워크플로우를 열고 빨간색 활동을 마우스 오른쪽 단추로 클릭한 다음 **로그 표시**&#x200B;를 선택하십시오. 오류 메시지는 무엇이 잘못되었고 어떤 레코드가 잘못되었는지 정확하게 식별합니다.

### 워크플로우 모니터링 기능 {#workflow-monitoring}

**다음 워크플로우 요소 모니터링:**

**워크플로 실행 상태** - 워크플로가 실행 중인지, 일시 중지되었는지, 실패했는지 또는 완료되었는지 추적합니다. [워크플로우 실행에 대해 자세히 알아보기](https://experienceleague.adobe.com/ko/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#_blank)

**활동 실행 로그** - 각 워크플로우 활동에 대한 자세한 로그에 액세스하여 문제를 해결하고 성능을 최적화합니다.

**워크플로우 HeatMap** - 인스턴스에서 동시에 실행되는 모든 워크플로우에 대한 시각적 개요입니다. 이를 사용하여 최대 로드 기간을 식별하고, 불균형적인 리소스를 사용하는 스팟 워크플로우를 식별하며, 실행 충돌을 방지하기 위한 일정을 계획합니다. Campaign 관리자만 사용 가능합니다. [워크플로우 Heatmap에 대해 자세히 알아보기](https://experienceleague.adobe.com/ko/docs/campaign/automation/workflows/monitoring-workflows/heatmap#_blank)

**워크플로 기록** - 시간에 따른 모든 워크플로 실행 및 수정 사항을 추적하여 워크플로 동작 및 성능을 파악합니다.

## 인스턴스 모니터링 {#monitor-instance}

인스턴스 모니터링은 Adobe Campaign 환경의 상태와 성능을 확인하는 데 도움이 됩니다. Campaign v8 관리 클라우드 서비스의 경우 Adobe이 사용자를 대신하여 인프라를 모니터링하고 관리합니다. [Adobe 관리 모니터링](#adobe-cloud-monitoring)에 대해 자세히 알아보세요.

### 감사 추적 {#audit-trail}

감사 추적 셀프서비스 인터페이스를 사용하면 Adobe Campaign 인스턴스 내에서 수행된 변경 사항을 모니터링할 수 있습니다. 감사 추적은 인스턴스 내에서 발생하는 작업 및 이벤트의 포괄적인 목록을 실시간으로 캡처합니다.

**감사 추적 사용 대상:**

- **구성 요소 변경 내용 추적**: 워크플로, 스키마, 옵션 및 기타 구성 요소에 발생한 결과 모니터링
- **변경한 사람 식별**: 특정 요소를 마지막으로 업데이트한 사람과 업데이트 시기 확인
- **사용자 작업 이해**: 문제 해결 또는 감사를 위해 인스턴스에서 사용자가 수행한 작업을 검토합니다
- **준수 유지**: 준수 및 보안을 위해 모든 구성 변경 내용을 추적합니다.

감사 추적은 Campaign 클라이언트 콘솔을 통해 액세스할 수 있으며 사용자가 수행한 작업에 대한 자세한 정보를 제공합니다.

[감사 추적](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/analytics/audit-trail)에 대해 자세히 알아보기

### 성능 모니터링 {#performance-monitoring}

Campaign v8은 인스턴스 성능을 추적하고 최적의 작업을 보장하는 몇 가지 모니터링 기능을 제공합니다.

**데이터베이스 모니터링** - Campaign 컨트롤 패널을 통해 데이터베이스 사용량 및 용량을 모니터링하여 최적의 성능과 저장소 관리를 보장합니다. [데이터베이스 모니터링에 대해 자세히 알아보기](https://experienceleague.adobe.com/ko/docs/control-panel/using/performance-monitoring/database-monitoring/database-monitoring#_blank)

**활성 프로필 모니터링** - 계약 제한에 대해 활성 프로필 사용을 추적하여 규정 준수를 유지하고 리소스 할당을 최적화합니다. [활성 프로필에 대해 자세히 알아보기](https://experienceleague.adobe.com/ko/docs/control-panel/using/performance-monitoring/active-profiles-monitoring#_blank)

**워크플로 모니터링** - 워크플로 실행 상태를 모니터링하여 오래 실행되는 워크플로를 식별하고 모든 기술 워크플로가 올바르게 실행되는지 확인합니다. [기술 워크플로우에 대해 자세히 알아보기](#technical-workflows)

**게재 처리량 및 대기 시간** - Campaign 컨트롤 패널을 통한 트랜잭션 통신에 대한 게재 처리량(시간당 전송된 메시지) 및 대기 시간을 추적합니다. [처리량 모니터링에 대해 자세히 알아보기](https://experienceleague.adobe.com/ko/docs/control-panel/using/performance-monitoring/throughputs-latencies#_blank)

>[!NOTE]
>
>Campaign v8 관리 클라우드 서비스의 경우 서버 인프라(CPU, 메모리, 디스크)는 Adobe에서 모니터링하고 관리합니다. [Adobe 관리 모니터링](#adobe-cloud-monitoring)에 대해 자세히 알아보세요.

### Adobe 관리 모니터링 {#adobe-cloud-monitoring}

Adobe Campaign 클라우드 서비스는 유연한 클라우드 인프라를 통해 까다로운 고객 경험 제공 요구 사항에 대한 미션 크리티컬 지원을 제공합니다. 이를 통해 조직은 Campaign 인프라 자체를 관리하거나 운영할 필요 없이 고객 경험을 시작, 모니터링 및 최적화할 수 있습니다.

Adobe은 Campaign Cloud Services 환경을 모니터링하여 기술 문제를 감지하고 성능 및 진행 중인 프로젝트에 대한 지속적인 피드백을 제공하여 다양한 문제를 관리하고 중단을 최소화하는 데 도움이 됩니다.

**Adobe의 응답 방식**

Adobe은 24/7 Campaign 네트워크의 모든 중요 네트워크 장비를 모니터링하고 수정 사항이나 에스컬레이션이 필요한 경우 모니터링 시스템으로부터 알림을 받습니다. 문제를 발견하면 시스템은 자동 재시작 및 자동 실행 메커니즘을 사용하여 수정을 시도합니다. 시스템이 자가 복구 기능을 제공하지 않으면 Adobe On-Call 엔지니어링이 개입하여 사전 정의된 경고 실행 정보를 기반으로 문제 해결을 수행합니다.

>[!NOTE]
>
>Adobe에서 수행한 일부 모니터링 작업이 **campaign-loginmonitor** 사용자 아래의 Campaign 로그에 나타납니다.

Adobe의 내부 모니터링 외에 Campaign 클라이언트 콘솔 또는 [Campaign Campaign 컨트롤 패널](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/permissions/self-service)를 통해 직접 모니터링 기능에 액세스할 수 있습니다. Campaign 컨트롤 패널을 사용하면 인스턴스에 대한 실시간 경고를 구독하고 식별된 인시던트에 대한 권장 수정 단계를 받을 수 있습니다(예: 만료가 임박한 SSL 인증서).

**분류 모니터링**

Adobe은 다음 세 가지 계층에 걸쳐 환경을 모니터링합니다.

| 계층 | 그룹 | 비즈니스에 미치는 잠재적 영향 |
| --- | --- | --- |
| **계층 1: 인프라** | 데이터베이스 공간 소모 | 로그인, 일괄 게재 실행 또는 쿼리 실행 불능 등 성능 문제 |
| **계층 1: 인프라** | 데이터베이스 가용성 | 사용자 및 서비스가 시스템을 사용하지 못할 수 있습니다 |
| **계층 1: 인프라** | 데이터베이스 오버로드(버스트 균형) | 로그인, 일괄 게재 실행 또는 쿼리 실행 불능 등 성능 문제 |
| **계층 1: 인프라** | 데이터베이스 시퀀스 및 트랜잭션 ID 소모 | 새 워크플로우, 게재를 만들거나 일괄 처리 이메일을 보낼 수 없음 |
| **계층 1: 인프라** | SFTP 스토리지 | SFTP 서버에서 데이터를 업데이트하거나 검색할 수 없음 |
| **계층 2: 플랫폼 및 웹** | 로그인 | 사용자가 로그인하지 못할 수 있으며 예약된 활동 및 워크플로우가 실행되지 않을 수 있습니다. |
| **계층 2: 플랫폼 및 웹** | API 잠금 | 사용자 또는 서비스가 작업을 인증하거나 실행하지 못할 수 있습니다. |
| **계층 2: 플랫폼 및 웹** | 웹 | Campaign에 대한 새 연결을 만들 수 없음 |
| **계층 2: 플랫폼 및 웹** | 데이터 센터 네트워크 | 데이터 센터의 사용자에 대한 성능 문제 또는 완벽한 가용성 해제 |
| **계층 3: 소프트웨어** | 게재 추적 | 추적 로그 처리를 사용할 수 없음 |
| **계층 3: 소프트웨어** | inMail | 이메일 게재 오류 및 반송에 대한 피드백 없음 |
| **계층 3: 소프트웨어** | 메시지 센터 상태 | 트랜잭션 게재를 보낼 수 없음 |
| **계층 3: 소프트웨어** | MTA | 예약된 이메일 게재 및 임시 이메일 게재를 보낼 수 없음 |
| **계층 3: 소프트웨어** | 워크플로 서버 상태 | 워크플로우를 실행할 수 없음 |
| **계층 3: 소프트웨어** | 웹 API 가용성 | HTTP 요청을 처리하거나 API 호출을 실행할 수 없음 |
| **계층 3: 소프트웨어** | 인바운드 상호 작용 | 인바운드 상호 작용을 처리할 수 없음 |

>[!NOTE]
>
>Adobe Campaign 클라우드 서비스는 다중 클라우드 전략을 기반으로 구축되었으며 AWS 및 Azure에 배포를 제공합니다. 공급업체 차이로 인해 AWS, Azure 및 기타 데이터 센터 배포마다 모니터링 기능이 다릅니다. 위의 표는 달리 명시되지 않는 한 AWS에서 호스팅되는 Campaign Cloud Services 고객에게 적용됩니다. 또한 Adobe Campaign은 현재 On-Call 엔지니어링에 의해 사용되는 모든 모니터링 데이터를 고객에게 노출하지는 않습니다.

### 기술 워크플로 {#technical-workflows}

기술 워크플로우는 Campaign 인스턴스를 유지 관리하기 위해 백그라운드에서 실행되는 필수 프로세스입니다.

**기술 워크플로우 모니터링:**

- 일정에 따라 실행
- 오류 없이 성공적으로 완료
- 데이터를 올바르게 처리 중

**모니터링할 주요 기술 워크플로우:**

| 워크플로 | 목적 | 실패할 경우 |
| --- | --- | --- |
| **추적** | 이메일 게재의 추적 데이터를 처리합니다. | 보고서에서 지표 업데이트 중지 를 클릭하여 엽니다. |
| **정리** | 이전 데이터 및 로그를 제거하여 데이터베이스 성능 유지 | 데이터베이스의 크기가 증가하여 쿼리 및 게재 성능 저하 |
| **게재 기능 업데이트** | 게재 가능성 규칙 및 스팸 필터 패턴 업데이트 | 규칙이 부실 해지고 필터링 정확성이 저하될 수 있습니다. |
| **데이터베이스 정리** | 이전 게재 및 추적 로그 제거 | 로그 축적은 시간이 지남에 따라 쿼리 및 보고를 느리게 합니다. |

[기술 워크플로우](https://experienceleague.adobe.com/ko/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows#_blank)에 대해 자세히 알아보기

### Campaign 컨트롤 패널 {#control-panel}

Campaign Campaign 컨트롤 패널은 관리자가 Campaign 인스턴스를 모니터링하고 관리할 수 있는 셀프서비스 기능을 제공합니다.

| 모니터링 유형 | 기능 |
| --- | --- |
| **성능** | 활성 프로필 사용량 추적, 데이터베이스 사용량 및 용량 모니터링, 워크플로우 실행 상태 보기, 게재 처리량 및 지연 모니터링 |
| **인프라** | SFTP 스토리지 용량 모니터링, 하위 도메인 구성 추적, SSL 인증서 만료 모니터링, IP 허용 목록 관리 |
| **인스턴스** | 빌드 버전 및 설치된 패키지 보기, 시스템 구성 모니터링, 승인된 외부 도메인 관리 |

[Campaign 컨트롤 패널](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/permissions/self-service) 및 [Campaign 컨트롤 패널 성능 모니터링](https://experienceleague.adobe.com/ko/docs/control-panel/using/performance-monitoring/about-performance-monitoring#_blank)에 대해 자세히 알아보기

>[!NOTE]
>
>Campaign v8 Managed Cloud Services의 경우 Adobe은 서버 인프라, 운영 체제 및 애플리케이션 계층을 모니터링하고 관리합니다. [Adobe 관리 모니터링](#adobe-cloud-monitoring)에 대해 자세히 알아보세요. 이 페이지 및 Campaign 컨트롤 패널에 설명된 모니터링 기능을 사용하여 인스턴스 성능, 워크플로우 및 게재를 모니터링할 수 있습니다.

## 추적 및 보고 {#tracking-reporting}

### 메시지 추적 {#message-tracking}

수신자 행동을 추적하고 캠페인의 효과를 측정합니다.

- **열기**: 받는 사람이 전자 메일을 열 때 추적
- **클릭 수**: 받는 사람이 클릭하는 링크 모니터링
- **구독 취소**: 옵트아웃 요청 추적
- **미러 페이지 보기**: 브라우저에서 메일을 보는 수신자 수 확인

[메시지 추적](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/analytics/tracking/tracking)에 대해 자세히 알아보기

### 게재 보고서 {#delivery-reports}

Adobe Campaign은 게재 성과를 분석할 수 있는 포괄적인 보고서 세트를 제공합니다.

- **게재 요약**: 전송, 게재 및 실패 개요
- **추적 표시기**: 열기, 클릭 수 및 클릭스루 비율
- **URL 및 클릭 스트림**: 게재에서 가장 많이 사용되는 링크
- **핫 클릭**: 받는 사람이 전자 메일을 클릭한 위치를 시각적으로 표시합니다.

[게재 보고서](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/analytics/reports/ac-reports/delivery-reports)에 대해 자세히 알아보기

### 전반적 보고서 {#global-reports}

글로벌 보고서에 액세스하여 모든 캠페인 및 게재의 성과를 분석할 수 있습니다.

- **게재 처리량**: 시간 경과에 따라 전송된 메시지
- **게재 불가 및 바운스**: 실패한 게재 분석
- **사용자 활동**: 모든 캠페인에서 열기, 클릭, 구독 취소

[글로벌 보고서](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/analytics/reports/ac-reports/global-reports)에 대해 자세히 알아보기

## 관련 항목 {#related-topics}

- [게재 모범 사례](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/send/delivery-best-practices)
- [격리 관리](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/send/monitor/quarantines)
- [게재 구성 및 보내기](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/send/validate/configure-and-send)
- [보고 시작](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/analytics/reports/gs-reporting)
