---
audience: end-user
user-guide-title: Campaign v8
user-guide-description: Adobe Campaign v8(클라이언트 콘솔)의 제품 설명서입니다.
title: Adobe Campaign v8 설명서
description: Campaign v8 설명서
breadcrumb-title: Campaign v8 설명서
source-git-commit: 4a62c551c43cd5a4866df36cce10e294f35db363
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 89%

---


# Adobe Campaign v8(콘솔) 설명서 {#campaign-v8}

+ [Campaign v8 설명서](campaign-home.md)
+ 릴리스 정보 {#releases}
   + [초기 릴리스 정보](start/e-release-notes.md)
   + [버전 및 업그레이드](start/upgrades.md)
   + [최신 릴리스](start/release-notes.md)
   + 이전 릴리스 {#previous-rn}
      + [2025](start/release-notes-2025.md)
      + [2024](start/release-notes-2024.md)
      + [2023](start/release-notes-2023.md)
      + [2022](start/release-notes-2022.md)
      + [2021](start/release-notes-2021.md)
   + [보호 기능](start/ac-guardrails.md)
   + [알려진 문제](start/known-issues.md)
   + [호환성 매트릭스](start/compatibility-matrix.md)
   + [설명서 업데이트](start/documentation-updates.md)
+ 시작 {#new}
   + [Adobe Campaign 시작](start/get-started.md)
   + [주요 기능](start/whats-new.md)
   + [사용자 인터페이스 살펴보기](start/campaign-ui.md)
   + [Campaign에 연결](start/connect.md)
   + [구성 요소 및 프로세스](start/ac-components.md)
   + [Campaign Classic v7에서 v8로의 전환](start/v7-to-v8.md)
   + [Campaign Standard에서 v8로의 전환](start/acs-to-v8.md)
   + [FAQ](start/campaign-faq.md)
+ 캠페인 관리 {#campaigns}
   + [캠페인 시작하기](start/campaigns.md)
   + [캠페인 오케스트레이션 >](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=ko)
+ 메시지 보내기{#send}
   + [메시지 시작하기](start/gs-message.md)
   + [첫 게재 만들어 보기](start/create-message.md)
   + [게재 모범 사례](start/delivery-best-practices.md)
   + 이메일 {#emails}
      + [이메일 디자인 및 유효성 검사](send/email.md)
      + [미러 페이지로 가는 링크](send/mirror-page.md)
      + [BCC 주소 추가](send/email-bcc.md)
      + [추가 이메일 매개 변수 정의](send/email-parameters.md)
      + [이메일 보내기 및 모니터링](send/send.md)
   + SMS {#sms}
      + [SMS 시작](send/sms/sms.md)
      + SMS 채널 구성 {#config-sms}
         + [SMS 게재 설정](send/sms/sms-delivery-settings.md)
         + [SMPP 외부 계정 설정](send/sms/smpp-external-account.md)
         + [SMS 채널 특성](send/sms/sms-channel.md)
         + [SMPP 연결 유효성 검사](send/sms/smpp-connection.md)
         + [독립형 인스턴스](send/sms/sms-standalone-instance.md)
         + [중간 소싱 인프라](send/sms/sms-mid-sourcing.md)
         + [SMPP 커넥터 설명](send/sms/smpp-connector-delivery.md)
      + SMS 만들기  {#create-sms}
         + [SMS 게재 만들기](send/sms/create-sms.md)
         + [콘텐츠 정의](send/sms/sms-content.md)
         + [대상자 선택](send/sms/sms-audience.md)
      + SMS 확인 및 보내기 {#validate-sms}
         + [SMS 증명 보내기](send/sms/sms-proofs.md)
         + [대상자에게 보내기](send/sms/sms-send.md)
      + [SMS 모니터링 및 추적](send/sms/sms-monitor.md)
   + 푸시 알림 {#push}
      + [푸시 알림 구성 및 전송](send/push.md)
      + 리치 푸시 {#rich-push}
         + [Android 리치 푸시 게재 디자인](send/rich-push-android.md)
         + [iOS 리치 푸시 게재 디자인](send/rich-push-ios.md)
      + [푸시 알림 채널 구성](send/push-settings.md)
      + [데이터 수집으로 푸시 알림 구성](send/push-data-collection.md)
   + [LINE 메시지 보내기](send/line.md)
   + [DM](send/direct-mail.md)
   + [X(Twitter)](send/twitter.md)
   + [사용자 지정 외부 채널](send/custom-channel.md)
   + 콘텐츠 개인화 {#personalize}
      + [개인화 시작하기](send/personalize.md)
      + [개인화 데이터](send/personalization-data.md)
      + [개인화 필드 추가](send/personalization-fields.md)
      + [개인화 블록 사용](send/personalization-blocks.md)
      + [조건 만들기](send/conditions.md)
   + 게재 확인 및 보내기 {#validate}
      + [미리 보기 및 교정쇄](send/preview-and-proof.md)
      + [게재 분석](send/delivery-analysis.md)
      + [게재 구성 및 보내기](send/configure-and-send.md)
      + [전송 시간 최적화](send/predictive.md)
   + 실패, 바운스 및 격리{#failures}
      + [격리](send/quarantines.md)
      + [게재 실패](send/delivery-failures.md)
   + [게재 템플릿 작업](send/create-templates.md)
   + 트랜잭션 메시지 {#real-time}
      + [트랜잭션 메시지 시작](send/transactional.md)
      + [템플릿 만들기 및 게시](send/transactional-template.md)
      + 이벤트 관리 {#event}
         + [이벤트 수집 및 처리](send/event-processing.md)
         + [이벤트 설명 이해](send/event-description.md)
         + [메시지 전송 및 모니터링](send/delivery-execution.md)
+ 프로필 및 대상자 관리 {#audience}
   + [프로필 및 대상자 시작](audiences/gs-audiences.md)
   + [대상자를 사용한 작업](start/audiences.md)
   + [프로필 액세스](audiences/view-profiles.md)
   + 프로필 추가 {#add-profiles}
      + [수동으로 프로필 만들기](audiences/create-profiles.md)
      + [파일에서 프로필 가져오기](audiences/import-profiles.md)
      + [외부 프로필 작업](audiences/external-profiles.md)
      + [웹 양식에서 프로필 데이터 수집](audiences/collect-profiles.md)
      + [대상 매핑 작업](audiences/target-mappings.md)
      + [테스트 프로필 만들기](audiences/test-profiles.md)
   + 대상자 만들기 {#create-audiences}
      + [연락처 목록 만들기](audiences/create-audiences.md)
      + [필터 만들기 및 관리](audiences/create-filters.md)
      + [Adobe 솔루션으로 대상자 공유](start/shared-audiences.md)
   + [모범 사례](audiences/audiences-best-practices.md)
   + [구독 관리](start/subscriptions.md)
+ 콘텐츠 관리 {#content}
   + [랜딩 페이지 만들기](dev/landing-pages.md)
   + [웹 앱 및 양식 디자인](dev/webapps.md)
+ 자동화 및 워크플로 {#automation}
   + [Campaign Automation 안내서 >](https://experienceleague.adobe.com/ko/docs/campaign/automation/home)
+ 개인 정보 보호 및 보안 관리 {#privacy}
   + [개인 정보 보호 요청 관리](start/privacy.md)
   + [보안 지침](config/security.md)
   + [향상된 보안 추가 기능](config/enhanced-security.md)
+ 의사 결정 관리 {#offers}
   + [실시간 상호 작용 시작](interaction/interaction.md)
   + [환경 및 아키텍처](interaction/interaction-architecture.md)
   + [모범 사례](interaction/interaction-best-practices.md)
   + 설정 정의{#interaction-settings}
      + [운영자 만들기](interaction/interaction-operators.md)
      + [환경 만들기](interaction/interaction-env.md)
      + [사전 정의 필터 만들기](interaction/interaction-predefined-filters.md)
      + [오퍼 공간 만들기](interaction/interaction-offer-spaces.md)
   + [오퍼 카탈로그 만들기](interaction/interaction-offer-catalog.md)
   + [오퍼 만들기](interaction/interaction-offer.md)
   + [오퍼 보내기(아웃바운드)](interaction/interaction-send-offers.md)
   + 오퍼(인바운드) 제공{#inbound}
      + [컨텍스트](interaction/interaction-present-offers.md)
      + [웹 페이지에서 오퍼 호출](interaction/interaction-integration.md)
      + [익명 상호 작용 관리](interaction/anonymous-interactions.md)
   + [보고서 및 기록](interaction/interaction-tracking.md)
   + [활용 사례](interaction/interaction-use-cases.md)
+ 보고 및 분석 {#analytics}
   + [추적 및 모니터링](start/tracking.md)
   + [감사 추적](reporting/audit-trail.md)
   + 보고서 작업{#reports}
      + [보고서 시작하기](reporting/gs-reporting.md)
      + 큐브 만들기{#cubes}
         + [큐브 시작](reporting/gs-cubes.md)
         + [큐브 만들기](reporting/cube-indicators.md)
         + [큐브를 사용하여 보고서 만들기](reporting/cube-tables.md)
         + [큐브 사용자 정의](reporting/customize-cubes.md)
      + 기본 제공 보고서{#ac-reports}
         + [기본 제공 보고서 목록](reporting/built-in-reports.md)
         + [전반적 보고서](reporting/global-reports.md)
         + [게재 보고서](reporting/delivery-reports.md)
         + [기본 제공 메트릭 계산](reporting/metrics-calculation.md)
      + [사용자 정의 보고서](reporting/custom-reports.md)
+ 데이터 관리 {#data}
   + [워크플로 시작](config/workflows.md)
   + [데이터 가져오기](start/import.md)
   + [워크플로 설명서](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=ko)
+ 통합 {#connect}
   + [캠페인을 다른 솔루션과 연결](connect/integration.md)
   + Campaign + Experience Platform {#ac-aep}
      + [대상자 및 프로필 속성 공유 및 동기화](connect/ac-aep.md)
      + [Campaign 랜딩 페이지에서 AEP 프로필 업데이트](connect/ac-aep-landing-pages.md)
   + [Campaign + Journey Optimizer](connect/ac-ajo.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign - Experience Cloud 트리거](connect/ac-triggers.md)
   + [Campaign + Workfront](connect/ac-workfront.md)
   + [Campaign + X(Twitter)](connect/ac-tw.md)
   + [Campaign + 외부 데이터베이스](connect/fda.md)
   + Campaign + CRM {#ac-crm}
      + [CRM 커넥터 시작](connect/crm.md)
      + [Campaign 및 SFDC 작업](connect/ac-sfdc.md)
      + [Campaign 및 Microsoft Dynamics 작업](connect/ac-ms-dyn.md)
      + [데이터 동기화](connect/crm-data-sync.md)
+ 관리 {#admin}
   + 사용자 및 권한 {#permissions}
      + [사용 권한 시작](start/gs-permissions.md)
      + [사용자 권한 관리](start/manage-permissions.md)
      + [폴더에 권한 추가](start/folder-permissions.md)
   + [컨트롤 패널](config/self-service.md)
+ 아키텍처 및 구성 {#config}
   + Campaign v8 아키텍처 {#architecture}
      + [글로벌 원칙](architecture/general-architecture.md)
      + [아키텍처 모델](architecture/architecture.md)
      + [Campaign FDA 배포](architecture/fda-deployment.md)
      + 엔터프라이즈(FFDA) 배포 {#ffda}
         + [Campaign FFDA란?](architecture/enterprise-deployment.md)
         + [키 관리 및 독자성](architecture/keys.md)
         + [새 API](architecture/new-apis.md)
         + [API 스테이징 메커니즘](architecture/staging.md)
         + [복제 메커니즘](architecture/replication.md)
   + 구현 {#implement}
      + [구현 단계](start/implement.md)
      + [인스턴스 사용자 정의](dev/customize.md)
      + [데이터 모델 모범 사례](dev/datamodel-best-practices.md)
   + 설정 및 구성 {#configuration}
      + [사용자 인터페이스 설정](config/ui-settings.md)
      + [폴더 및 보기 관리](audiences/folders-and-views.md)
      + [트랜잭션 메시지 설정](config/transactional-msg-settings.md)
      + [Campaign SDK와 앱 통합 - 더 이상 사용되지 않는 페이지](config/push-config.md)
      + [외부 계정](config/external-accounts.md)
+ 개발자 리소스 {#developer}
   + [Campaign 데이터 모델](dev/datamodel.md)
   + 스키마 및 양식 {#shemas-forms}
      + [스키마 작업](dev/schemas.md)
      + [스키마 만들기](dev/create-schema.md)
      + [스키마 확장](dev/extend-schema.md)
      + [스키마 필터링](dev/filter-schema.md)
      + [스키마 구조](dev/schema-structure.md)
      + [데이터베이스 매핑](dev/database-mapping.md)
      + [키 관리](dev/database-keys.md)
      + [링크 관리](dev/database-links.md)
      + [PI 보기 제한](dev/restrict-pi-view.md)
      + [사용자 정의 수신자 테이블 사용](dev/custom-recipient.md)
      + [데이터베이스 업데이트](dev/update-database-structure.md)
      + [입력 양식](dev/forms.md)
   + [데이터 패키지 작업](dev/packages.md)
   + [Campaign API](dev/api.md)
+ [Campaign 기술 노트 >](https://experienceleague.adobe.com/ko/docs/campaign/technotes-ac/technotes-home)
+ [Campaign 웹 사용자 인터페이스 설명서 >](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/campaign-web-home)

