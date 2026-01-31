---
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 6693bb8a62c0d126b871dc24a75b76de71b86f8d
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 21%

---

# 최신 릴리스 {#latest-release}

이 페이지에는 Campaign v8(콘솔) **최신 릴리스**&#x200B;에 포함된 새로운 기능, 개선 사항 및 수정 사항이 나와 있습니다. Campaign 릴리스와 버전, 업그레이드에 대한 자세한 내용은 [이 페이지](upgrades.md)에서 알아보세요. 다른 릴리스는 이 설명서의 이전 릴리스 섹션에 나열되어 있습니다.

## 릴리스 8.9.1 {#release-8-9-1}

_2026년 1월 27일_

>[!CAUTION]
>
> 클라이언트 콘솔 업그레이드는 필수입니다. 이 [페이지](../start/connect.md#upgrade-ac-console)에서 클라이언트 콘솔을 업그레이드하는 방법을 알아보십시오.

### 새로운 기능 {#new-8-9-1}

**새 SMS 전송 커넥터**&#x200B;를 이제 모든 고객(GA)이 사용할 수 있습니다. [자세한 설명서](../send/sms/sms.md)를 참조하세요.

이 릴리스에는 Campaign 웹 사용자 인터페이스에서 사용할 수 있는 기능 집합이 포함되어 있습니다.

* [GA(다국어 게재 기능)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html?lang=ko){target="_blank"}
* [트랜잭션 메시지(GA)의 프로필 보강](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html?lang=ko){target="_blank"}
* [Adobe Experience Manager 라이브 및 언어 사본](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html?lang=ko){target="_blank"}
* [콘텐츠 실험 - A/B 테스트](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html?lang=ko)
* [연속 게재 활동](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html?lang=ko)
* [캠페인 승인 관리](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html?lang=ko)

Campaign 웹 UI [릴리스 노트](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=ko){target="_blank"}를 참조하세요.

### 보안 개선 사항 {#security-8-9-1}

* 이제 Snowflake 외부 계정이 OAuth2 인증을 지원하므로 페더레이션 데이터 액세스 연결에 대한 현대적이고 안전한 인증 방법이 제공됩니다. (NEO-87013)
* 승인된 디렉터리로 작업을 제한하고 무단 액세스와 잠재적인 원격 코드 실행을 방지하여 워크플로우 파일 액세스 취약성을 해결했습니다. (NEO-88460)
* 워크플로우 JavaScript 코드 활동에 FTP URL 허용 목록에 추가 컨트롤을 추가하여 승인된 주소로만 아웃바운드 FTP 연결을 제한했습니다. (NEO-89083)

### 기타 변경 사항 {#changes-8-9-1}

* 지능적인 워크플로우 재시작 기능과 중요하지 않은 프로세스를 위한 메모리 보호 기능을 사용하여 메모리 사용량이 많은 상태에서 자동 워크플로우 조정을 구현하여 컨테이너 메모리 관리를 개선했습니다. (NEO-89041)
* Campaign 워크플로우에서 비대칭 암호화 및 암호 해독 기능에 대한 지원을 추가했습니다. (NEO-80257)
* FFDA 배포에서 대용량 데이터 업로드를 위한 복제 에이전트 성능 및 메모리 복원력을 개선했습니다. (NEO-88430)


### 수정 사항 {#fixes-8-9-1}

* 특정 열로 그룹화할 때 동적 보고서에 잘못된 카운트가 표시되는 문제를 수정했습니다. (NEO-86898)
* 동적 보고서와 실제 캠페인 데이터 간의 데이터 불일치가 해결되었습니다. (NEO-88068)
* 쿼리에 예기치 않은 결과를 발생시키는 PostgreSQL &quot;char&quot; 필드 유형의 연결 문제를 해결했습니다. (NEO-87769)
* JavaScript logInfo 명령이 특정 매개 변수를 제대로 처리하지 못하는 문제가 해결되었습니다. (NEO-88263)
* 메시지 센터 실시간 이벤트 처리에서 동기화 중단 문제가 해결되었습니다. (NEO-88330)
* 비주얼 편집기에서 자동으로 HTML 콘텐츠 형식이 변경되어 레이아웃이 변경되는 문제가 해결되었습니다. (NEO-88409)
* 중복 제거 활동이 임시 스키마에서 제대로 작동하지 않는 문제를 해결했습니다. (NEO-88577)
* 증명을 보낼 때 시드 주소가 생성되지 않던 문제를 수정했습니다. (NEO-88720)
* 파티션 열 처리를 최적화하여 PostgreSQL 쿼리 성능이 개선되었습니다. (NEO-88771)
* 파일 전송 활동에서 줄 연속 문자를 제대로 처리하지 못하는 문제가 해결되었습니다. (NEO-88812)
* 대규모 데이터 세트에서 더 나은 성능을 위해 PostgreSQL 쿼리 최적화를 개선했습니다. (NEO-88885)
* 하이브리드 캠페인이 열리지 않도록 하는 &quot;권한 거부&quot; 오류를 수정했습니다. (NEO-88955)
* 더 긴 텍스트 문자열을 처리하기 위해 바코드 기능 지원을 확장했습니다. (NEO-88958)
* 반복 게재에서 증명을 사용할 때 발생한 캠페인 로그 오류를 수정했습니다. (NEO-88976)
* 특정 시나리오에서 이메일 전송 작업에 영향을 주는 문제를 해결했습니다. (NEO-89019)
* 워크플로우 시작 모드가 즉시 (으)로 예기치 않게 변경되는 문제를 해결했습니다. (NEO-89025)
* 특정 조건에서 데이터 업데이트 활동을 실행할 때 발생한 오류를 수정했습니다. (NEO-89031)
* 데이터 업데이트 활동이 사용자 지정 스키마 메타데이터를 잃는 문제를 해결했습니다. (NEO-89056)
* 게재를 준비하는 동안 발생한 유효성 검사 오류를 수정했습니다. (NEO-89063)
* 쿼리에 1-1 링크 관계에 대한 필터가 포함된 경우 잘못된 SQL 생성이 해결되었습니다. (NEO-89065)
* 증분 쿼리 활동이 구성된 크기 제한을 준수하지 않던 문제를 수정했습니다. (NEO-89066)
* 대규모 작업을 위한 FFDA 배포의 워크플로우 성능이 개선되었습니다. (NEO-89098)
* 워크플로우 프로세스를 위한 메모리 관리 및 안정성을 개선했습니다. (NEO-89105)
* 데이터 불일치를 방지하기 위해 웹 양식에 대해 엄격한 열 유효성 검사를 활성화했습니다. (NEO-89111)
* 처리 지연을 초래한 메시지 센터 동기화 문제가 해결되었습니다. (NEO-89138)
* &quot;게재 능력을 위해 새로 고침&quot; 워크플로우에서 제대로 실행되지 않는 오류를 해결했습니다. (NEO-89160)
* 워크플로우에서 JavaScript 코드 활동을 실행할 때 발생하는 오류를 수정했습니다. (NEO-89169)
* 적절한 외부 계정 설정을 허용하도록 하드코딩된 Snowflake 웨어하우스 구성이 제거되었습니다. (NEO-89201)
* 워크플로우 파일 전송 작업 중 발생한 403 금지된 오류를 수정했습니다. (NEO-89226)
* FFDA 배포의 수신자 테이블에서 느린 쿼리를 최적화했습니다. (NEO-89268)
* 증분 쿼리 활동이 구성된 일정을 무시하는 문제를 해결했습니다. (NEO-89317)
* 하이브리드 환경에서 캠페인을 열 때 발생하는 액세스 오류를 해결했습니다. (NEO-89320)
