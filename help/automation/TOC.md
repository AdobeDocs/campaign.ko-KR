---
audience: user
user-guide-title: Campaign Automation 안내서
user-guide-description: Campaign Automation 안내서
source-git-commit: 7fe079c5473fa164405753c2be6cc8be16329f58
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 85%

---


# Campaign 자동화 안내서 {#automation}

+ [Campaign Automation 안내서](home.md)
+ 워크플로우 자동화 {#workflows}
   + 워크플로우 시작 {#introduction}
      + [워크플로우 정보](workflow/about-workflows.md)
      + 워크플로우 유형 {#wf-type}
         + [타겟팅 워크플로우](workflow/targeting-workflows.md)
         + [캠페인 워크플로우](workflow/campaign-workflows.md)
         + [기술 워크플로우](workflow/technical-workflows.md)
      + [워크플로우 구축](workflow/build-a-workflow.md)
      + [모범 사례](workflow/workflow-best-practices.md)
      + [워크플로우 데이터 사용](workflow/use-workflow-data.md)
   + 워크플로우 실행 {#executing-a-workflow}
      + [워크플로우 시작](workflow/start-a-workflow.md)
      + [워크플로우 수명 주기](workflow/workflow-life-cycle.md)
      + [승인 설정](workflow/define-approvals.md)
   + 워크플로우 모니터링 {#monitoring-workflows}
      + [워크플로우 실행 모니터링](workflow/monitor-workflow-execution.md)
      + [기술 워크플로우 모니터링](workflow/monitor-technical-workflows.md)
      + [워크플로우 히트맵](workflow/heatmap.md)
   + 워크플로우 활동 {#wf-activities}
      + [활동 시작](workflow/activities.md)
      + 타겟팅 활동 {#targeting-activities}
         + [타겟팅 활동 목록](workflow/targeting-activities.md)
         + [셀](workflow/cells.md)
         + [데이터 소스 변경](workflow/change-data-source.md)
         + [차원 변경](workflow/change-dimension.md)
         + [CRM 커넥터](workflow/crm-connector.md)
         + [중복 제거](workflow/deduplication.md)
         + [게재 개요](workflow/delivery-outline.md)
         + [스키마 편집](workflow/edit-schema.md)
         + [데이터 보강](workflow/enrichment.md)
         + [예외](workflow/exclusion.md)
         + [증분 쿼리](workflow/incremental-query.md)
         + [교차](workflow/intersection.md)
         + [목록 업데이트](workflow/list-update.md)
         + [셀별 오퍼](workflow/offers-by-cell.md)
         + [오퍼 엔진](workflow/offer-engine.md)
         + [쿼리](workflow/query.md)
         + [목록 읽기](workflow/read-list.md)
         + [분할](workflow/split.md)
         + [구독 서비스](workflow/subscription-services.md)
         + [결합](workflow/union.md)
         + [데이터 업데이트](workflow/update-data.md)
      + 흐름 제어 활동 {#flow-control-activities}
         + [흐름 제어 활동 목록](workflow/flow-control-activities.md)
         + [경고](workflow/alert.md)
         + [AND-결합](workflow/and-join.md)
         + [승인](workflow/approval.md)
         + [외부 신호](workflow/external-signal.md)
         + [포크](workflow/fork.md)
         + [이동(시작점 및 끝점)](workflow/jump--start-point-and-end-point-.md)
         + [시작 및 종료](workflow/start-and-end.md)
         + [예약](workflow/scheduler.md)
         + [하위 워크플로우](workflow/sub-workflow.md)
         + [테스트](workflow/test.md)
         + [시간 제한](workflow/time-constraint.md)
         + [대기](workflow/wait.md)
      + 작업 활동 {#action-activities}
         + [작업 활동 목록](workflow/action-activities.md)
         + [콘텐츠 관리](workflow/content-management.md)
         + [지속적인 게재](workflow/continuous-delivery.md)
         + [크로스 채널 게재](workflow/cross-channel-deliveries.md)
         + [데이터 추출(파일)](workflow/extraction--file-.md)
         + [데이터 로딩(파일)](workflow/data-loading--file-.md)
         + [데이터 로딩(RDBMS)](workflow/data-loading--rdbms-.md)
         + [게재](workflow/delivery.md)
         + [게재 제어](workflow/delivery-control.md)
         + [로컬 승인](workflow/local-approval.md)
         + [로딩(SOAP)](workflow/loading-soap.md)
         + [Nlserver 모듈](workflow/nlserver-module.md)
         + [반복 게재](workflow/recurring-delivery.md)
         + [SQL 코드 및 JavaScript 코드](workflow/sql-code-and-javascript-code.md)
         + [SQL 데이터 관리](workflow/sql-data-management.md)
         + [집계 업데이트](workflow/update-aggregate.md)
      + 이벤트 활동 {#event-activities}
         + [이벤트 활동 목록](workflow/event-activities.md)
         + [파일 수집기](workflow/file-collector.md)
         + [파일 전송](workflow/file-transfer.md)
         + [인바운드 이메일](workflow/inbound-emails.md)
         + [인바운드 SMS](workflow/inbound-sms.md)
         + [웹 다운로드](workflow/web-download.md)
   + 사용 사례 {#use-cases}
      + [워크플로우 사용 사례 기본 정보](workflow/workflow-use-cases.md)
      + 게재 {#deliveries}
         + [로컬 승인 활동 사용](workflow/local-approval-activity.md)
         + [생일 이메일 보내기](workflow/send-a-birthday-email.md)
         + [게재 콘텐츠 로드](workflow/load-delivery-content.md)
         + [크로스 채널 게재 워크플로우](workflow/cross-channel-delivery-workflow.md)
         + [사용자 정의 날짜 필드를 통한 이메일 강화](workflow/email-enrichment-with-custom-date-fields.md)
      + 모니터링 {#monitoring}
         + [목록으로 보고서 보내기](workflow/send-a-report-to-a-list.md)
         + [워크플로우 관리](workflow/workflow-supervision.md)
         + [운영자에게 개인화된 경고 보내기](workflow/send-alerts-to-operators.md)
      + 데이터 관리 {#data-management}
         + [데이터 업데이트 조정](workflow/coordinate-data-updates.md)
         + [요약 목록 만들기](workflow/create-a-summary-list.md)
         + [데이터 강화](workflow/enrich-data.md)
         + [집계 사용](workflow/using-aggregates.md)
         + [중복 제거 활동의 병합 기능 사용](workflow/deduplication-merge.md)
         + [가져오기 반복 워크플로우 설정](workflow/recurring-import-workflow.md)
      + 쿼리 디자인 {#designing-queries}
         + [증분 쿼리를 사용한 분기별 목록 업데이트](workflow/quarterly-list-update.md)
      + 쿼리 및 필터 {#designing-queries}
         + [수신자 테이블 쿼리](workflow/querying-recipient-table.md)
         + [쿼리 게재 정보](workflow/query-delivery-info.md)
         + [계산 집계](workflow/compute-aggregates.md)
         + [그룹 관리를 사용한 쿼리](workflow/query-grouping-management.md)
         + [다대다 관계를 사용한 쿼리](workflow/query-many-to-many-relationship.md)
         + [열거형 계산 필드 추가](workflow/adding-enumeration-type-calculated-field.md)
         + [필터 만들기](workflow/create-a-filter.md)
         + [중복 수신자 필터링](workflow/filter-duplicated-recipients.md)
   + 고급 설정 {#advanced-management}
      + [워크플로우 속성](workflow/workflow-properties.md)
      + [고급 매개 변수](workflow/advanced-parameters.md)
      + [JavaScript 스크립트 및 템플릿](workflow/javascript-scripts-and-templates.md)
      + [워크플로우의 JavaScript 코드 예](workflow/javascript-in-workflows.md)
      + [외부 데이터베이스 액세스](workflow/accessing-an-external-database--fda-.md)
      + [권한 관리](workflow/managing-rights.md)
      + [활동 이미지 변경](workflow/change-activity-images.md)
      + [표준 시간대 관리](workflow/managing-time-zones.md)
+ 캠페인 오케스트레이션 {#campaign-orchestration}
   + [마케팅 캠페인 시작](campaigns/set-up-campaigns.md)
   + [프로그램 및 캠페인 만들기](campaigns/marketing-campaign-create.md)
   + [템플릿 만들기 및 구성](campaigns/marketing-campaign-templates.md)
   + [게재 추가](campaigns/marketing-campaign-deliveries.md)
   + [대상자 선택](campaigns/marketing-campaign-target.md)
   + [문서 및 에셋 관리](campaigns/marketing-campaign-assets.md)
   + [승인 설정 및 관리](campaigns/marketing-campaign-approval.md)
   + [반복 및 정기 캠페인](campaigns/recurring-periodic-campaigns.md)
   + [캠페인 모니터링](campaigns/marketing-campaign-monitoring.md)
   + [공급자, 재고 및 예산](campaigns/providers--stocks-and-budgets.md)
+ Campaign 최적화(추가 기능){#campaign-optimization}
   + [캠페인 유형화 시작](campaign-opt/campaign-typologies.md)
   + [필터링 규칙](campaign-opt/filtering-rules.md)
   + [제어 규칙](campaign-opt/control-rules.md)
   + [압력 규칙](campaign-opt/pressure-rules.md)
   + [일관성 규칙](campaign-opt/consistency-rules.md)
   + [규칙 적용](campaign-opt/apply-rules.md)
   + [캠페인 시뮬레이션](campaign-opt/campaign-simulations.md)
+ 분산 마케팅(추가 기능) {#distributed-marketing}
   + [분산 마케팅 정보](distributed-marketing/about-distributed-marketing.md)
   + [로컬 캠페인 만들기](distributed-marketing/creating-a-local-campaign.md)
   + [공동 캠페인 만들기](distributed-marketing/creating-a-collaborative-campaign.md)
   + [캠페인 패키지 게시](distributed-marketing/publishing-the-campaign-package.md)
   + [캠페인 액세스](distributed-marketing/accessing-campaigns.md)
   + [캠페인 추적](distributed-marketing/tracking-a-campaign.md)
   + [활용 사례](distributed-marketing/examples.md)
+ [Campaign v8 설명서](https://experienceleague.adobe.com/docs/campaign/campaign-v8/campaign-home.html?lang=ko)