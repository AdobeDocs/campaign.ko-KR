---
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 4a3e6cf15b1877e6eb4e13fdee056356eab267c5
workflow-type: tm+mt
source-wordcount: '1747'
ht-degree: 6%

---

# 최신 릴리스 {#latest-release}

이 페이지에는 Campaign v8(콘솔) **최신 릴리스**&#x200B;에 포함된 새로운 기능, 개선 사항 및 수정 사항이 나와 있습니다. Campaign 릴리스와 버전, 업그레이드에 대한 자세한 내용은 [이 페이지](upgrades.md)에서 알아보세요. 다른 릴리스는 이 설명서의 이전 릴리스 섹션에 나열되어 있습니다.

## 릴리스 8.9.2 {#release-8-9-2}

>[!CAUTION]
>
> 클라이언트 콘솔 업그레이드는 필수입니다. 이 [페이지](../start/connect.md#upgrade-ac-console)에서 클라이언트 콘솔을 업그레이드하는 방법을 알아보십시오.

_2026년 5월 3일_

### 보안 개선 사항 {#security-8-9-2}

* 최적의 보안, 안정성 및 규정 준수를 유지하기 위해 모든 인스턴스가 Debian 13 및 PostgreSQL 17로 업그레이드되었습니다.

### 해결 사항 {#fixes-8-9-2}

>[!NOTE]
>
> 아래 나열된 수정 사항은 연속적인 8.9.2 빌드에서 점진적으로 롤아웃되었습니다. **[!UICONTROL Help > About...]** [메뉴](upgrades.md#version)(으)로 이동하여 최신 8.9.2(11d1c68) 빌드가 있는지 확인합니다. 자세한 내용은 Adobe 담당자에게 문의하십시오.

* 데이터 유형 전환 문제로 인해 트랜잭션 이벤트의 이벤트 날짜가 잘못 설정되어 동적 보고에서 잘못된 날짜가 발생하는 문제를 해결했습니다. (NEO-93923)
* 제목 및 본문 필드가 비어 있는 경우 게재를 준비하는 동안 Android 및 iOS 자동 푸시 알림이 실패하는 문제를 해결했습니다. (NEO-93739)
* 잘못된 조정 키로 인해 Android 앱 등록 토큰에 대해 언어 필드가 캡처되지 않는 문제를 해결했습니다. (NEO-93100)
* 압력 규칙이 있는 사용자 지정 유형화 규칙을 적용할 때 게재 준비가 실패하는 문제를 해결했습니다. (NEO-94457)
* 클라이언트 콘솔에서 HTTP 요청 처리 오류가 발생하는 문제를 해결했습니다. (NEO-94071)

<!-- BUILD 8.9.2.9829.9669833 -->

* 이제 연결 로그 삽입 오류를 방지하기 위해 FDA 모니터링이 기본적으로 비활성화됩니다. (NEO-94841)
* 오퍼 상환에 사용된 상호 작용 SOAP 호출이 네임스페이스 해결 오류와 함께 실패할 수 있는 문제를 해결했습니다. (NEO-94787)
<!-- infra * Fixed an issue where Snowflake connections using private key authentication could fail on ARM64 architectures. (NEO-94350) -->
* 길이가 1인 문자열 필드로 인해 PostgreSQL 17의 워크플로우 임시 테이블에서 SQL 오류가 발생할 수 있는 문제를 해결했습니다. (NEO-94487)
<!-- linked to previous build * Fixed an issue where the server could fail to restart after a Debian 13 build upgrade due to a missing dependency. (NEO-94598) -->

<!-- BUILD 8.9.2.9829.c90aa36 -->

* 클라이언트 콘솔 및 웹 UI의 **미러 페이지 표시** 옵션이 &quot;잘못된 미러 페이지&quot; 오류를 반환할 수 있는 문제를 해결했습니다. (NEO-93303)

<!-- BUILD 8.9.2.9830.4a6f868 -->

* FFDA 배포에서 다중 변형 패키지를 설치한 후 기본 **추적** 기술 워크플로우가 실패할 수 있는 문제를 해결했습니다. (NEO-94972)
* 게재 템플릿에서 현재 게재를 참조하는 가중치 공식을 사용한 경우 게재 준비가 대상에 수신자를 추가하지 못하는 문제를 수정했습니다. (NEO-94892)
<!-- hotfix -->
* 업그레이드 후 2개의 연속된 1-N 링크에서 조인을 사용하는 워크플로우 보강이 SQL 오류로 인해 실패할 수 있는 문제를 해결했습니다. (NEO-94893)

<!-- BUILD 8.9.2.9831.f53d3d2 -->

* 시간이 지남에 따라 과도한 메모리 소모가 발생할 수 있는 이메일 파이프라인의 문제를 해결했습니다. (NEO-95088)
* 시드 또는 증명 주소가 사용된 경우 충돌하는 이메일 유형화 규칙이 중복되지 않은 수신자를 게재 대상에서 잘못 제외할 수 있는 문제를 해결했습니다. (NEO-95026)
* 업그레이드 후 기본 제공 **오퍼 알림** 기술 워크플로우가 실패할 수 있는 문제를 해결했습니다. (NEO-95064)
* 빌드 업그레이드 중 추적 워크플로우 오류를 방지하기 위해 다변형 패키지 설치 프로세스가 개선되었습니다. (NEO-95018)

<!-- BUILD 8.9.2.9831.11d1c68 -->

* 서버가 반복적으로 충돌하여 인스턴스가 중단되는 문제를 해결했습니다. (NEO-95304)
* 추적 및 미러 페이지 링크가 게재를 로드하지 못하는 문제를 해결했습니다. (NEO-95239)
* IMS Single Sign-On으로 보호되는 Campaign 웹 애플리케이션에 로그인할 때 리디렉션 루프가 발생할 수 있는 문제를 해결했습니다. (NEO-95188)
* 게재를 저장한 후 게재 추출 파일에서 게재 생성 날짜가 누락되는 문제를 해결했습니다. (NEO-95010)
* 대량으로 생성된 하위 워크플로우가 **편집 중** 상태로 유지되어 트랜잭션 워크플로우 용량이 감소할 수 있는 문제를 해결했습니다. (NEO-95131)
* **목록 읽기** 활동이 미리 정의된 목록 템플릿을 워크플로우가 생성한 목록 구조로 덮어써서 다운스트림 워크플로우에서 오류가 발생하는 문제를 해결했습니다. (NEO-95103)
* 대량 게재를 처리할 때 푸시 알림 피드백 처리로 인해 서버가 충돌하는 문제를 해결했습니다. (NEO-95150)
* 스키마 탐색기에서 `xtk:workflow` 스키마에서 **데이터** 탭을 열면 오류 메시지가 트리거되는 문제가 해결되었습니다. (NEO-94923)
<!-- hotfixes -->
* **데이터 보강** 활동이 더 이상 업스트림 **하위 워크플로우** 활동에서 출력 특성을 검색할 수 없어 워크플로우가 실패하는 문제를 해결했습니다. (NEO-95151)
* 게재 상태 업데이트를 방지하고 다운스트림 메시지 처리를 차단할 수 있는 추적 데이터 수집 문제를 해결했습니다. (NEO-94666)
* 오퍼 제안과 관련된 특정 클라이언트 콘솔 작업이 Snowflake 데이터베이스에서 장기 실행 쿼리를 트리거하여 잠금 및 지연을 일으킬 수 있는 문제를 해결했습니다. (NEO-92936)
* Snowflake 외부 계정에 암호화된 키를 저장하기 위한 사용자 지정 옵션을 구성할 수 없는 문제를 해결했습니다. (NEO-93302)

<!-- 
Internal/non-customer-facing:
* Internal test automation task added to cover NEO-94893. (NEO-94990) — autotest only
Customer-specific hotfixes:
* Fixed an issue affecting WhatsApp delivery preparation. (NEO-92480) — HeroMotoCorp only
* Added a feature-flagged optimization to use dynamic shared memory in Customer Targeting Audience (CTA) processing. (NEO-93542) — DerTour only
* Fixed an issue where the delivery alerting workflow could fire incorrect "long start pending" notifications even when deliveries were sent within the configured threshold. (NEO-93434) — non-ZDT hotfix, NORC only
* Added a new parameter in the mobile SDK to allow identification of the source instance for push notifications. (NEO-94650) — ICICI only
* Fixed an issue with the custom send time feature on the Web UI where deliveries waited until the contact date and time to execute instead of executing at the equivalent local time per recipient timezone, breaking parity with Campaign Standard behavior. (NEO-94762) — H&M only (in progress at time of writing)
-->

## 릴리스 8.9.1 {#release-8-9-1}

_2026년 1월 27일_

>[!CAUTION]
>
> 클라이언트 콘솔 업그레이드는 필수입니다. 이 [페이지](../start/connect.md#upgrade-ac-console)에서 클라이언트 콘솔을 업그레이드하는 방법을 알아보십시오.

### 새로운 기능 {#new-8-9-1}

**새 SMS 전송 커넥터**&#x200B;를 이제 모든 고객(GA)이 사용할 수 있습니다. [자세한 설명서](../send/sms/sms.md)를 참조하세요.

이 릴리스에는 Campaign 웹 사용자 인터페이스에서 사용할 수 있는 기능 집합이 포함되어 있습니다.

* [다국어 게재 기능(GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html?lang=ko){target="_blank"}
* [트랜잭션 메시지(GA)의 프로필 보강](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html?lang=ko){target="_blank"}
* [Adobe Experience Manager 라이브 및 언어 사본](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html?lang=ko){target="_blank"}
* [콘텐츠 실험 - A/B 테스트](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html?lang=ko){target="_blank"}
* [연속 게재 활동](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html?lang=ko){target="_blank"}
* [캠페인 승인 관리](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html?lang=ko){target="_blank"}

Campaign 웹 UI [릴리스 노트](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=ko){target="_blank"}를 참조하세요.

### 보안 개선 사항 {#security-8-9-1}

* 이제 Snowflake 외부 계정이 OAuth2 인증을 지원하므로 페더레이션 데이터 액세스 연결에 대한 현대적이고 안전한 인증 방법이 제공됩니다. (NEO-87013) [자세한 내용](../config/external-accounts.md#snowflake-external-accounts)
* 이제 데이터 블록 외부 계정은 서비스 주체(비대화형 클라이언트 자격 증명 흐름)를 통한 OAuth2 인증을 지원하므로 페더레이션 데이터 액세스 연결에 대한 보안 인증 방법이 제공됩니다. 대화형 OAuth2 인증은 향후 릴리스에서 사용할 수 있습니다. (NEO-87422) [자세한 내용](../config/external-accounts.md#databricks-external-accounts)
* 승인된 디렉터리로 작업을 제한하고 무단 액세스와 잠재적인 원격 코드 실행을 방지하여 워크플로우 파일 액세스 취약성을 해결했습니다. (NEO-88460)
* 워크플로우 JavaScript 코드 활동에 FTP URL 허용 목록에 추가 컨트롤을 추가하여 승인된 주소로만 아웃바운드 FTP 연결을 제한했습니다. (NEO-89083)

### 기타 변경 사항 {#changes-8-9-1}

* 지능적인 워크플로우 재시작 기능과 중요하지 않은 프로세스를 위한 메모리 보호 기능을 사용하여 메모리 사용량이 많은 상태에서 자동 워크플로우 조정을 구현하여 컨테이너 메모리 관리를 개선했습니다. (NEO-89041)
* Campaign 워크플로우에서 비대칭 암호화 및 암호 해독 기능에 대한 지원을 추가했습니다. (NEO-80257)
* FFDA 배포에서 대용량 데이터 업로드를 위한 복제 에이전트 성능 및 메모리 복원력을 개선했습니다. (NEO-88430)
* Campaign에서 사용자 지정 SQL을 실행할 때 PostgreSQL 데이터베이스를 더 잘 보호하고 워크플로우가 원활하게 실행되도록 **[!UICONTROL SQL code]** 및 **[!UICONTROL SQL Data Management]** 워크플로우 활동을 개선했습니다. 자세한 내용과 모범 사례는 [SQL 데이터 관리](../../automation/workflow/sql-data-management.md#important-notes) 및 [SQL 코드](../../automation/workflow/sql-code-and-javascript-code.md#important-notes)를 참조하세요. (NEO-86540)


### 수정 사항 {#fixes-8-9-1}

* sysFilter 변경 후 데이터베이스 구조를 업데이트할 수 없는 문제가 해결되었습니다. (NEO-93306)
* 마이그레이션 후 동적 보고서 데이터가 누락되는 문제를 해결했습니다. (NEO-92962)
* 게재 상태가 올바르게 업데이트되지 않는 문제를 해결했습니다. (NEO-92908)
* Databricks FDA Use Catalog 제한과 관련된 문제를 수정했습니다. (NEO-92900)
* Outlook Windows 바탕 화면에서 HTML 레이아웃 오류가 발생할 수 있는 문제를 해결했습니다. (NEO-92611)
* 업그레이드 후 게재 기본 키가 중간 인스턴스에서 복제되는 데이터 무결성 문제를 해결했습니다. (NEO-92424)
* 게재의 추적 및 이미지 대화 상자에서 링크를 비활성화할 수 없는 문제를 해결했습니다. (NEO-92381)
* nms.subscription.RecipientSubscribe() 함수가 일괄 구독에 대해 작동하지 않던 문제를 수정했습니다. (NEO-92308)
* 업그레이드 후 게재 부분이 누락되어 게재 실패가 발생하는 문제를 해결했습니다. (NEO-92278)
* 중복 상태 오류 및 SQL 구문 오류로 인해 추적 표시기가 업데이트되지 않는 추적 워크플로우의 문제를 해결했습니다. (NEO-92239)
* dbEnum 필드를 사용할 때 워크플로우를 통해 만든 목록에서 열거 필드 레이블이 누락되거나 잘못 표시되는 문제를 해결했습니다. (NEO-91158)
* RT 게시/게시 취소 대화 상자가 닫히지 않고 정지되지 않던 문제를 수정했습니다. (NEO-91038)
* &quot;서비스 공급자가 고려함&quot; 상태의 수신자에 대해 발생하는 문제를 해결했습니다. (NEO-90927)
* 옵트아웃 링크에 대한 (구독 취소) 원본 이 누락되는 문제를 수정했습니다. (NEO-90714)
* 쿠폰을 추가하면 게재를 준비하지 못하는 문제가 해결되었습니다. (NEO-90547)
* [거부 카운트 삽입]이 [감사] 탭에 정확하게 반영되지 않던 문제를 수정했습니다. (NEO-90318)
* 애플리케이션 서비스 거부를 초래할 수 있는 보안 문제를 해결했습니다. (NEO-89984)
* 다운로드한 Hotclick 보고서의 PDF이 손상되는 문제를 해결했습니다. (NEO-89954)
* 업그레이드 후 발생한 SSL 오류를 해결했습니다. 오류를 읽는 동안 예기치 않은 EOF가 발생했습니다. (NEO-89108)
* 업그레이드 후 데이터 스키마에서 데이터를 쿼리할 수 없는 문제를 해결했습니다. (NEO-88663)
* PostgreSQL 15에서 &quot;char&quot; 필드를 연결할 때 발생하는 오류를 수정했습니다. (NEO-88028)
* 템플릿을 저장하거나 복제할 때 게재 템플릿 변수의 순서가 변경되던 문제를 수정했습니다. (NEO-87845)
* 새 데이터 라이브러리 스키마를 만들면 웹 인터페이스가 충돌하는 문제가 해결되었습니다. (NEO-87816)
* 에서 중복 제거 활동의 보조 세트를 사용하는 문제가 해결되었습니다. (NEO-87711)
* X11 종속성 없이 설치 패키지에 대한 요청을 수정했습니다. (NEO-87471)
* 세그먼트 코드를 동적 보고서에 사용할 수 없던 문제를 수정했습니다. (NEO-87276)
* 데이터 업데이트 활동에서 워크플로우가 중단되는 문제를 해결했습니다. (NEO-87252)
* BigQuery에서 잘못된 시간대를 사용하는 문제가 수정되었습니다. (NEO-86622)
* &#39;mcSynch_mcExec1/jsReplicateUrl&#39; 스크립트를 평가하는 동안 발생한 JavaScript 오류를 해결했습니다. (NEO-86553)
* 잘못된 식별자 계산 방법으로 인해 eventHisto 테이블에 중복 이벤트가 발생하는 문제가 해결되었습니다. (NEO-86544)
* 복사 시 iOS 푸시에 대한 고급 탭이 표시되지 않는 문제를 해결했습니다. (NEO-86231)
* 참조 테이블 복제 워크플로우가 nms:delivery 스키마를 복제하지 못하는 문제를 해결했습니다. (NEO-85884)
* 게재를 보내는 동안 MXIP 주소에 해당하는 null 도메인 오류가 오류 로그에 표시되는 문제를 수정했습니다. (NEO-85238)
* 옵션을 변경한 후 기술 게재 템플릿이 새로 고쳐지지 않는 문제를 해결했습니다. (NEO-84149)
* 기본 청구 워크플로우의 오류를 수정했습니다. (NEO-83624)
* 타겟팅된 레코드의 기본 키만 기반으로 하여 중복을 제외하는 문제가 해결되었습니다. (NEO-82910)
* 추적 통계가 콘솔과 비교하여 다른 값을 표시하는 Campaign 웹 UI 보고서의 불일치를 수정했습니다. (NEO-82339)
* 데이터 업데이트 활동에서 레코드를 업데이트하지 않아도 마지막 수정 날짜가 변경되는 문제를 수정했습니다. (NEO-82002)
* 목록에 새 속성을 추가하면 목록을 읽는 워크플로우가 실패하는 문제가 해결되었습니다. (NEO-80258)
* 추적 표시기 보고서에 개별 열림에 대한 잘못된 값이 표시되던 문제를 수정했습니다. (NEO-79466)