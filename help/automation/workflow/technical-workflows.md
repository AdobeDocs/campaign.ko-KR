---
product: campaign
title: 기술 워크플로
description: Campaign에서 사용할 수 있는 기술 워크플로우에 대해 자세히 알아보기
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: 2693856c-80b2-4e35-be8e-2a9760f8311f
source-git-commit: f75b95faa570d7c3f59fd8fb15692d3c3cbe0d36
workflow-type: tm+mt
source-wordcount: '2064'
ht-degree: 0%

---

# 기술 워크플로{#about-technical-workflows}

Adobe Campaign에는 기술 워크플로우가 내장되어 있습니다. 서버에서 주기적으로 실행되도록 예약된 작업과 작업을 제어합니다. 기술 워크플로우는 Campaign 데이터베이스에서 유지 관리 작업을 실행하고, 게재의 추적 데이터를 관리하며, 게재의 임시 프로세스를 설정합니다.

기본적으로 기술 워크플로우는 **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]** 노드의 하위 폴더에서 사용할 수 있습니다.

![](assets/navtree.png){width="50%" align="left" zoomable="yes"}

>[!NOTE]
>
>* 각 모듈과 함께 설치된 기술 워크플로우 목록은 [이 섹션](#list-technical-workflows)에서 사용할 수 있습니다.
>
>* 메시지 센터 추가 기능과 관련된 기술 워크플로는 기본적으로 **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Message Center]** > **[!UICONTROL Technical workflows]** 노드에 저장됩니다.

**[!UICONTROL Campaign process]** 하위 폴더는 캠페인 내에서 프로세스를 실행하는 데 필요한 워크플로(작업 알림, 재고 관리, 비용 계산 등)를 중앙 집중화합니다.

![](assets/campaign-processes-wf.png)

## 기술 워크플로우 관리 및 만들기 {#manage-tech-workflows}

**관리** 권한이 있는 운영자만 Campaign 기술 워크플로우를 시작하고 수정할 수 있습니다. 이 [전용 섹션](monitor-technical-workflows.md)에서 기술 워크플로우를 모니터링하는 방법을 알아봅니다.

트리 구조의 **[!UICONTROL Administration > Production > Technical workflows]** 노드에서 사용자 지정 기술 워크플로우를 만들 수 있습니다. 기술 워크플로우를 만드는 데 기본 템플릿을 사용할 수 있습니다. 필요에 맞게 구성할 수 있습니다. 그러나 이 프로세스는 전문가 사용자용으로 예약되어 있습니다. 기술 워크플로우에서 사용할 수 있는 활동은 타겟팅 워크플로우와 동일합니다. [자세히 알아보기](targeting-workflows.md)

## 내장 기술 워크플로우 {#list-technical-workflows}

이 페이지에 설명된 워크플로우는 Adobe Campaign 기본 제공 패키지와 함께 설치됩니다. 이러한 패키지 및 관련 기술 워크플로우는 라이선스 계약 및 추가 기능에 따라 다릅니다.

