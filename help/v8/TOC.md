---
audience: end-user
user-guide-title: Campaign v8
description: Campaign v8 설명서
breadcrumb-title: Campaign v8
title: Campaign v8 문서
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 94%

---


# Adobe Campaign v8 설명서 {#campaign-v8}

+ [Campaign v8 설명서](campaign-home.md)
+ 새로운 기능 {#new}
   + [주요 기능](start/whats-new.md)
   + [릴리스 정보](start/release-notes.md)
   + [알려진 제한 사항](start/known-limitations.md)
   + [Classic v7에서 v8로](start/capability-matrix.md)
+ 시작 {#start}
   + [시작](start/get-started.md)
   + [구성 요소 및 프로세스](start/ac-components.md)
   + Campaign UI {#ac-ui}
      + [Campaign 인터페이스 살펴보기](start/campaign-ui.md)
      + [Campaign 인터페이스 사용자 정의](start/customize-ui.md)
   + [대상자를 사용한 작업](start/audiences.md)
   + [데이터 가져오기](start/import.md)
   + [캠페인 만들기](start/campaigns.md)
   + [메시지 보내기](start/create-message.md)
   + [구독 관리](start/subscriptions.md)
   + [추적 및 모니터링](start/tracking.md)
   + [지표 및 보고서](start/reporting.md)
   + [FAQ](start/campaign-faq.md)
+ 구현 {#implement}
   + [구현 단계](start/implement.md)
   + [인스턴스 사용자 정의](dev/customize.md)
   + [보안 지침](config/security.md)
   + [웹 앱 및 양식 디자인](dev/webapps.md)
   + [데이터 모델 모범 사례](dev/datamodel-best-practices.md)
+ 배포 {#deploy}
   + [호환성 매트릭스](start/compatibility-matrix.md)
   + [Campaign에 연결](start/connect.md)
   + [사용 권한](start/permissions.md)
   + [Campaign 컨트롤 패널](config/self-service.md)
+ 프로필 및 대상자 {#profiles-and-audiences}
   + [시작](audiences/gs-audiences.md)
   + [프로필 액세스](audiences/view-profiles.md)
   + 프로필 추가 {#add-profiles}
      + [수동으로 프로필 만들기](audiences/create-profiles.md)
      + [파일에서 프로필 가져오기](audiences/import-profiles.md)
      + [외부 프로필 작업](audiences/external-profiles.md)
      + [웹 양식에서 프로필 데이터 수집](audiences/collect-profiles.md)
   + 대상자 만들기 {#create-audiences}
      + [연락처 목록 만들기](audiences/create-audiences.md)
      + [필터 만들기 및 관리](audiences/create-filters.md)
   + [폴더 및 보기 관리](audiences/folders-and-views.md)
   + [모범 사례](audiences/audiences-best-practices.md)
+ 메시지 보내기{#send}
   + [이메일](send/email.md)
   + [SMS](send/sms.md)
   + [푸시 알림](send/push.md)
   + [LINE 메시지 보내기](send/line.md)
   + [DM](send/direct-mail.md)
   + [소셜 마케팅](send/twitter.md)
   + [트랜잭션 메시지 ](send/transactional.md)
   + 실패, 바운스, 격리{#failures}
      + [격리](send/quarantines.md)
      + [게재 실패](send/delivery-failures.md)
+ 실시간 상호 작용{#interaction}
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
   + [오퍼 보내기 (아웃바운드)](interaction/interaction-send-offers.md)
   + 오퍼(인바운드) 제공{#inbound}
      + [컨텍스트](interaction/interaction-present-offers.md)
      + [웹 페이지에서 오퍼 호출](interaction/interaction-integration.md)
      + [익명 상호 작용 관리](interaction/anonymous-interactions.md)
   + [보고서 및 기록](interaction/interaction-tracking.md)
   + [활용 사례](interaction/interaction-use-cases.md)
+ 구성 {#config}
   + [워크플로우 자동화](config/workflows.md)
   + [데이터 관리](config/replication.md)
   + [이메일 설정](config/email-settings.md)
   + [트랜잭션 메시지 설정](config/transactional-msg-settings.md)
   + [Campaign SDK와 앱 통합](config/push-config.md)
   + [외부 계정](config/external-accounts.md)
+ 연결 {#connect}
   + [다른 솔루션과 연결](connect/integration.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign - Experience Cloud 트리거](connect/ac-triggers.md)
   + [Campaign + RTCDP](connect/ac-rtcdp.md)
   + [Campaign + Twitter](connect/ac-tw.md)
   + [Campaign + 외부 데이터베이스](connect/fda.md)
   + Campaign + CRM {#ac-crm}
      + [CRM 커넥터 시작](connect/crm.md)
      + [Campaign을 SFDC와 함께 사용하기](connect/ac-sfdc.md)
      + [Campaign을 Microsoft Dynamics와 함께 사용하기](connect/ac-ms-dyn.md)
      + [데이터 동기화](connect/crm-data-sync.md)
+ 개발자 리소스 {#architecture}
   + [글로벌 원칙](dev/general-architecture.md)
   + [아키텍처](dev/architecture.md)
   + [데이터 모델](dev/datamodel.md)
   + 스키마 및 양식 {#shemas-forms}
      + [스키마 작업](dev/schemas.md)
      + [키 관리 및 독자성](dev/keys.md)
      + [스키마 만들기](dev/create-schema.md)
      + [스키마 확장](dev/extend-schema.md)
      + [스키마 필터링](dev/filter-schema.md)
      + [스키마 구조](dev/schema-structure.md)
      + [데이터베이스 매핑](dev/database-mapping.md)
      + [PI 보기 제한](dev/restrict-pi-view.md)
      + [사용자 정의 수신자 테이블 사용](dev/custom-recipient.md)
      + [데이터베이스 업데이트](dev/update-database-structure.md)
      + [입력 양식](dev/forms.md)
   + API {#api}
      + [시작](dev/api.md)
      + [새 API](dev/new-apis.md)
      + [API 스테이징 메커니즘](dev/staging.md)
+ [Campaign 컨트롤 패널](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ko)
