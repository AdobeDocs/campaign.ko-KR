---
source-git-commit: 548b4be24e26a6970f953f92af1f89d829689592
workflow-type: tm+mt
source-wordcount: '1522'
ht-degree: 0%

---
# AC-UI-26-01 설명서 분석

## 다음 릴리스 컨텐츠

이 문서는 AC-UI-26-01 및 AC-UI-25-11 월별 릴리스에 대한 제품 JIRA를 분석하여 문서 작업을 계획합니다.

### JIRA 필터

1. **[AC-UI-26-01-월별 스토리](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-26-01-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - 기본 릴리스 스토리
2. **[NEO 92400 개선 사항](https://jira.corp.adobe.com/issues/?jql=issueFunction%20in%20linkedIssuesOf(%27key%3DNEO-92400%27%2C%20%27is%20implemented%20by%27))** - 릴리스 개선 사항과 연결된 문제
3. **[AC-UI-25-11-월별 스토리](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - 이전 릴리스 이월
4. **[8.8.2](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20fixVersion%20!%3D%208.8.2%20and%20type%20%3D%20story%20order%20by%20status)**&#x200B;을(를) 제외한 AC-UI-25-11 - 필터링된 이전 릴리스

---

## 🟢 DOCAC 만들기

### [NEO-91565](https://jira.corp.adobe.com/browse/NEO-91565) - 개인화 필드에 대한 지원 추가(고급 AEM 통합)
**상태:** 해결됨\
**문서 필요:** 예\
**기존 DOCAC:** 없음\
**작업:** DOCAC 만들기

**범위:**
- 고급 AEM 통합에서 개인화 필드에 대한 문서 지원
- UI 워크플로 및 구성 단계
- AEM 다국어 통합 기능

**기능 설명:**
고급 AEM 통합을 사용하여 게재에서 개인화 필드를 추가할 수 있도록 지원하므로, Campaign 데이터에서 AEM 작성 이메일 템플릿으로 동적 콘텐츠를 삽입할 수 있습니다.

**컨텍스트:** ACS-ACC 패리티, MSFT별 요구 사항

**참조:** [AEM 다국어 위키](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=2988189953)

---

### [NEO-93487](https://jira.corp.adobe.com/browse/NEO-93487) - 게재 예약 계산 프로세스(ACS 패리티)
**상태:** 신규\
**문서 필요:** 예\
**기존 DOCAC:** 없음\
**작업:** DOCAC 만들기

**범위:**
- 푸시 알림에 대한 문서 게재 예약 계산 프로세스
- 시간대 기반 예약 공식
- 다중 시간대 타깃팅을 위한 파일 업로드

**기능 설명:**
수신자 시간대를 기반으로 계산된 전송 시간으로 OOTB 파일 기반 게재 일정을 활성화하여 지역별 전송 시간이 최적화된 여러 시간대에 단일 게재 타깃팅을 사용할 수 있습니다.

**컨텍스트:** 고객 기반(H&amp;M), ACS-ACC 패리티 요구 사항

**참조:** [ACS 설명서](https://experienceleague.adobe.com/en/docs/campaign-standard/using/testing-and-sending/scheduling-messages/computing-the-sending-date)

---

## 🔄 DOCAC 업데이트

### [NEO-80973](https://jira.corp.adobe.com/browse/NEO-80973) - 모든 웹 UI 사용자에 대한 동적 보고 사용 가능
**상태:** 진행 중\
**문서 필요:** 예\
**기존 DOCAC:** [DOCAC-11070](https://jira.corp.adobe.com/browse/DOCAC-11070)&#x200B;(닫힘), [DOCAC-13432](https://jira.corp.adobe.com/browse/DOCAC-13432)&#x200B;(해결됨)\
**작업:** DOCAC 검토

**범위:**
- 가용성 정보 업데이트(이제 8.7이 아닌 모든 웹 UI 사용자)
- 문서 언어 제한 사항
- 이전 보고와 충돌 지표 표시 명확하게 하기

**기능 설명:**
이제 모든 Campaign Web UI 사용자(이전에는 ACC 고객에게 8.7 ACS로 제한됨)에 대해 동적 보고를 사용할 수 있으며, ACS 스타일 인터페이스와 함께 고급 분석 및 사용자 지정 보고 기능을 제공합니다.

**컨텍스트:** 기능 확장, 백엔드 빌드 종속성(8.8.1)

**참조:** [Wiki - 보고서 비교](https://wiki.corp.adobe.com/display/~kumarvishal/Reports+-+Client+console+vs+WebUI)

---

### [NEO-86754](https://jira.corp.adobe.com/browse/NEO-86754) - A/B 테스트
**상태:** 진행 중\
**문서 필요:** 예\
**기존 DOCAC:** [DOCAC-13104](https://jira.corp.adobe.com/browse/DOCAC-13104)&#x200B;(신규)\
**작업:** DOCAC 업데이트

**범위:**
- 전체 A/B 테스트 워크플로우 설명서
- 콘텐츠 실험 설정 및 변형 구성
- 샘플 비율 정의 및 승자 선택 기준
- 통계 수집 및 평가

**기능 설명:**
이메일 게재에 대한 콘텐츠 실험 및 A/B 테스트를 통해 마케터는 다양한 콘텐츠 변형을 테스트하고, 샘플 크기를 정의하고, 성능 통계를 수집하며, 가장 성과가 좋은 변형을 나머지 수신자에게 자동으로 전송할 수 있습니다.

**컨텍스트:** Europa 프로젝트, Microsoft 요구 사항, 기능 플래그 사용

**참조:** [위키](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=3017705719), [그림 목마](https://www.figma.com/design/4EfXEaA6OIV0D8rauuXSWX/A-B-Testing)

---

### [NEO-76126](https://jira.corp.adobe.com/browse/NEO-76126) - 스키마 작성(새 테이블 만들기, 스키마 확장, 외부 DB 액세스)
**상태:** 진행 중\
**문서 필요:** 예\
**기존 DOCAC:** [DOCAC-13826](https://jira.corp.adobe.com/browse/DOCAC-13826)&#x200B;(신규)\
**작업:** DOCAC 업데이트

**범위:**
- 문서 스키마 작성 워크플로(3개 옵션: 테이블 만들기, 스키마 확장, 외부 DB 액세스)만
- 사용자 지정 엔터티에 대한 양식 정의
- 사용자 정의 스키마에서 탐색 및 CRUD 작업
- 2단계 및 3단계 기능

**기능 설명:**
관리자가 새 데이터베이스 테이블을 만들고, 사용자 지정 필드로 기존 스키마를 확장하고, 외부 데이터베이스에 연결할 수 있는 Web UI의 스키마 작성 기능이 있습니다. 이는 데이터 모델 사용자 지정에 필수적입니다.

**컨텍스트:** Microsoft 요구 사항, Europa 프로젝트, 단계별 게재(2단계 활성, 3단계 2월 말)

**참조:** [PRD](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=AC+Web+UI+-+Schemas+PRD), [그림](https://www.figma.com/design/lZkJso2HvXPbNjG0TmQTrC/Schemas)

---

### [NEO-92668](https://jira.corp.adobe.com/browse/NEO-92668) - 웹 분석
**상태:** 신규\
**문서 필요:** 예\
**기존 DOCAC:** 없음\
**작업:** DOCAC 만들기

**범위:**
- 웹 분석 외부 계정 구성
- 통합 설정 및 인증
- 캠페인의 Analytics 데이터 사용

**기능 설명:**
웹 분석 통합을 통해 웹 분석 플랫폼에 연결하여 캠페인 성과 및 웹 사이트 방문자 행동을 추적하고 보고할 수 있습니다.

**컨텍스트:** 고객 요청(P2E-RSC), 환경 가용성 보류 중

**참조:** 제공된 항목 없음

---

### [NEO-86753](https://jira.corp.adobe.com/browse/NEO-86753) - 라이브 카피/언어 사본에 대한 AEM 통합
**상태:** 신규\
**문서 필요:** 예\
**기존 DOCAC:** [DOCAC-13829](https://jira.corp.adobe.com/browse/DOCAC-13829)&#x200B;(해결됨)\
**작업:** DOCAC 검토

**범위:**
- AEM 게재 템플릿 찾아보기
- 한 번의 클릭으로 라이브 카피 및 언어 사본 만들기
- 다국어 콘텐츠 변형 만들기 워크플로

**기능 설명:**
AEM 통합 간소화를 통해 AEM 게재 템플릿에서 라이브 카피 및 언어 사본을 한 번의 클릭으로 만들 수 있으므로 AEM 사용자를 위한 다국어 캠페인 생성을 단순화할 수 있습니다.

**컨텍스트:** Microsoft 요구 사항, 작업이 Himanshu 팀으로 전송됨

**참조:** [ACS 설명서](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-experience-manager/creating-multilingual-email-aem.html)

---

### [NEO-88838](https://jira.corp.adobe.com/browse/NEO-88838) - 콘텐츠 편집기: 조각에 테마 변수 사용
**상태:** 신규\
**문서 필요:** 예\
**기존 DOCAC:** [DOCAC-12941](https://jira.corp.adobe.com/browse/DOCAC-12941)&#x200B;(신규)\
**작업:** DOCAC 업데이트

**범위:**
- 이메일 디자이너의 테마 변수(Beta)
- 조각에서 테마 사용
- Acrite 기능 활성화

**기능 설명:**
콘텐츠 조각 내 테마 변수 사용을 지원하여 중앙 집중식 테마 관리를 통해 이메일 구성 요소 전반에 걸쳐 일관된 브랜딩 및 디자인 시스템 애플리케이션을 활성화합니다.

**컨텍스트:** 보류 중, 다시 방문할 Acrite 기능

**참조:** [ATU-5460](https://jira.corp.adobe.com/browse/ATU-5460)

---

## ➕ DOCAC 만들기(개선 사항)

### [NEO-92942](https://jira.corp.adobe.com/browse/NEO-92942) - 사전 정의된 필터 - 공유 옵션
**상태:** 해결됨\
**문서 필요:** 예\
**기존 DOCAC:** [DOCAC-13697](https://jira.corp.adobe.com/browse/DOCAC-13697)&#x200B;(코드 검토), [DOCAC-13522](https://jira.corp.adobe.com/browse/DOCAC-13522)&#x200B;(닫힘 - 도우미)\
**작업:** DOCAC 검토

**범위:**
- 사전 정의된 필터에 대한 공유 옵션
- 다른 연산자로 가시성 필터링(ACC와 브랜드 여정 동작 비교)
- 공유 필터의 사용자 관리

**기능 설명:**
이제 ACC(기본값) 및 Brand 여정(사용자별 필터링)에 대한 다양한 비헤이비어를 사용하여 사전 정의된 필터를 다른 연산자가 볼 수 있도록 &quot;공유&quot;로 표시할 수 있습니다.

**컨텍스트:** 규칙 빌더 개선 사항, 기능 플래그: enable-query-filter-shared

**NEO-88441**&#x200B;과(와) 관련된 [참조:](https://jira.corp.adobe.com/browse/NEO-88441)

---

### [NEO-91299](https://jira.corp.adobe.com/browse/NEO-91299) - 연속 게재 활동
**상태:** 닫힘\
**문서 필요:** 예\
**기존 DOCAC:** [DOCAC-13586](https://jira.corp.adobe.com/browse/DOCAC-13586)&#x200B;(신규), [DOCAC-13808](https://jira.corp.adobe.com/browse/DOCAC-13808)&#x200B;(닫힘 - 상황별 도움말)\
**작업:** DOCAC 업데이트

**범위:**
- 연속 게재 워크플로우 활동
- 게재 템플릿 선택기 구성
- 자동 아웃바운드 전환 생성
- 타깃팅 옵션(콘텐츠 액세스 권한 없음)

**기능 설명:**
워크플로우에 대한 연속 게재 활동을 사용하면 템플릿에서 반복적으로 게재를 실행할 수 있으므로 콘텐츠를 수정하지 않고 워크플로우 오케스트레이션에 대한 아웃바운드 전환을 자동으로 생성할 수 있습니다.

**컨텍스트:** 기능 플래그: enable-continuous-delivery

**참조:** 관련 서사 [NEO-67972](https://jira.corp.adobe.com/browse/NEO-67972)

---

### [NEO-90130](https://jira.corp.adobe.com/browse/NEO-90130) - 다국어 푸시 알림에 대해 OOTB 파일 업로드 사용
**상태:** 닫힘\
**문서 필요:** 예\
**기존 DOCAC:** [DOCAC-13606](https://jira.corp.adobe.com/browse/DOCAC-13606)&#x200B;(신규)\
**작업:** DOCAC 업데이트

**범위:**
- 다국어 푸시 알림용 파일 업로드(iOS 및 Android)
- CSV 형식 및 필드 매핑
- 다국어 기능을 통한 다양한 푸시 지원

**기능 설명:**
CSV 가져오기를 통해 다국어 푸시 알림 게재를 만들고 ACS 기능을 일치시키며 효율적인 다국어 캠페인 구성을 가능하게 하는 OOTB 파일 업로드 기능입니다.

**컨텍스트:** 고객 기반(H&amp;M), ACS에서 ACC로의 패리티, 마이그레이션에 중요

**참조:** [ACS 설명서](https://experienceleague.adobe.com/en/docs/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push)

---

## ❌이(가) 취소됨/더 이상 적용되지 않음

### [NEO-91566](https://jira.corp.adobe.com/browse/NEO-91566) - webui에서 CTA 추적 지원
**상태:** 닫힘(더 이상 적용되지 않음)\
**문서 필요:** 아니요\
**기존 DOCAC:** [DOCAC-13821](https://jira.corp.adobe.com/browse/DOCAC-13821)&#x200B;(신규)\
**작업:** DOCAC 닫기

**이유:** MSFT를 지원하는 새 ACS 기능 - 시작되지 않음, MSFT에서 보류 중인 정보, 필요한 UI 작업 없음

**컨텍스트:** Microsoft 전용, CTA 추적 요구 사항

---

### [NEO-91564](https://jira.corp.adobe.com/browse/NEO-91564) - AEM 다국어 UI 지원
**상태:** 닫힘(더 이상 적용되지 않음)\
**문서 필요:** 아니요\
**기존 DOCAC:** [DOCAC-13822](https://jira.corp.adobe.com/browse/DOCAC-13822)&#x200B;(신규)\
**작업:** DOCAC 닫기

**이유:** Himanshu 팀에서 관리하는 UI 작업(다른 스토리)

**컨텍스트:** Microsoft 요구 사항, 작업 전송됨

---

### [NEO-91567](https://jira.corp.adobe.com/browse/NEO-91567) - NRT 기능에 대한 지원 추가
**상태:** 해결됨(더 이상 적용되지 않음)\
**문서 필요:** 아니요\
**기존 DOCAC:** [DOCAC-13824](https://jira.corp.adobe.com/browse/DOCAC-13824)&#x200B;(신규)\
**작업:** DOCAC 닫기

**이유:** MSFT용 새 ACS 특정 기능 - 사양을 사용할 수 있지만 웹 UI에 영향을 주지 않음

**컨텍스트:** Microsoft 요구 사항, 트랜잭션 메시지

---

### [NEO-91563](https://jira.corp.adobe.com/browse/NEO-91563) - 프로필 기반 강화를 위한 트랜잭션 Rest API
**상태:** 해결됨(더 이상 적용되지 않음)\
**문서 필요:** 아니요\
**기존 DOCAC:** [DOCAC-13825](https://jira.corp.adobe.com/browse/DOCAC-13825)&#x200B;(신규)\
**작업:** DOCAC 닫기

**이유:** 웹 UI가 작동하지 않습니다. 업그레이드된 인스턴스를 보류 중입니다. 릴리스에는 빌드 업그레이드가 필수입니다.

**컨텍스트:** REST API 끝점 기능

---

### [NEO-92151](https://jira.corp.adobe.com/browse/NEO-92151) - 프로필 기반 데이터 보강 트랜잭션 메시지 2단계
**상태:** 해결됨(더 이상 적용되지 않음)\
**문서 필요:** 아니요\
**기존 DOCAC:** [DOCAC-13823](https://jira.corp.adobe.com/browse/DOCAC-13823)&#x200B;(신규)\
**작업:** DOCAC 닫기

**이유:** 스토리에 작업이 없습니다. &quot;더 이상 적용되지 않음&quot;으로 표시됨

**컨텍스트:** Microsoft 요구 사항, Europa 프로젝트

---

## 🟢 설명서 준비(AC-UI-25-11에서)

### [NEO-90183](https://jira.corp.adobe.com/browse/NEO-90183) - 다국어 리치 푸시 - UI
**상태:** 닫힘\
**문서 필요:** 예\
**기존 DOCAC:** [DOCAC-13565](https://jira.corp.adobe.com/browse/DOCAC-13565)&#x200B;(신규)\
**작업:** DOCAC 검토

**범위:**
- 다국어 게재용 리치 푸시 필드
- iOS 및 Android 플랫폼 지원
- 템플릿 및 콘텐츠 구성

**기능 설명:**
다국어 기능을 통한 풍부한 푸시 알림 지원을 통해 마케터는 iOS 및 Android 모두에 대해 여러 언어로 이미지, 버튼 및 리치 미디어를 사용하는 향상된 푸시 알림을 만들 수 있습니다.

**컨텍스트:** 고객 기반(H&amp;M), 25-11에 제공, 백엔드 작업 완료

**참조:** [Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=Rich+push+fields+in+multilingual)

---

### [NEO-84916](https://jira.corp.adobe.com/browse/NEO-84916) - 승인 프로세스 설정 및 관리
**상태:** 해결됨\
**문서 필요:** 예\
**기존 DOCAC:** [DOCAC-13827](https://jira.corp.adobe.com/browse/DOCAC-13827)&#x200B;(신규)\
**작업:** DOCAC 업데이트

**범위:**
- 게재/캠페인에서 유효성 검사 연산자 구성
- 승인 작업 과정 설정
- 콘텐츠 및 대상 승인 프로세스
- 다중 채널 지원(이메일, SMS, 푸시, DM, 콜 센터, 사용자 정의)

**기능 설명:**
모든 게재 채널에서 운영자 할당 및 승인 추적을 통해 게재 콘텐츠 및 타겟팅에 대한 유효성 검사 워크플로우를 가능하게 하는 승인 프로세스 관리

**컨텍스트:** 고객 중심(Pierre Fabre), Microsoft 요구 사항, 개발 완료 및 테스트 중

**참조:** [클래식 설명서](https://experienceleague.adobe.com/en/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval), [그림 목마](https://www.figma.com/design/r2vpqXoVyI3aucKgkt8TLN/Approvals)

---

## 작업별 📊 요약

| 작업 | 계수 |
|--------|-------|
| 🟢 DOCAC 만들기 | 3 |
| 🔄 DOCAC 업데이트 | 6 |
| ✅ DOCAC 검토 | 3 |
| ❌ DOCAC 닫기 | 5 |
| 총 **개** | **17** |

---

## 진행 중인 질문 ⚠️개

1. NEO-93487 - H&amp;M 에스컬레이션 - 컴퓨팅 프로세스 예약에 긴급한 주의 필요
2. NEO-92668 - 웹 분석 - 설명서를 완료하기 전에 환경 가용성 대기 중
3. NEO-76126 - 스키마 3단계 - ETA 2월 말, 별도의 설명서 스토리 필요
4. NEO-88838 - 테마 변수 - 보류 중 Acrite 기능 개정
5. 동적 보고 - 이전 보고와 관련된 충돌 지표 표시 지침을 명확하게 합니다.

---

## 🔗 관련 Epics

- NEO-85263 - ACS-ACC(EUROPA) 상위 서사
- NEO-67972 - 워크플로우 개선 사항
- NEO-87980 - 고급 AEM 통합
- NEO-90199 - 동적 보고 릴리스 준비
- NEO-63067 - 콘텐츠 실험 UX/UI
- NEO-67726 - A/B 테스트 및 콘텐츠 실험
- NEO-85274 - 스키마 및 양식(2단계)
- NEO-87993 - 스키마 및 양식(3단계)