| 기술 워크플로 | 패키지 | 설명 |
|------|--------|-----------|
| **별칭 정리**(aliasCleaning) | 기본적으로 설치됨 | 이 워크플로는 [열거형](../../v8/config/enumerations.md#alias-cleansing) 값을 표준화합니다. 기본적으로 매일 오전 3시에 트리거됩니다. |
| **청구**(청구) | 기본적으로 설치됨 | 이 워크플로우는 &#39;과금&#39; 운영자에게 이메일로 시스템 활동 보고서를 보냅니다. 마케팅 인스턴스에서 매월 25일에 트리거됩니다. |
| **캠페인 작업**(operationMgt) | 기본적으로 설치됨 | 이 워크플로우는 마케팅 캠페인(론치 타기팅, 파일 추출 등)에 대한 작업을 관리합니다. 또한 반복 및 정기 캠페인과 관련된 워크플로우를 만듭니다. |
| **HeatMap 서비스에 대한 데이터 수집**(collectDataHeatMapService) | 기본적으로 설치됨 | 이 워크플로우는 HeatMap 서비스에 필요한 데이터를 검색합니다. |
| **개인 정보 보호 요청 수집**(collectPrivacyRequests) | 개인 정보 보호 규정 | 이 워크플로우는 Adobe Campaign에 저장된 수신자의 데이터를 생성하여 개인 정보 보호 요청의 화면에서 다운로드할 수 있도록 합니다. |
| **비용 계산**(budgetMgt) | 기본적으로 설치됨 | 이 워크플로우에서는 예산, 계획, 프로그램, 캠페인, 게재 및 태스크에 대한 경비 및 원가 라인 계산을 시작합니다. |
| **데이터베이스 정리**(정리) | 기본적으로 설치됨 | 이 워크플로우는 데이터베이스 유지 관리 워크플로우입니다. 통계 및 프로세스에서 다른 계산을 수행하고 배포 도우미에 정의된 구성에 따라 데이터베이스에서 오래된 데이터를 삭제합니다. 기본적으로 매일 오전 4시에 트리거됩니다. |
| **차단된 LINE 사용자 삭제**(deleteBlockedLineUsersV2) | LINE 채널 | 이 워크플로우에서는 180일 동안 LINE 공식 계정을 차단한 후 LINE V2 사용자의 데이터를 삭제합니다. |
| **개인 정보 보호 요청 데이터 삭제**(deletePrivacyRequestsData) | 개인 정보 보호 규정 | 이 워크플로우는 Adobe Campaign에 저장된 수신자의 데이터를 삭제합니다. |
| **게재 표시기**(deliveryIndicators) | 기본적으로 설치됨 | 이 워크플로우는 게재에 대한 게재 추적 지표를 업데이트합니다. 이 워크플로우는 기본적으로 매 시간마다 트리거됩니다. |
| **FFDA를 즉시 배포**(ffdaDeploy) | 기본적으로 [Campaign Enterprise(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)에만 설치됩니다. | 클라우드 데이터베이스에 대한 즉각적인 배포를 수행합니다. [데이터 복제에 대해 자세히 알아보기](../../v8/architecture/replication.md) |
| **분산 마케팅 프로세스**(centralLocalMgt) | 중앙/로컬 마케팅(분산 마케팅) | 이 워크플로우는 분산 마케팅 모듈 사용과 관련된 처리를 시작합니다. 로컬 캠페인 생성을 시작하고 주문 및 캠페인 패키지 가용성과 관련된 알림을 관리합니다. |
| **이벤트 제거**(webAnalyticsPurgeWebEvents) | 웹 분석 커넥터 | 이 워크플로우를 사용하면 수명 필드에 구성된 기간에 따라 데이터베이스 필드에서 모든 이벤트를 삭제할 수 있습니다. |
| **Adobe Experience Cloud으로 대상 내보내기**(exportSharedAudience) | Adobe Experience Cloud과 통합 | 이 워크플로우에서는 대상을 공유 대상/세그먼트로 내보냅니다. 이러한 대상은 사용하는 다른 Adobe Experience Cloud 솔루션에서 사용할 수 있습니다. |
| **예측**(예측) | 기본적으로 설치됨 | 이 워크플로우는 임시 캘린더에 저장된 게재를 분석합니다(임시 로그 생성). 기본적으로 매일 오전 1시에 트리거됩니다. |
| **전체 집계 계산(propositionrcp 큐브)**(agg_nmspropositionrcp_full) | 오퍼 엔진(상호 작용) | 이 워크플로우는 오퍼 제안 큐브에 대한 전체 집계를 업데이트합니다. 기본적으로 매일 오전 6시에 트리거됩니다. 이 집계는 채널, 게재, 마케팅 오퍼 및 날짜 차원을 캡처합니다. 그런 다음 오퍼 제안 큐브를 사용하여 오퍼를 기반으로 보고서를 생성합니다. [이 섹션](../../v8/reporting/gs-cubes.md)에서 큐브에 대해 자세히 알아보세요. |
| **변환된 연락처 식별**(webAnalyticsFindConverted) | 웹 분석 커넥터 | 이 워크플로우는 리마케팅 캠페인 후 구매를 완료한 사이트 방문자를 색인화합니다. 이 워크플로우에서 복구한 데이터는 리마케팅 효율성 보고서에서 액세스할 수 있습니다(이 페이지 참조). |
| **Adobe Experience Cloud에서 대상 가져오기**(importSharedAudience) | Adobe Experience Cloud과 통합 | 이 워크플로우를 통해 다른 Adobe Experience Cloud 솔루션의 대상/세그먼트를 Adobe Campaign으로 가져올 수 있습니다. |
| **캠페인의 게재에 대한 작업**(deliveryMgt) | 기본적으로 설치됨 | 이 워크플로우는 승인된 게재를 트리거하고 외부 게재에 대한 서비스 공급자의 사후 처리를 시작합니다. 승인 알림과 미리 알림도 보냅니다. |
| 서비스 공급자의 **작업**(supplierMgt) | 기본적으로 설치됨 | 게재가 승인되면 이 워크플로우는 공급자 처리(라우터로의 이메일 전송 및 사후 처리)를 시작합니다. |
| **MID에서 LineUserID로 마이그레이션**(MIDToUserIDMigration) | LINE 채널 | 이 워크플로우는 LINE V1에서 LINE V2로 마이그레이션할 LINE V2 사용자의 ID를 생성합니다. |
| **메시지 센터 &lt;external_account_name>**(mcSynch_&lt;external_account_name>) | 트랜잭션 메시지 제어(메시지 센터 - 제어) | 이 워크플로우는 <ul><li>작업에서 처리된 이벤트 목록을 복구합니다.</li><li>게재 메시지 자격을 복구하려면 NmsBroadLogMsg 테이블과 동기화합니다.</li><li>nmsBroadLogMsg 테이블과의 동기화가 완료되는 즉시 이벤트 게재 로그를 복구합니다.</li><li>는 게재 URL에 대한 추적을 복구하기 위해 NmsTrackingUrl 테이블과 동기화합니다.</li><li>nmsTrackingUrl 테이블과의 동기화가 완료되는 즉시 이벤트 추적 URL을 복구합니다.</li><li>게재를 보낸 후 3시간마다 격리된 모든 이메일 주소를 복구할 수 있습니다.</li></ul> |
| **MessageCenter 전체 집계 계산**(agg_messageCenter_full) | 트랜잭션 메시지 제어(메시지 센터 - 제어) | 이 워크플로우는 메시지 센터 큐브에 대한 전체 집계를 업데이트합니다. 기본적으로 매일 오전 3시에 트리거됩니다. 이 집계는 채널, 날짜, 상태 및 이벤트 유형과 같은 차원을 캡처합니다. 그런 다음 메시지 센터 큐브를 사용하여 이벤트를 기반으로 보고서를 생성합니다. 큐브에 대한 자세한 내용은에서 확인할 수 있습니다.  |
| **중간 소싱(게재 카운터)**(defaultMidSourcingDlv) | 중간 소싱으로 전송 | 이 워크플로우는 중간 소싱 서버의 게재에 대한 카운트 정보를 수집합니다. 카운트 정보에는 전송된 게재 수 등과 같은 일반 게재 지표가 포함됩니다. 열림 등의 추적 정보는 포함되지 않습니다. 기본적으로 10분마다 트리거됩니다. |
| **중간 소싱(게재 로그)**(defaultMidSourcingLog) | 중간 소싱으로 전송 | 이 워크플로우는 중간 소싱 서버에서 게재 로그를 수집합니다. 기본적으로 매시간 트리거됩니다. |
| **NMAC 옵트아웃 관리**(mobileAppOptOutMgt) | 모바일 앱 채널(푸시) | 이 워크플로우는 모바일 장치에 대한 구독 취소 알림을 업데이트합니다. 오전 1시부터 자정까지 6시간마다 트리거됩니다. |
| **오퍼 알림**(offerMgt) | 기본적으로 설치됨 | 이 워크플로는 승인된 오퍼를 오퍼 카탈로그에 포함된 모든 범주와 온라인 환경에 배포합니다. |
| **일시 중지된 워크플로 정리**(cleanupPausedWorkflows) | 기본적으로 설치됨 | 이 워크플로우는 심각도가 정상으로 설정된 일시 중지된 워크플로우를 분석하고, 너무 오랫동안 일시 중지된 경우 경고 및 알림을 트리거합니다. 한 달 후 일시 중지된 기술 워크플로우는 무조건 중지됩니다. 기본적으로 매주 월요일 오전 5시에 트리거됩니다. 자세한 내용은 [일시 중지된 워크플로 처리](monitor-workflow-execution.md#handling-of-paused-workflows)를 참조하십시오. |
| **개인 정보 보호 요청 정리**(cleanupPrivacyRequests) | 개인 정보 보호 규정 | 이 워크플로우는 90일 이전의 액세스 요청 파일을 삭제합니다. |
| **일괄 처리 이벤트 처리**(batchEventsProcessing) | 트랜잭션 메시지 실행(메시지 센터 - 실행) | 이 워크플로우를 사용하면 메시지 템플릿과 연결하기 전에 일괄 처리 이벤트를 대기열에 넣을 수 있습니다. |
| **실시간 이벤트 처리**(rtEventsProcessing) | 트랜잭션 메시지 실행(메시지 센터 - 실행) | 이 워크플로우를 사용하면 실시간 이벤트를 메시지 템플릿과 연결하기 전에 대기열에 넣을 수 있습니다. |
| **제안 동기화**(propositionSynch) | 실행 인스턴스가 있는 오퍼 엔진 제어 | 이 워크플로우는 상호 작용에 사용되는 마케팅 인스턴스와 실행 인스턴스 간의 제안을 동기화합니다. |
| **웹 이벤트 복구**(webAnalyticsGetWebEvents) | 웹 분석 커넥터 | 매시간마다 이 워크플로우는 주어진 사이트에서 인터넷 사용자 비헤이비어에 대한 세그먼트를 다운로드하여 Adobe Campaign 데이터베이스에 넣고 리마케팅 워크플로우를 시작합니다. |
| **FFDA 데이터를 즉시 복제**(ffdaReplicate) | 기본적으로 [Campaign Enterprise(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)에만 설치됩니다. | 지정된 외부 계정에 대한 XS 데이터를 복제합니다. [데이터 복제에 대해 자세히 알아보기](../../v8/architecture/replication.md) |
| **nmsDelivery 큐 복제**(ffdaReplicateQueueDelivery) | 기본적으로 [Campaign Enterprise(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)에만 설치됩니다. | `nms:delivery` 테이블에 대한 큐. [데이터 복제에 대해 자세히 알아보기](../../v8/architecture/replication.md) |
| **nmsDlvExclusion 큐 복제**(ffdaReplicateQueueDlvExclusion) | 기본적으로 [Campaign Enterprise(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)에만 설치됩니다. | `nms:dlvExclusion` 테이블에 대한 큐. [데이터 복제에 대해 자세히 알아보기](../../v8/architecture/replication.md) |
| **nmsDlvMidRemoteIdRel 큐 복제**(ffdaReplicateQueueDlvMidRemoteIdRel) | 기본적으로 [Campaign Enterprise(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)에만 설치됩니다. | `nms:dlvRemoteIdRel` 테이블에 대한 큐. [데이터 복제에 대해 자세히 알아보기](../../v8/architecture/replication.md) |
| **nmsTrackingUrl 큐 복제**(ffdaReplicateQueueTrackingUrl)<br/>**동시 실행 시 nmsTrackingUrl 큐 복제**(ffdaReplicateQueueTrackingUrl_2) | 기본적으로 [Campaign Enterprise(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)에만 설치됩니다. | 서로 다른 우선 순위를 기준으로 요청을 처리하여 효율성을 개선하기 위해 두 개의 워크플로우를 활용하는 `nms:trackingUrl` 테이블의 동시 큐. [데이터 복제에 대해 자세히 알아보기](../../v8/architecture/replication.md) |
| **참조 테이블 복제**(ffdaReplicateReferenceTables) | 기본적으로 [Campaign Enterprise(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)에만 설치됩니다. | Campaign 로컬 데이터베이스(PostgreSQL) 및 클라우드 데이터베이스([!DNL Snowflake])에 있어야 하는 기본 제공 테이블의 자동 복제를 수행합니다. 매시간, 매일 실행되도록 예약되어 있습니다. **lastModified** 필드가 있으면 복제가 점진적으로 발생하고 그렇지 않으면 전체 테이블이 복제됩니다. [데이터 복제에 대해 자세히 알아보기](../../v8/architecture/replication.md) |
| **스테이징 데이터 복제**(ffdaReplicateStagingData) | 기본적으로 [Campaign Enterprise(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)에만 설치됩니다. | 단일 호출에 대한 스테이징 데이터를 복제합니다. 매시간, 매일 실행되도록 예약되어 있습니다. [데이터 복제에 대해 자세히 알아보기](../../v8/architecture/replication.md) |
| **집계 보고**(reportingAggregates) | 게재 | 이 워크플로우는 보고서에 사용된 합계를 업데이트합니다. 기본적으로 매일 오전 2시에 트리거됩니다. |
| **지표 및 캠페인 특성 전송**(webAnalyticsSendMetrics) | 웹 분석 커넥터 | 이 워크플로우를 사용하면 Adobe® Analytics 커넥터를 통해 Adobe Campaign에서 Adobe Experience Cloud Suite로 이메일 캠페인 지표를 보낼 수 있습니다. 관련 지표는 다음과 같습니다. 전송됨(iSent), 총 열람 수(iTotalRecipientOpen), 클릭한 총 수신자 수(iTotalRecipientClick), 오류(iError), 옵트아웃(optOut) |
| **재고: 주문 및 경고**(stockMgt) | 기본적으로 설치됨 | 이 워크플로우는 주문 라인에서 재고 계산을 시작하고 경고 경고 임계값을 관리합니다. |
| **Adobe Experience Platform 데이터 수집에서 모바일 앱 동기화**(syncWithLaunch) | 기본적으로 설치됨, v8.5부터 | 이 워크플로우는 데이터 수집에서 모바일 속성을 Adobe Campaign에 자동으로 동기화합니다. |
| **추적**(추적) | 기본적으로 설치됨 | 이 워크플로우는 추적 정보의 복구 및 통합을 수행합니다. 또한 특히 메시지 센터 아카이빙 워크플로우에서 사용하는 추적 및 게재 통계를 다시 계산할 수 있습니다. 기본적으로 시간당 한 번 트리거됩니다. |
| **이벤트 상태 업데이트**(updateEventsStatus) | 트랜잭션 메시지 실행(메시지 센터 - 실행) | 이 워크플로우를 통해 이벤트에 상태를 할당할 수 있습니다. 이벤트 상태는 다음과 같습니다.<ul><li>보류 중: 이벤트가 큐에 있습니다. 아직 연결된 메시지 템플릿이 없습니다.</li><li>게재 보류 중: 이벤트가 큐에 있고 메시지 템플릿이 연결되어 있으며 현재 게재에서 처리 중입니다.</li><li>전송됨: 이 상태는 게재 로그에서 복사됩니다. 게재가 전송되었음을 의미합니다.</li><li>게재에서 무시됨: 이 상태는 게재 로그에서 복사됩니다. 게재가 무시되었음을 의미합니다.</li><li>게재 오류: 이 상태는 게재 로그에서 복사됩니다. 게재가 실패했다는 뜻입니다.</li><li>이벤트가 포함되지 않음: 이벤트를 메시지 템플릿과 연결하지 못했습니다. 이벤트는 재처리되지 않습니다.</li></ul> |
| **게재 능력을 위한 업데이트**(게재 가능성 업데이트) | 기본적으로 설치됨 | 전달성 모니터링(이메일 전달성) 패키지가 설치되면 이 워크플로우는 매일 밤 실행되며 바운스 이메일 자격 규칙과 도메인 및 MX 목록을 관리합니다. 이렇게 하려면 플랫폼에서 HTTPS 포트를 열어야 합니다. |
| **구독 취소 업데이트**(ffdaUnsuscribe) | 기본적으로 [Campaign Enterprise(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)에만 설치됩니다. | 이 워크플로는 `<mailto>` 목록 구독 취소 메서드를 사용하여 바운스 메일로 다시 받은 구독 취소를 처리합니다. 엔터프라이즈(FFDA) 배포가 있는 마케팅 인스턴스에서만 1시간마다 매일 실행됩니다.<br/><br/>워크플로는 inMail 모듈(NmsBroadLog 테이블의 iFlags 열에 설정된 표시)에서 구독 취소로 표시된 특정 시간 범위(마지막 처리 시간 및 현재 시간)의 브로드로그를 확인하고 브로드로그 서비스의 설정 여부에 따라 구독 취소를 처리합니다.<ul><li>serviceId가 0(정의되지 않음)이면 수신자는 차단 목록에 추가된으로 수신됩니다.</li><li>serviceId가 0(기존 서비스에 연결됨)이 아니면 수신자는 해당 서비스의 구독을 취소하게 됩니다.</li></ul><br/>참고: 이 워크플로는 바운스 구독 취소만 처리합니다. 구독 취소는 옵트아웃 링크를 통해 수행되고 원클릭 구독 취소(URL 메서드)는 이 워크플로의 외부에서 별도로 처리됩니다. |
