---
title: Campaign v8 FAQ
description: 설정, 구성, 메시징, 워크플로 등에 대한 일반적인 Adobe Campaign v8 질문에 대한 답변을 얻을 수 있습니다
feature: Overview
role: User
level: Beginner
keywords: FAQ, Campaign v8, 질문, 답변, 도움말, 지원, 문제 해결
version: Campaign v8
source-git-commit: 9c751429ac3da2a583990ba0d891744353bd65c8
workflow-type: tm+mt
source-wordcount: '10116'
ht-degree: 7%

---

# 자주 묻는 질문 {#faq}

Adobe Campaign v8에 대해 가장 일반적인 질문에 대한 빠른 답변을 얻으십시오. 이제 막 시작했거나 고급 구성 도움말을 찾고 있는 경우 아래 주제별로 구성된 답변을 찾을 수 있습니다.

Campaign을 **처음 사용하시겠습니까?** 필수 구성 요소를 배우려면 [시작하기](#getting-started)로 시작하십시오.\
**버전에 대한 도움말이 필요하십니까?** 버전 정보 및 업그레이드 프로세스를 보려면 [업그레이드](#upgrades)를 확인하십시오.\
**v7 또는 Standard에서 마이그레이션하시겠습니까?** 차이점 및 전환 지침은 [Campaign v8과 이전 버전](#v7-differences)을 참조하세요.\
**기술 지원이 필요하십니까?** [개발자](#developers) 및 [캠페인 설정](#settings)을 확인하세요.\
**답변을 찾을 수 없습니까?** [커뮤니티 포럼](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}을 방문하거나 [지원 팀에 문의](#get-help)하세요.

**팁:** Ctrl+F(Mac의 Cmd+F)를 사용하여 이 페이지에서 특정 키워드를 검색합니다. 질문을 클릭하여 답변을 확장합니다.


##  시작 {#getting-started}

설치 및 연결에서 첫 번째 캠페인 만들기에 이르기까지 Adobe Campaign v8 작업을 시작하는 데 필요한 필수 사항에 대해 알아봅니다.

+++ Adobe Campaign v8이란?

Adobe Campaign v8은 이메일, 모바일, 소셜 및 오프라인 채널 전반에서 개인화된 캠페인을 제작, 조정 및 제공할 수 있는 강력한 크로스채널 마케팅 자동화 플랫폼입니다. 강력한 마케팅 데이터베이스, 캠페인 오케스트레이션 엔진 및 실시간 상호 작용 기능을 결합하여 여정 전반에 걸쳐 고객을 참여시킵니다.

**주요 기능:** 멀티채널 캠페인 관리, 대상자 세분화 및 타기팅, 워크플로우 자동화, 규모에 맞는 개인화, 실시간 및 일괄 메시징, 보고 및 분석, Adobe Experience Cloud과의 통합.

**v8의 고유한 기능:** 클라우드 기반 아키텍처(Managed Cloud Services만 해당), Snowflake 데이터베이스를 기반으로 하는 엔터프라이즈급 성능, 자동 업그레이드, 향상된 보안 및 Adobe Experience Platform과의 양방향 통합.

**다음 대상입니다.** 여러 채널 및 고객 접점에서 복잡한 대량 캠페인을 관리하는 엔터프라이즈 마케팅 팀.

**관련 항목:**

[Campaign v8 제품 설명](https://helpx.adobe.com/kr/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"} | [v8의 새로운 기능](whats-new.md) | [시작 안내서](get-started.md)

+++

+++ Campaign을 다운로드하는 방법은 무엇인가요?

Adobe 다운로드 센터에서 설치 프로그램과 클라이언트 콘솔을 다운로드할 수 있습니다.

관리 사용자로 Adobe [소프트웨어 배포](https://experience.adobe.com/#/downloads/content/software-distribution/ko/campaign.html){target="_blank"}에 액세스하여 Adobe Campaign을 다운로드합니다.

이 페이지에서 [ 배포 센터에 대해 자세히 알아보세요](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=ko){target="_blank"}.

+++

+++ Campaign v8에 연결하려면 어떻게 해야 합니까?

Adobe Campaign에 연결하려면 Campaign 클라이언트 콘솔을 다운로드하여 설치해야 합니다. [자세히 알아보기](connect.md)

Campaign v8.6 릴리스부터 중앙 Adobe Experience Cloud 환경을 통해 사용할 수 있는 **Campaign 웹 사용자 인터페이스**&#x200B;에 액세스할 수 있습니다. Experience Cloud은 Adobe의 디지털 마케팅 애플리케이션, 제품 및 서비스 통합 제품군입니다.

Adobe Experience Cloud에 연결하고 Adobe Campaign 웹 인터페이스 [에 액세스하는 방법은 이 페이지에서](campaign-ui.md#ac-web-ui)알아볼 수 있습니다. [Adobe Campaign Web 사용자 인터페이스 설명서](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/campaign-web-home){target="_blank"}에서 자세히 알아보십시오.


**관련 항목:**

[클라이언트 콘솔 설치](connect.md) | [Campaign 사용자 인터페이스](campaign-ui.md) | [사용자 권한](gs-permissions.md)

+++

+++ Adobe ID으로 Campaign v8에 연결할 수 있습니까?

예! IMS(Adobe Identity Management System)와의 통합 덕분에 사용자는 Adobe ID을 사용하여 Adobe Campaign 콘솔에 연결합니다. 이 통합은 다음과 같은 이점을 제공합니다.

*  모든 Experience Cloud 솔루션에 동일한 ID를 사용할 수 있습니다.
* 서로 다른 통합으로 Adobe Campaign을 사용하는 경우 연결이 기억됩니다.
* 보안 암호 관리 정책.
* 페더레이션 ID 계정 사용(외부 ID 공급자).

Adobe ID을 사용하여 Campaign v8에 액세스하는 방법에 대해 [자세히 알아보기](connect.md).

+++

+++ 알아야 하는 Campaign 사용자 인터페이스 개념은 무엇입니까?

Adobe Campaign 사용자 인터페이스 기본 사항에 대한 자세한 내용은 [이 섹션](campaign-ui.md)을 참조하세요.

Campaign v8.6 릴리스부터 중앙 Adobe Experience Cloud 환경을 통해 사용할 수 있는 새로운 **Campaign 웹 사용자 인터페이스**&#x200B;에 액세스할 수 있습니다.

[Adobe Campaign 웹 사용자 인터페이스 설명서에서 자세히 알아보세요](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

+++

+++ 사용자 권한을 설정하려면 어떻게 해야 합니까?

Campaign 관리자는 조직의 사용자에 대한 권한을 설정할 수 있습니다.

다음은 권한을 부여하거나 거부한 권한 및 제한 세트입니다.

* 특정 기능에 액세스
* 특정 데이터에 액세스
* 데이터 만들기, 수정 및/또는 삭제

**관련 항목:**

[사용 권한 시작](gs-permissions.md) | [사용자 권한 관리](manage-permissions.md) | [폴더에 권한 추가](folder-permissions.md)

+++

+++ 메시지 대상자를 선택하려면 어떻게 해야 합니까?

Campaign은 메시지에 적합한 대상자를 선택할 수 있는 다양한 타깃팅 방법을 제공합니다.

**타깃팅 메서드:**

* **쿼리 편집기** - 받는 사람 특성, 동작 또는 인구 통계에 대한 시각적 필터를 사용하여 대상을 만듭니다.
* **목록** - 사전 정의된 정적 또는 동적 받는 사람 목록을 사용합니다.
* **파일 가져오기** - 일회성 캠페인에 대한 외부 수신자 파일 업로드
* **워크플로우** - 쿼리, 분할 및 데이터 보강 활동을 사용하여 복잡한 타깃팅 논리를 만듭니다.
* **미리 정의된 필터** - 바로 사용 가능한 필터(활성 고객, 구독자, VIP) 적용
* **Adobe Experience Platform의 세그먼트** - 통합 프로필 및 실시간 세그먼트 활용

여러 기준(위치, 구매 내역, 참여)을 결합하고 제외, 교집합 또는 합집합을 사용하여 대상을 세분화할 수 있습니다.

**관련 항목:**

[Campaign v8에서 대상 정의](../audiences/gs-audiences.md) | [쿼리 편집기](query-editor.md) | [대상 매핑](../audiences/target-mappings.md)

+++

+++ 첫 번째 이메일을 만들고 보내는 방법

Campaign v8에서 첫 번째 이메일을 만드는 것은 간단합니다. 템플릿에서 시작하여 타겟 대상을 선택하고, 개인화로 콘텐츠를 디자인하고, 증명으로 테스트한 다음 전송합니다. Campaign은 전자 메일 생성을 위한 두 가지 인터페이스를 제공합니다. 고급 사용자를 위한 전체 기능 **클라이언트 콘솔**&#x200B;과 보다 빠르고 직관적인 전자 메일 빌드를 위한 최신 **Campaign 웹 UI**.

**5개의 주요 단계:**

1. **게재 만들기** - 전자 메일 템플릿에서 시작하거나 처음부터 만들기
2. **대상 정의** - 쿼리, 목록 또는 워크플로를 사용하여 받는 사람 선택
3. **콘텐츠 디자인** - 전자 메일 디자이너를 사용하여 개인화 필드가 있는 메시지를 만들 수 있습니다.
4. **테스트 증명 보내기** - 장치 및 전자 메일 클라이언트 간 렌더링 및 콘텐츠 유효성 검사
5. **분석 및 보내기** - 게재 분석을 실행하여 오류를 확인한 다음 이메일을 보냅니다.

**관련 항목:**

[전자 메일 디자인 및 유효성 검사](../send/email.md) | [첫 번째 게재 만들기](create-message.md) | [게재 템플릿](../send/create-templates.md) | [콘텐츠 개인화](../send/personalize.md)

+++

+++ 오류 메시지를 번역하는 방법

외국어로 오류 메시지가 표시됩니까? 모든 오류 메시지와 해당 번역이 [이 페이지](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=ko){target="_blank"}에 나열됩니다.

+++

+++ 문제를 기록하려면 어떻게 해야 합니까?

Adobe 고객 지원 센터에 문의하려면 [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"}에 연결하여 서비스 케이스를 만들거나 채팅 세션을 시작하십시오.

올바른 권한을 가진 개별 계정이 필요합니다. 로그인할 수 없는 경우 Experience League을 통해 액세스를 요청합니다. [자세히 알아보기](https://helpx.adobe.com/kr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

또는 [Campaign 커뮤니티](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}에 참여하여 답변을 검색하거나 전문가에게 질문해 보십시오.

+++

+++ 어떤 시스템과 구성 요소가 Campaign v8과 호환됩니까?

[Adobe Campaign 호환성 매트릭스](compatibility-matrix.md)에서 Campaign 최신 빌드에 대해 지원되는 모든 시스템 및 구성 요소 목록을 가져올 수 있습니다.

+++

+++ 다른 Adobe 솔루션과 함께 Campaign v8을 사용할 수 있습니까?

예. Campaign v8은 통합 마케팅 에코시스템을 위해 Adobe Experience Cloud 솔루션과 원활하게 통합됩니다.

**주요 통합:** Adobe Experience Platform(통합 프로필, 실시간 데이터), Adobe Analytics(성능 측정), Adobe Target(개인화), Adobe Experience Manager(컨텐츠 관리), Adobe Audience Manager(대상 세그먼트).

**설치:**&#x200B;에는 Campaign v8 관리 클라우드 서비스에 대해 자동으로 구성된 Adobe IMS 인증이 필요합니다.

**관련 항목:**

[Adobe Campaign 통합](../connect/integration.md) | [Adobe ID과 연결](connect.md)

+++

+++ Campaign v8의 제한 사항은 무엇입니까?

Campaign v8은 성능이 크게 개선되었지만 특히 FFDA 배포의 경우 Campaign Classic v7과 일부 아키텍처 차이가 있습니다.

**주요 고려 사항:**

* **FFDA 아키텍처** - 다양한 데이터 액세스 패턴을 가진 클라우드 데이터베이스(Snowflake)를 사용합니다.
* **데이터 업데이트** - 직접 데이터베이스 액세스를 통하지 않고 워크플로우에서 수행해야 합니다.
* **일괄 처리 최적화** - 빈도가 높은 개별 업데이트가 아닌 일괄 처리 작업에 최적화되었습니다.
* **FFDA에서 사용할 수 없음** - 설문 조사, 마케팅 리소스 관리(MRM), 일부 특정 커넥터

**마이그레이션 영향:** 직접 데이터베이스 쓰기를 사용하는 사용자 지정 코드에는 리팩터링이 필요합니다. API 통합에는 일괄 처리를 위한 조정이 필요할 수 있습니다.

Adobe이 v8을 향상함에 따라 이러한 제한 사항이 발전하고 있습니다. 현재 상태에 대해서는 최신 설명서를 참조하십시오.

**관련 항목:**

[Campaign v7에서 v8로의 마이그레이션](../start/v7-to-v8.md#limitations) | [FFDA 아키텍처](../architecture/enterprise-deployment.md)

+++

+++ Campaign Classic v7 사용자는 Campaign v8로 마이그레이션할 수 있나요?

기존 Campaign Classic v7 환경에서의 자동 마이그레이션은 아직 불가능합니다.

Campaign v8은 현재 **관리 클라우드 서비스로만 사용할 수 있으며** 온-프레미스 또는 하이브리드 환경에 배포할 수 없습니다.

마이그레이션 프로세스에 대한 자세한 내용은 Adobe 담당자에게 문의하십시오.

자세한 내용은 [Campaign v8 및 이전 버전](#v7-differences) 섹션을 참조하세요.

+++


## 업그레이드 {#upgrades}

Campaign 버전을 확인하고 업그레이드 프로세스를 이해하며 새로운 릴리스에 대한 정보를 유지하는 방법을 알아봅니다. Campaign v8 Managed Cloud Services는 중단을 최소화하면서 업그레이드를 자동으로 처리합니다.

+++ Campaign의 버전은 무엇입니까?

Campaign 클라이언트 콘솔의 **도움말 > 정보...[ 메뉴에서 버전 및 빌드 번호](upgrades.md#version)를** 확인합니다.

+++

+++ Campaign을 최신 버전으로 업그레이드하려면 어떻게 해야 합니까?

Adobe Campaign은 정기적으로 업데이트됩니다. 일부 버전은 새로운 기능, 개선 사항 및 수정 사항이 포함되어 매년 출시됩니다. 또한, 누적 수정 사항만 있는 빌드를 주기적으로 릴리스합니다.

이러한 정기 업데이트 빈도는 최신 업데이트를 직접 경험해 보고 사용 환경을 안전하게 지키며 Adobe 제품 경험을 향상시키는 것을 목표로 합니다. 이 때문에 Adobe Campaign의 최신 버전을 실행하는 것이 매우 중요하다고 생각합니다.

**참고:** Managed Cloud Services 사용자는 새 릴리스를 통해 Adobe에서 인스턴스를 업그레이드합니다.

[Campaign 버전 및 업그레이드에 대해 자세히 알아보세요](upgrades.md).

+++

+++ 새 버전의 릴리스에 대한 정보는 어떻게 얻을 수 있습니까?

다음 채널을 통해 새로운 Campaign 릴리스에 대한 최신 정보 제공:

* **Adobe 담당자** - 새 버전을 사용할 수 있는 경우 직접 연락합니다.
* **릴리스 정보** - [Campaign 릴리스 정보](release-notes.md)에 문서화된 모든 버전 및 변경 사항
* 이메일 알림용 **Adobe 우선 순위 제품 업데이트** - [구독](https://www.adobe.com/kr/subscription/priority-product-update.html){target="_blank"}
* **Campaign 커뮤니티** - 초기 업데이트를 위해 [토론](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}에 참여

Managed Cloud Services 사용자는 Adobe을 사용하여 업그레이드를 처리하고 시간 조정을 수행할 수 있습니다.

**관련 항목:**

[릴리스 정보](release-notes.md) | [새로운 기능](whats-new.md) | [Campaign 버전 및 업그레이드](upgrades.md)

+++

+++ 조직에 업그레이드가 필요한 이유는 무엇입니까?

최신 Campaign 버전으로 업그레이드하는 것은 보안, 성능 및 지원 품질에 매우 중요합니다.

**주요 이점:**

* **향상된 보안** - 취약점, 최신 패치, 향상된 데이터 보호 방지
* **향상된 지원** - 문제 해결 시간 단축, 버그 수정 액세스, 최신 버전에 대한 우선 순위 지원
* **향상된 성능** - 데이터베이스 및 워크플로 최적화, 향상된 확장성, 보다 안정적인 작업
* **새로운 기능** - 최신 기능, 향상된 Adobe Experience Cloud 통합, 최신 UI 개선 사항

Adobe에서는 최신 버전을 실행하는 것이 좋습니다. Managed Cloud Services 고객은 Adobe에서 중단을 최소화하면서 업그레이드를 수행합니다.

**관련 항목:**

[Campaign 버전 및 업그레이드](upgrades.md) | [새로운 기능](whats-new.md) | [호환성 매트릭스](compatibility-matrix.md)

+++

+++ 업그레이드의 프로세스와 타임라인은 무엇입니까?

Managed Cloud Services 고객인 Adobe은 운영에 미치는 영향을 최소화하면서 전체 업그레이드 프로세스를 관리합니다.

**프로세스:**

1. **알림** - Adobe에서 몇 주 전에 미리 알려줍니다.
2. **계획** - Adobe 담당자와 최적의 시간에 업그레이드 일정을 예약합니다.
3. **준비** - Adobe이 환경을 준비하고 유효성을 검사합니다.
4. **실행** - Adobe이 가동 중지 시간을 최소화하면서 인프라를 업그레이드합니다.
5. **유효성 검사** - Adobe의 업그레이드 후 테스트
6. **클라이언트 콘솔 업그레이드** - 서버 버전에 맞게 클라이언트 콘솔을 업그레이드합니다.

**귀하의 책임:**

* 타이밍을 위해 내부 이해 당사자 조정
* 새 버전으로 [클라이언트 콘솔 업그레이드](connect.md#upgrade-ac-console)
* 업그레이드 후 캠페인 및 워크플로우 테스트
* Adobe 지원에 문제 보고

Adobe은 인프라 업그레이드를 수행합니다. 서버에서 기술 작업을 수행할 필요가 없습니다.

**관련 항목:**

[Campaign 버전 및 업그레이드](upgrades.md) | [클라이언트 콘솔 업그레이드](connect.md#upgrade-ac-console) | [릴리스 정보](release-notes.md)

+++


## Campaign v8과 이전 버전 {#v7-differences}

아키텍처, 배포, 마이그레이션 경로, 기능 변경 사항을 포함하여 Campaign v8과 이전 버전(Classic v7 및 Standard)의 주요 차이점을 이해합니다. Campaign Classic v7 또는 Campaign Standard 출신이든 새로운 기능과 원활하게 전환하는 방법에 대해 알아보십시오.


+++ Campaign v8과 이전 버전 간의 주요 차이점은 무엇입니까?

Campaign v8은 다음과 같이 대폭 향상된 최신 클라우드 기반 아키텍처를 기반으로 합니다.

* **관리 클라우드 서비스만** - Adobe에서 완전히 호스팅(온-프레미스/하이브리드 옵션 없음)
* **뛰어난 성능** - 시간당 최대 2,000만 개의 작업(FFDA(Full Federated Data Access) 아키텍처 사용)
* **새로운 Campaign 웹 UI** - 클래식 콘솔과 함께 현대적이고 직관적인 인터페이스
* **자동 업그레이드** - 가동 중지 시간 없이 항상 최신 버전
* **향상된 기능** - AI Assistant, 리치 푸시 알림, 업그레이드된 SMS, Adobe Experience Cloud과의 통합 개선

**Campaign Classic v7 사용자:** 아키텍처 변경 사항, 사용할 수 없는 기능 및 마이그레이션 고려 사항을 포함하여 [v7에서 v8로 전환](v7-to-v8.md)에 대해 알아봅니다.

**Campaign Standard 사용자의 경우:** [v8로의 전환 경로](acs-to-v8.md) 및 [Campaign Standard 마이그레이션 안내서](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/acs-migration){target="_blank"}를 살펴보십시오.

**관련 항목:**

[Campaign v8 주요 기능](whats-new.md) | [Campaign v8 아키텍처](../architecture/architecture.md) | [기능 매트릭스](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [보호 기능 및 제한 사항](ac-guardrails.md)

+++

+++ Campaign Classic v7 또는 Campaign Standard에서 v8로 마이그레이션해야 합니까?

Campaign v8은 Adobe의 플랫폼으로, 대량 캠페인(시간당 2천만 건), 최신 웹 UI, 클라우드 기반의 이점 및 장기 지원이 필요한 조직에 이상적입니다.

**주요 이점:**

* **Campaign Standard 사용자용** - 친숙한 웹 UI, 기능 패리티(동적 보고, REST API, 랜딩 페이지), 원활한 데이터 마이그레이션
* **Campaign Classic v7 사용자용** - 듀얼 인터페이스(콘솔 + 웹 UI), 향상된 성능, 자동 업그레이드, 향상된 FFDA 아키텍처

**다음 경우에 마이그레이션하는 것이 좋습니다.**

* 대용량 데이터 볼륨 또는 경험 성능 문제 처리
* IT 오버헤드와 인프라 관리를 줄이고자 함
* Adobe Experience Cloud/플랫폼 통합 필요
* 자동 업데이트로 미래형 기술 필요

**다음 단계:** Adobe 담당자에게 문의하여 마이그레이션 준비 상태를 평가하고 마이그레이션 도구에 액세스합니다.

**관련 항목:**

[Campaign Classic v7에서 v8로](v7-to-v8.md) | [Campaign Standard 전환 안내서](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [기능 매트릭스](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}

+++

+++ Campaign v8을 온-프레미스 또는 하이브리드 환경에 설치할 수 있습니까?

아니요. Campaign v8은 Adobe에서 완전히 호스팅하는 **관리 Cloud Service**&#x200B;로만 사용할 수 있습니다.

**Managed Cloud Services의 주요 이점:**

* 탁월한 성능 및 확장성
* 자동 업그레이드 - 항상 최신 버전
* 지속적인 모니터링으로 보안 향상
* 인프라 관리 또는 IT 오버헤드가 없음
* 고가용성 및 재해 복구 기능 내장

[Campaign v8 아키텍처](../architecture/architecture.md) 및 [Campaign v8과 Classic v7의 차이점](../start/v7-to-v8.md)에 대해 자세히 알아보세요.

+++

+++ Campaign Classic v7 On-Premise 또는 Hybrid 환경을 Adobe Managed Services으로 마이그레이션하려면 어떻게 합니까?

Adobe Managed Services으로 마이그레이션하면 온-프레미스/하이브리드 v7에서 클라우드로의 전략적 경로가 제공되어 향상된 확장성, 보안 및 IT 오버헤드를 줄일 수 있습니다. 이는 Campaign v8로 전환하기 전의 징검다리인 경우가 많습니다.

**주요 사항:**

* 사용 가능한 자동 마이그레이션 툴 없음 - 수동 계획 및 실행 필요
* Adobe Professional Services 지원이 적극 권장됨
* 클라우드 인프라, 자동 보안 패치, 전문가 지원, v8로 가는 쉬운 경로 등의 이점을 제공합니다
* 마이그레이션은 실사, 환경 감사, 데이터 정리, 스테이지 마이그레이션, 프로덕션 전환 등의 작업을 포함합니다.

**시작하기:** Adobe 담당자에게 문의하여 환경을 평가하고 Adobe Professional Services을 통한 자세한 마이그레이션 계획을 개발하십시오.

과제, 모범 사례 및 자세한 마이그레이션 로드맵을 포함하여 [Managed Services으로 마이그레이션](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic-blogs/migrate-your-adobe-campaign-v7-onprem-hybrid-environment-to/ba-p/681605){target="_blank"}하는 방법에 대해 자세히 알아보십시오.

+++

+++ Campaign v8의 주요 용어 및 기능 차이점은 무엇입니까?

Campaign v8은 대부분의 v7/Standard 기능을 개선했지만 일부 용어와 기능은 다릅니다. 아래에서 주요 변경 사항에 대한 요약을 확인할 수 있습니다.

**주요 용어 변경(Campaign Standard → v8):**

* 사용자 지정 리소스 →**스키마** | 메시지 → **게재** | 제품 사용자 → **운영자**
* 보안 그룹 → **운영자 그룹** | 조직 단위 → **폴더 권한**

**Campaign 웹 UI 업데이트:**

* **→**&#x200B;을(를) 받는 사람 | 시드 주소 → **테스트 프로필** | 게재 분석 → **게재 준비**
* {→}대상&#x200B;**목록 | 이메일 미리 보기 →**&#x200B;콘텐츠 시뮬레이션&#x200B;****

**v8에서 사용할 수 없음:**

* 온-프레미스/하이브리드 배포(Managed Cloud Services만 해당)
* 직접 데이터베이스 액세스(API 사용)
* 수동 인프라 관리(Adobe 관리)

**Campaign Standard 사용자를 위한 새로운 기능:**

* 동적 보고, 중앙 집중식 브랜딩, REST API, 랜딩 페이지 개선 사항, 시각적 조각

**관련 항목:**

[기능 매트릭스](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [v7에서 v8로의 전환 안내서](v7-to-v8.md) | [Campaign Standard에서 v8로 전환](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++


## 프로필 및 대상자 {#audiences}

캠페인 프로필 관리, 대상자 만들기, 데이터 가져오기 및 수신자 타겟팅에 대한 질문에 대한 답변을 찾을 수 있습니다.

+++ 수신자를 만드는 방법

개별 프로필에 대해 클라이언트 콘솔에서 수동으로 수신자를 만들거나, 대량 추가를 위해 파일에서 가져오기(CSV/TXT), 자체 등록을 위해 웹 양식을 사용하거나, 외부 시스템의 API를 통해 통합할 수 있습니다. 가져오기 워크플로우를 사용하여 반복되는 데이터를 로드합니다.

**관련 항목:**

[수동으로 프로필 만들기](../audiences/create-profiles.md) | [파일에서 프로필 가져오기](../audiences/import-profiles.md) | [웹 양식으로 프로필 수집](../audiences/collect-profiles.md)

+++

+++ 프로필을 가져오는 방법

Campaign은 가져오기 마법사를 사용한 간단한 파일 가져오기, 복잡한 변환을 위한 워크플로우 기반 가져오기, SFTP에서 예약된 워크플로우를 사용한 반복 가져오기, 프로그래밍 방식의 통합을 위한 API 가져오기 등 다양한 가져오기 방법을 제공합니다.

파일 가져오기의 경우 데이터 파일(CSV/TXT, UTF-8 인코딩)을 준비하고, 가져오기 마법사 또는 워크플로우를 사용하고 열을 Campaign 필드에 매핑하고, 업데이트/삽입 규칙을 정의하고 작은 샘플로 먼저 테스트합니다. 반복 가져오기에 워크플로우를 사용하고 중복 제거 규칙을 적용합니다.

**관련 항목:**

[데이터 가져오기 안내서](../start/import.md) | [가져오기 워크플로우 반복](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"} | [데이터 로드 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"}

+++

+++ 게재에 대한 테스트 프로필을 만들려면 어떻게 해야 합니까?

테스트 프로필(시드 주소)을 사용하면 정의된 타겟팅 기준과 일치하지 않는 수신자를 타겟팅할 수 있으므로, 주 대상자에게 보내기 전에 게재를 테스트할 수 있습니다. 게재 속성에서 **[!UICONTROL Seed addresses]**&#x200B;을(를) 통해 추가하거나 **[!UICONTROL Seed addresses]** 폴더를 사용하십시오.

[테스트 프로필](../audiences/test-profiles.md)에 대해 자세히 알아보세요.

+++

+++ 마케팅 캠페인의 대상 모집단을 정의하려면 어떻게 해야 합니까?

Campaign은 시각적 기준으로 쿼리를 빌드하거나, 기존 목록 또는 세그먼트를 타겟팅하거나, 외부 파일(CSV, TXT)에서 수신자를 가져오거나, 사전 정의된 필터를 적용하는 등 다양한 타겟팅 방법을 제공합니다. AND/OR 논리와 기준을 결합하고, 특정 모집단을 제외하고, 제어 그룹을 사용하고, A/B 테스트를 위해 분할할 수 있습니다. 보내기 전에 항상 대상 모집단 크기를 미리 봅니다.

**관련 항목:**

[캠페인 대상 정의](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=ko){target="_blank"} | [쿼리 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"} | [대상자 만들기](../audiences/create-audiences.md)

+++

+++ 프로필 목록을 만들려면 어떻게 해야 합니까?

목록은 게재에서 타겟팅하고 캠페인 간에 재사용할 수 있는 정적 수신자 세트입니다.

**세 가지 생성 방법:**

* **수동 만들기:** **[!UICONTROL Profiles and Targets > Lists]**(으)로 이동하여 **[!UICONTROL Create]**&#x200B;을(를) 클릭합니다. 쿼리, 개별 선택 또는 폴더에서 수신자를 추가합니다.

* **워크플로 자동화:** **[!UICONTROL List update]** 활동을 사용하여 쿼리 결과 또는 가져온 데이터에서 자동으로 목록을 만들고 유지 관리합니다.

* **가져오는 중:** 프로필을 가져올 때 목록을 만들어 재사용 가능한 그룹으로 저장합니다.

**팁:** 정기 업데이트가 필요한 목록에는 워크플로우를 사용하고 일회성 세그먼테이션을 수행하려면 수동으로 만드십시오.

**관련 항목:**

[대상자 만들기](../audiences/create-audiences.md) | [업데이트 활동 나열](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html){target="_blank"}

+++

+++ 메시지를 보내기 전에 모집단 중복을 제거하려면 어떻게 해야 합니까?

워크플로우에서 **[!UICONTROL Deduplication]** 활동을 사용하여 배달하기 전에 중복 수신자를 제거합니다. **[!UICONTROL Query]**&#x200B;과(와) **[!UICONTROL Delivery]** 활동 사이에 배치한 다음 중복 제거 기준(일반적으로 이메일 주소 또는 수신자 ID)과 보관할 레코드를 선택하십시오.

**팁:** 각 사용자가 메시지를 한 번만 받도록 하려면 보내기 전에 항상 중복 제거를 수행하세요.

[중복 제거 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html){target="_blank"}에 대해 자세히 알아보기

+++

+++ 뉴스레터 가입자를 식별하고 타겟팅하는 방법

Campaign은 정보 서비스를 통해 뉴스레터 구독을 자동으로 추적합니다. 구독자를 타겟팅하려면:

* **[!UICONTROL Query]** 활동을 사용하고 **[!UICONTROL Subscriptions]**&#x200B;에서 필터링하고 뉴스레터 서비스를 선택하세요.
* **[!UICONTROL To > Subscribers of an information service]**&#x200B;을(를) 선택하여 게재에서 바로 구독자를 타겟팅합니다.
* **[!UICONTROL Subscription Services]** 워크플로우 활동으로 구독자 목록 작성

Campaign은 구독/구독 취소 기록을 추적하고 옵트인/옵트아웃을 자동으로 관리합니다.

**관련 항목:**

[구독 관리](../start/subscriptions.md) | [쿼리 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}

+++

+++ 대상 모집단에서 프로필을 제외하는 가장 좋은 방법은 무엇입니까?

워크플로우에서 **[!UICONTROL Exclusion]** 활동을 사용하여 대상에서 원치 않는 프로필을 제거하십시오. 타겟팅 활동 뒤에 배치하고 제외할 모집단을 정의합니다.

[제외 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html){target="_blank"}에 대해 자세히 알아보기

+++


## 메시지 디자인 {#design}

이메일 템플릿, 개인화 기술 및 다국어 콘텐츠를 포함하여 Campaign v8에서 효과적인 마케팅 메시지를 디자인하는 방법을 알아봅니다. 향상된 시각적 편집 환경을 위해 클라이언트 콘솔에서 메시지를 디자인하거나 Campaign 웹 UI에서 최신 **이메일 Designer**&#x200B;을(를) 사용하십시오.

+++ Campaign에서 전자 메일을 디자인하는 우수 사례는 무엇입니까?

주요 지침: 모바일 반응형 디자인 확인, 인라인 CSS와 함께 HTML 4.0/XHTML 호환 코드 사용, 대체 텍스트로 이미지 최적화(100KB 미만), 개인화 병합 필드 사용, 보내기 전에 이메일 클라이언트 간 테스트, 일반 텍스트 버전 포함. 최적의 전달성을 위해 500KB 미만의 총 이메일 크기를 목표로 합니다.

**관련 항목:**

[전자 메일 디자인 가이드](../send/email.md) | [게재 모범 사례](delivery-best-practices.md)

+++

+++ 게재 템플릿이란 무엇입니까?

게재 템플릿은 여러 캠페인에서 재사용할 모든 설정 및 매개 변수를 저장하는 사전 구성된 게재입니다. 템플릿에는 타겟 규칙, 콘텐츠 디자인, 개인화, 기술 설정(발신자, 회신) 및 유형화 규칙이 포함됩니다. 한 번 만든 다음 재사용하여 일관성을 유지하고 캠페인 생성 속도를 높일 수 있습니다.

[게재 템플릿 만들기](../send/create-templates.md) 방법을 알아봅니다.

+++

+++ Campaign에서 전자 메일을 만들기 위해 기존 HTML을 쉽게 가져올 수 있습니까?

예. 직접 복사/붙여넣기를 통해 콘텐츠 편집기에 HTML 콘텐츠를 가져오거나, 컴퓨터에서 파일을 업로드하거나, URL에서 로드합니다. HTML에서 인라인 CSS와 함께 이메일 호환 코드(HTML 4.0/XHTML)를 사용하고 공용 서버에서 이미지를 호스팅하는지 확인하십시오. Campaign은 가져온 HTML에 개인화 및 추적을 자동으로 추가합니다.

**팁:** 이메일 디자인 환경을 최적화하려면 Campaign 웹 UI에서 원시 Designer을 가져오는 대신 최신 드래그 앤 드롭 기능과 기본 제공 반응형 템플릿을 제공하는 **이메일 HTML**&#x200B;을(를) 사용하십시오.

[HTML 콘텐츠 가져오기](../send/defining-the-email-content.md) 방법 알아보기

+++

+++ Campaign에서 구독 기반 뉴스레터를 만들려면 어떻게 해야 합니까?

예. Campaign의 정보 서비스를 사용하여 뉴스레터 구독을 관리합니다. 주요 기능에는 자동 옵트인/옵트아웃 처리, 구독 추적, 규정 준수 관리(GDPR, CAN-SPAM), 다중 뉴스레터 지원, 가입 양식을 위한 웹 통합 및 구독자에 대한 타겟팅 게재가 포함됩니다.

[구독을 관리](../start/subscriptions.md)하는 방법 알아보기

+++

+++ 메시지를 개인화하려면 어떻게 해야 합니까?

Campaign은 수신자 데이터, 동작 및 환경 설정을 기반으로 관련성 있고 타깃팅된 메시지를 만들 수 있는 개인화 기능을 제공합니다.

**Personalization 옵션:**

* **개인화 필드** - 수신자 데이터 삽입(예: `"Hello {{firstName}}")`)
* **개인화 블록** - 미리 정의된 콘텐츠 블록 또는 사용자 지정 콘텐츠 블록 사용
* **조건부 콘텐츠** - 수신자 기준에 따라 다른 콘텐츠 표시
* **동작 데이터** - 검색 기록, 구매 패턴 또는 참여 지표 활용

보내기 전에 개인화를 테스트하여 병합 필드 및 조건부 논리가 올바르게 작동하는지 확인하십시오.

**관련 항목:**

[Personalization 안내서](../send/personalize.md) | [개인화 필드](../send/personalization-fields.md) | [조건부 콘텐츠](../send/conditions.md)

+++

+++ 이메일 제목 줄을 개인화하려면 어떻게 해야 합니까?

개인화된 제목 줄은 열람률을 크게 증가시킵니다. Campaign을 사용하면 수신자 데이터를 동적으로 삽입하고, 조건부 논리를 적용하고, 변형을 테스트하여 참여를 최적화할 수 있습니다.

**Personalization 기법:**

* **기본 필드** - 이름, 성, 위치: `"<%@ firstName %>, exclusive offer for you"` 삽입
* **조건부 콘텐츠** - 세그먼트별로 다른 주제: `"<% if (recipient.gender == 'F') { %>Special offer just for you<% } else { %>Exclusive deal inside<% } %>"`
* **동적 데이터** - 구매 내역, 충성도 포인트 또는 계정 정보 포함
* **이모티콘** - 시각적 호소력 추가(먼저 전자 메일 클라이언트 간 테스트)

**모범 사례:** 50자 미만으로 유지하고, 전송하기 전에 개인화 토큰을 테스트하고, A/B 테스트를 사용하여 최적화하고, 스팸 트리거 단어를 피하고, 가치 제안 또는 긴급성을 포함하십시오.

**관련 항목:**

[개인화 필드](../send/personalization-fields.md) | [조건부 콘텐츠](../send/conditions.md)

+++

+++ 다국어 메시지를 보낼 수 있습니까?

예. Campaign v8은 다국어 기능을 제공하며 **Campaign 웹 UI**&#x200B;는 가장 쉬운 접근 방식을 제공합니다. 웹 UI는 언어 변형이 포함된 기본 다국어 게재를 제공합니다. 언어 변형을 게재에 추가하면 Campaign에서 수신자의 선호 언어를 기반으로 적절한 버전을 자동으로 전송합니다. 이메일, 푸시 알림, SMS 및 트랜잭션 메시지에 사용할 수 있습니다.

주요 기능: 자동 콘텐츠 복제, 자동 언어 기반 전송, 기본 언어 대체 및 간편한 변형 관리.

또한 클라이언트 콘솔은 조건부 콘텐츠 및 워크플로를 사용하여 다국어 콘텐츠를 지원하지만 더 많은 수동 구성이 필요합니다.

**관련 항목:**

[다국어 게재(웹 UI)](https://experienceleague.adobe.com/en/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [조건부 콘텐츠(클라이언트 콘솔)](../send/conditions.md)

+++

+++ Webform을 현지화할 수 있습니까?

예. Campaign 웹 애플리케이션은 다국어 현지화 기능을 지원합니다. 수신자 프로필 또는 브라우저 설정을 기반으로 자동 언어 감지를 사용하여 모든 양식 요소(레이블, 버튼, 메시지, 오류 텍스트)에 대한 번역을 정의합니다. 단일 웹 애플리케이션 내에서 여러 언어 버전이 지원되며 필요한 경우 기본 언어로 대체됩니다.

[웹 응용 프로그램 로컬라이제이션에 대해 자세히 알아보기](../dev/webapps.md)

+++

+++ 이메일에 AI 기반 콘텐츠를 사용할 수 있습니까?

예, 하지만 **Campaign 웹 UI를 통해서만**&#x200B;됩니다. Microsoft Azure OpenAI 및 Adobe Firefly에서 제공하는 AI Assistant는 이메일, SMS 및 푸시 알림에서 전문적이고 브랜드 일관적인 콘텐츠를 만드는 데 도움이 됩니다.

**주요 기능:**

* 텍스트(이메일 사본, 제목 줄, SMS/푸시 콘텐츠) 및 브랜드 이미지 생성
* 다양한 대상자에 대해 최적화된 콘텐츠 변형 만들기
* 콘텐츠 세분화(정교함, 요약, 구문 변경, 간소화)
* 브랜드 자산을 업로드하고 브랜드 정렬 점수 받기
* 기존 콘텐츠를 참조로 사용하고 스타일 참조 이미지 업로드

**참고:** AI 도우미는 Campaign 웹 UI에서만 사용할 수 있으며 현재 영어만 지원합니다. 사용자는 적절한 권한이 필요하며 사용자 계약에 동의해야 합니다.

**관련 항목:**

[AI Assistant 개요](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [AI Assistant 사용 사례](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [브랜드 정렬](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## 메시지 테스트 및 보내기 {#send}

성공적인 캠페인 전달을 위해 마케팅 메시지를 테스트, 유효성 검사, 전송 및 추적하기 위한 모범 사례에 대해 알아봅니다.

+++ 이메일 게재 기능을 구성하는 방법

모든 발신자의 마케팅 프로그램 성공에 중요한 구성 요소인 이메일 게재 기능의 특징은 기준과 규칙이 계속 변한다는 것입니다. 이 디지털 세상을 효과적으로 탐색하려면 주요 전달성 트렌드를 고려하여 이메일 전략을 정기적으로 조정함으로써 대상자에게 가장 효과적으로 도달해야 합니다.

[게재 가능성 모범 사례](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=ko){target="_blank"}에 대해 알아보려면 이 안내서를 참조하세요.

[이 안내서에서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=ko){target="_blank"} Campaign의 전달성을 구현하는 방법을 알아보십시오.

**관련 항목:**

[게재 기능 시작](../send/about-deliverability.md) | [메시지 콘텐츠 제어](../send/control-message-content.md) | [게재 기능 모니터링](../send/monitoring-deliverability.md) | [SpamAssassin](../send/spamassassin.md)

+++

+++ 게재가 오류 없이 전송되도록 하려면 어떻게 해야 합니까?

**보내기 전:** 게재 분석을 실행하고, 테스트 증명을 보내고, 경고를 검토하고, 대상 수를 확인합니다.

**전송 중/전송 후:** 게재 대시보드(전송, 게재, 반송, 오류)를 모니터링하고, 게재 로그를 확인하고, 성공/바운스 비율을 추적하고, 격리된 주소를 검토합니다.

**모범 사례:** 경고를 설정하고 큰 볼륨에 웨이브를 사용하고, 작은 볼륨부터 테스트하고, 정기적으로 받는 사람 데이터베이스를 정리하고, 보낸 사람의 신뢰도를 모니터링합니다.

**관련 항목:**

[게재 추적 및 모니터링](../send/tracking.md) | [게재 모범 사례](delivery-best-practices.md)

+++

+++ 게재 분석이란 무엇입니까?

게재 분석은 보내기 전에 Campaign이 실행되는 유효성 검사 단계입니다. 대상 모집단을 계산하고, 콘텐츠를 확인하고, 오류를 확인하고, 유형화 규칙을 적용하고, 게재 볼륨을 예측합니다.

Campaign은 경고 및 오류를 표시하는 로그를 생성합니다. 오류는 전달을 차단하며 수정해야 합니다. 경고는 도움이 됩니다. 보내기 전에 항상 분석 로그를 검토하십시오.

자세한 내용은 [게재 분석 안내서](../send/delivery-analysis.md)를 참조하세요.

+++

+++ 증명을 만들어야 하는 이유는 무엇입니까?

증명은 기본 대상자에게 보내기 전에 게재를 확인하는 테스트 메시지입니다. 증명을 사용하여 개인화를 확인하고, 이메일 클라이언트 간에 콘텐츠 렌더링을 테스트하고, 링크 및 추적 작업을 확인하고, 이미지 및 첨부 파일을 확인하고, 모바일 응답성을 확인합니다.

증명을 사용하면 수천 명의 수신자에게 도달하기 전에 오류를 포착하고, 관련자 승인을 활성화하고, 받은 편지함 배치를 테스트할 수 있습니다. 여러 이메일 클라이언트 및 장치에 증명을 보내고, 프로덕션이 전송되기 전에 항상 승인을 받습니다.

[증명 및 미리 보기 가이드](../send/preview-and-proof.md)에서 자세히 알아보기

+++

+++ Adobe Campaign에서 시드 주소를 사용하는 방법

시드 주소는 대상 기준과 일치하지 않고 테스트, 품질 보증 및 모니터링을 위해 모든 게재에 자동으로 추가되는 특수 수신자입니다. 지속적인 모니터링, 받은 편지함 배치 테스트, DM 유효성 검사 및 관련자 가시성에 유용합니다.

**증명과의 주요 차이점:**

* **시드 주소** - 프로덕션 게재에 자동으로 추가되며 전송 볼륨에 계산됩니다.
* **증명** - 프로덕션 전에 테스트가 전송되고, 볼륨에 포함되지 않으며, 유효성 검사에 사용됩니다.

**[!UICONTROL Resources > Campaign management > Seed addresses]**&#x200B;의 시드 주소를 관리합니다. 게재 지표에 영향을 주지 않도록 목록을 작게 유지합니다.

[시드 주소 가이드](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html){target="_blank"}에서 자세히 알아보기

+++

+++ 메시지를 보내기 전에 승인 프로세스를 설정하려면 어떻게 해야 합니까?

Campaign은 메시지를 보내기 전에 품질 기준을 충족하는 승인 워크플로우를 제공합니다. 캠페인 또는 게재 수준에서 콘텐츠, 타겟, 추출(DM) 및 예산에 대한 승인을 구성합니다.

**설치:**

**[!UICONTROL Administration > Access management > Operator groups]**&#x200B;에서 연산자 그룹을 만든 다음 캠페인 또는 게재 속성에서 승인 그룹을 할당하십시오. Campaign은 변경 사항을 승인, 거부 또는 요청할 수 있는 검토자에게 알림 이메일을 보냅니다.

**독립 실행형 게재의 경우(캠페인에 포함되지 않음):**

**증명을 승인 프로세스로 사용**. 확인을 위해 승인 그룹에 증명을 보내고, 관련자가 최신 버전을 검토하도록 변경한 후 항상 새 증명을 보냅니다.

**관련 항목:**

[게재 유효성 검사](../send/preview-and-proof.md) | [캠페인 승인](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=ko){target="_blank"}

+++

+++ 게재에 대해 A/B 테스트를 실행할 수 있습니까?

예! Campaign을 사용하면 A/B 테스트(분할 테스트라고도 함)를 실행하여 여러 변형의 성능을 비교하여 제목란, 콘텐츠, 발신자 이름, 전송 시간 등을 최적화할 수 있습니다.

**테스트할 수 있는 사항:**

* **제목 줄** - 다른 제목 간의 열람률을 비교합니다.
* **콘텐츠 변형** - 다른 레이아웃, 클릭 유도 문안 또는 이미지 테스트
* **보낸 사람 정보** - 보낸 사람 이름 또는 주소 영향 테스트
* **전송 시간** - 최적의 배달 기간을 식별합니다.
* **Personalization 전략** - 개인화된 컨텐츠와 일반 컨텐츠 비교

**작동 방식:**

1. 게재 만들기 및 테스트 변형 정의(최대 3개)
2. 대상을 분할합니다(일반적으로 테스트 세그먼트의 경우 10~20%)
3. Campaign은 테스트 세그먼트에 변형을 보내고 성과를 추적합니다.
4. 채택 변형은 나머지 대상자에게 자동으로 전송됩니다(또는 수동으로 채택)

**Campaign 웹 UI와 클라이언트 콘솔을 모두 사용할 수 있습니다.** 웹 UI는 시각적 비교를 통해 보다 간단한 설정을 제공합니다.

**관련 항목:**

[게재 분석](../send/delivery-analysis.md) | [게재 보내기 및 추적](../send/send.md)

+++

+++ 유형화 규칙이란 무엇입니까?

유형화 규칙은 메시지 보내기의 유효성을 검사하고 최적화하기 위해 게재 분석 중에 적용되는 자동화된 비즈니스 논리입니다. 마케팅 정책 준수를 보장하고, 전달성을 보호하며, 고객 피로도를 방지합니다.

**기본 규칙 유형:**

* **필터링 규칙** - 수신자 제외(차단 목록에 추가된, 구독 취소, 격리됨)
* **압력 규칙** - 받는 사람이 너무 많으면 메시지 빈도를 제어합니다.
* **용량 규칙** - 처리 용량 또는 ISP 제한에 대한 메시지 볼륨 제한
* **제어 규칙** - 메시지 유효성 확인(제목 줄, 구독 취소 링크, 보낸 사람 형식)

규칙은 유형화로 그룹화되고 게재 분석 중에 적용됩니다. Campaign은 규칙에 따라 수신자를 제외하거나, 게재를 차단하거나, 경고를 생성할 수 있습니다.

자세한 내용은 [유형화 규칙 안내서](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=ko){target="_blank"}를 참조하세요.

+++

+++ 전자 메일을 웨이브로 보내려면 어떻게 해야 합니까?

예. 웨이브 전송은 예약된 간격으로 전송된 여러 배치로 게재를 분할합니다. 이는 대량 캠페인이 서버 로드 밸런스를 조정하고, ISP 제한을 방지하고, 새 IP를 사용하여 보낸 사람의 신뢰도를 높이고, 예약된 일괄 처리 사이에서 옵트아웃/바운스를 관리하는 데 필수적입니다.

**구성:**

게재 속성에서 웨이브 전송을 활성화하고 웨이브 수(또는 배치 크기), 웨이브 간 간격 및 웨이브 분포(선형 또는 사용자 지정 백분율)를 정의합니다. Campaign은 자동으로 대상 모집단을 분할하고 각 웨이브를 일정에 따라 전송합니다.

대규모 캠페인에 웨이브를 사용하고, 계속하기 전에 첫 번째 웨이브 성능을 모니터링하고, 웨이브 간 충분한 시간을 사용하여 바운스 및 옵트아웃을 처리할 수 있습니다.

[웨이브 전송을 구성](../send/configure-and-send.md#sending-using-multiple-waves)하는 방법에 대해 알아봅니다.

+++

+++ 게재를 예약하는 방법

Campaign을 사용하면 향후 전송을 위해 게재를 예약하여 전송 시간을 최적화하고 캠페인을 조정할 수 있습니다.

**예약 옵션:**

* **게재 속성** - 즉시 보내거나, 특정 날짜/시간에 대해 예약하거나, 시간/일별로 연기합니다.
* **캠페인 수준** - 캠페인 내의 모든 게재를 조정합니다.
* **워크플로우 스케줄러 활동** - 반복 게재, 복잡한 패턴 및 이벤트 트리거 캠페인의 경우

Campaign은 또한 연락 날짜 최적화(수신자당 가장 적합한 전송 시간)와 시간대 적응(모든 수신자에 대해 동일한 현지 시간)을 지원합니다.

[게재 예약 전송](../send/configure-and-send.md#schedule-delivery-sending)하는 방법 알아보기

+++

+++ 전자 메일에 첨부 파일을 추가할 수 있습니까?

예. Campaign은 정적 첨부 파일(모든 수신자에 대해 동일한 파일) 및 개인화된 첨부 파일(프로필 데이터에 따라 수신자마다 다른 파일)을 지원합니다. 게재 속성의 **[!UICONTROL Attachments]** 섹션에 첨부 파일을 추가합니다.

**중요 고려 사항:**

* 최적의 전달성을 위해 첨부 파일을 1MB 미만으로 유지
* 첨부 파일이 스팸 필터를 트리거할 수 있습니다. 보내기 전에 철저히 테스트하십시오.
* 이메일 클라이언트(.exe, .zip, .js)에 의해 일반적으로 차단되는 파일 형식을 피하십시오.
* 대용량 파일의 경우 추적된 다운로드 링크를 대신 사용하는 것이 좋습니다.

프로덕션 전송 전에 안전한 파일 형식(PDF, JPEG, PNG, DOCX)을 사용하고 시드 주소로 테스트합니다.

[전자 메일 첨부 파일 가이드](../send/email.md#attachments)에서 자세히 알아보기

+++

+++ 이메일 게재에서 추적된 링크를 구성하려면 어떻게 해야 합니까?

Campaign은 이메일의 모든 URL을 추적된 링크로 자동 변환하여 수신자 참여를 모니터링합니다. 게재의 **[!UICONTROL Tracking]** 섹션에 액세스하여 각 링크에 대한 추적 설정을 구성합니다.

**구성 옵션:**

* **추적 활성화/비활성화** - 링크당 추적 제어
* **링크 레이블** - 보고를 위한 수사적 이름을 추가합니다(예: &quot;Shop Now CTA&quot;).
* **링크 범주** - 집계된 분석을 위해 유형별 링크 그룹화
* **추적 형식** - 클릭 수, 열기 수 또는 둘 다 추적

Campaign은 콘텐츠 링크, 미러 페이지 링크, 구독 취소 링크를 추적하며, 이메일 열기를 위한 선택적 추적 픽셀을 포함할 수 있습니다. 의미 있는 레이블 및 범주를 사용하여 보고를 단순화하고 높은 성과를 보이는 콘텐츠를 신속하게 식별할 수 있습니다.

**관련 항목:**

[링크 추적 가이드](../send/tracking.md) | [추적 모범 사례](../send/send.md)

+++

+++ 게재 및 추적 로그는 어디에서 액세스할 수 있습니까?

각 게재 대시보드에서 직접 게재 및 추적 로그에 액세스합니다. 클라이언트 콘솔에서 하단의 **[!UICONTROL Delivery]** 탭을 클릭합니다. Campaign 웹 UI에서 **[!UICONTROL Logs]** 섹션으로 이동합니다.

**사용 가능한 로그:**

* **게재 로그** - 받는 사람 세부 정보 및 상태가 포함된 보낸 메시지(보냄, 보류, 실패)
* **추적 로그** - 타임스탬프를 사용한 수신자 상호 작용(열기, 클릭)
* **제외 로그** - 이유(격리, 유형화 규칙, 중복)가 있는 제외된 받는 사람
* **브로드캐스트 로그** - 다시 시도 및 오류를 포함한 전송 기록 완료

이러한 로그를 사용하여 게재 문제를 해결하고, 참여를 분석하고, 목록 위생 상태를 유지합니다.

**관련 항목:**

[게재 모니터링](../send/send.md) | [추적 가이드](../send/tracking.md)

+++

+++ 게재 보고서는 어디에서 얻을 수 있습니까?

Campaign은 게재 성과, 수신자 참여 및 캠페인 효과를 분석하는 포괄적인 기본 제공 보고서를 제공합니다. 모든 게재의 **[!UICONTROL Reports]** 탭, 캠페인 대시보드 또는 캠페인 간 분석을 위한 글로벌 **[!UICONTROL Reports]** 메뉴에서 보고서에 액세스합니다.

**주요 보고서 포함:**

* **게재 요약** - 통계, 열기, 클릭, 바운스 및 구독 취소 전송
* **핫 클릭** - 링크 성능의 시각적 히트맵
* **추적 표시기** - 클릭스루 비율 및 참여 지표
* **게재 불가** - 실패 이유가 있는 바운스 분석

보고서는 클라이언트 콘솔과 최신 시각화가 포함된 Campaign 웹 UI 모두에서 사용할 수 있습니다.

**관련 항목:**

[기본 제공 게재 보고서](../reporting/delivery-reports.md) | [캠페인 보고](../reporting/gs-reporting.md)

+++

+++ Adobe Campaign은 격리 주소를 어떻게 분류하고 관리합니까?

Campaign은 격리 목록을 자동으로 관리하여 보낸 사람의 신뢰도를 보호하고 전달성을 향상시킵니다. 격리된 주소는 유효성 검사를 완료하거나 격리에서 제거될 때까지 향후 게재에서 자동으로 제외됩니다.

**주소가 격리되는 이유:**

* **하드 바운스** - 영구 게재 실패(잘못된 전자 메일 주소, 도메인이 없음, 사서함 삭제)
* **소프트 바운스 임계값** - 오류 임계값을 초과하는 일시적인 오류가 반복됩니다(사서함 가득 참, 서버를 일시적으로 사용할 수 없음).
* **스팸 고객 불만** - 이메일을 스팸으로 표시하는 받는 사람
* **잘못된 주소** - 구문 오류가 있거나 유효성 검사에 실패한 주소
* **차단 목록에 추가된** - 제외를 옵트아웃하거나 요청한 수신자

**격리 작동 방식:**

Campaign은 각 주소에 대한 게재 오류를 추적합니다. 주소가 구성된 오류 임계값에 도달하면 자동으로 격리되고 분석 중에 이후의 모든 게재에서 제외됩니다. 하드 바운스(영구 실패)는 즉시 격리되는 반면 소프트 바운스는 격리되기 전에 여러 번의 실패가 필요합니다.

**격리된 주소 관리:**

**[!UICONTROL Administration > Campaign Management > Non deliverables Management]**&#x200B;의 격리 관리에 액세스하십시오. 격리된 주소를 보거나, 확인된 주소를 격리에서 수동으로 제거하거나, 자동 정리 규칙을 구성할 수 있습니다.

**팁:** 격리 목록을 정기적으로 모니터링합니다. 검역률이 높아지면 보낸 사람의 신뢰도에 영향을 미치기 전에 주의가 필요한 데이터 품질 문제를 알리는 경우가 많습니다.

**관련 항목:**

[격리 관리 가이드](../send/quarantines.md) | [바운스 관리](../send/delivery-failures.md)

+++

## 워크플로 {#workflows}

워크플로우를 사용하여 Adobe Campaign에서 프로세스를 자동화하고, 데이터를 관리하고, 복잡한 마케팅 캠페인을 오케스트레이션하는 방법을 살펴봅니다.

+++ 워크플로란?

Adobe Campaign에는 애플리케이션 서버의 여러 모듈에 걸쳐 전체 프로세스 및 작업을 오케스트레이션하는 워크플로가 포함되어 있습니다. 이 포괄적인 그래픽 환경을 사용하면 세분화, 캠페인 실행, 파일 처리, 인력 참여 등의 프로세스를 디자인할 수 있습니다. 워크플로 엔진은 이러한 프로세스를 실행하고 추적합니다.

예를 들어 워크플로에서 서버에서 파일을 다운로드하고 압축을 해제한 다음 Adobe Campaign 데이터베이스에 포함된 레코드를 가져올 수 있습니다.

워크플로에는 알림을 받거나 프로세스를 선택하고 승인할 수 있는 운영자가 한 명 이상 포함될 수도 있습니다. 이러한 방식으로 게재 작업을 만들고, 콘텐츠를 사용하여 작업하도록 한 명 이상의 운영자에게 작업을 할당하고, 대상을 지정하고, 게재를 시작하기 전에 교정쇄를 승인할 수 있습니다.

워크플로우에 대해 [자세히 알아보기](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=ko){target="_blank"}. 또한 [워크플로 모범 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=ko){target="_blank"}를 참조할 수 있습니다.

**관련 항목:**

[워크플로우 시작](../config/workflows.md) | [첫 번째 워크플로우 구축](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=ko){target="_blank"} | [워크플로우 사용 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [워크플로우 실행 모니터링](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

+++

+++ 워크플로 실행을 모니터링할 수 있습니까?

예. Campaign은 워크플로우 대시보드(실시간 상태 및 오류), 워크플로우 로그(자세한 실행 로그), 히트맵(활동 및 병목 현상 시각화), 감사 추적(수정 추적) 및 경고(오류 알림)와 같은 여러 모니터링 도구를 제공합니다.

모니터링하려면 워크플로우를 열고 **로그** 탭을 클릭합니다. 실패한 활동은 빨간색으로 표시됩니다.

**관련 항목:**

[워크플로우 실행 모니터링](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} | [워크플로우 모범 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}

+++

+++ 워크플로우를 만드는 주요 단계는 무엇입니까?

Campaign에서 마케팅 프로세스를 자동화하는 워크플로우 만들기:

1. **새 워크플로우 만들기** - **[!UICONTROL Profiles and Targets > Jobs > Targeting workflows]** 또는 **[!UICONTROL Administration > Production > Technical workflows]**(으)로 이동하여 **[!UICONTROL Create]** 클릭
1. **활동 추가** - 팔레트에서 활동을 끌어서 놓습니다(타깃팅, 흐름 제어, 작업 활동).
1. **활동 구성** - 각 활동을 두 번 클릭하여 매개 변수를 설정하고 논리를 정의합니다.
1. **활동 연결** - 활동을 전환과 연결하여 실행 흐름을 정의합니다.
1. **테스트 및 유효성 검사** - 워크플로 다이어그램을 사용하여 논리를 확인한 다음 작은 데이터 세트로 테스트합니다.
1. **실행** - 워크플로를 수동으로 시작하거나 자동 실행을 예약합니다.

일반적인 워크플로우 패턴: 데이터 가져오기, 대상 세그멘테이션, 게재 전송, 데이터 보강 및 크로스 채널 오케스트레이션.

**관련 항목:**

[워크플로우 구축](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=ko){target="_blank"} | [워크플로우 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"} | [워크플로우 모범 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"} | [워크플로우 사용 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ 반복 캠페인을 자동화하려면 어떻게 해야 합니까?

**스케줄러** 활동이 있는 워크플로우를 사용하여 일별, 주별, 월별 또는 사용자 지정 간격으로 정기적으로 실행되는 캠페인을 자동화합니다. 환영 이메일, 생일 메시지, 뉴스레터 전송, 포기한 장바구니 미리 알림 및 정기적인 보고에 적합합니다.

**설치 패턴:**

1. **스케줄러** - 빈도 정의(예: &quot;매주 월요일 오전 9시&quot;)
2. **쿼리** - 동적 기준이 있는 대상 선택
3. **데이터 보강**(선택 사항) - 개인화 데이터 추가
4. **게재** - 메시지 구성(이메일, SMS, 푸시)
5. **종료** - 워크플로우가 완료되고 다음 예약된 실행을 기다립니다.

**일반적인 자동화된 캠페인:**

* **시작 시리즈** - 새 구독자에게 온보딩 전자 메일을 보내는 일일 워크플로
* **생일 전자 메일** - 생일이 있는 수신자를 매일 확인하고 개인화된 메시지를 보냅니다.
* **다시 참여** - 윈백 오퍼가 있는 비활성 사용자의 매주 타깃팅
* **뉴스레터** - 예약된 주별 또는 월별 콘텐츠 배포
* **장바구니 포기** - 장바구니 포기를 식별하고 메시지를 보내는 시간별 워크플로

**팁:** 워크플로우에서 **반복 게재** 유형을 사용하여 각 실행을 개별적으로 추적하고 기록 보고를 유지 관리합니다.

**관련 항목:**

[스케줄러 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/scheduler.html){target="_blank"} | [반복 게재](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/sending-a-birthday-email.html){target="_blank"} | [Campaign 자동화](https://experienceleague.adobe.com/docs/campaign/automation/home.html?lang=ko){target="_blank"}

+++

+++ Campaign에서 데이터를 가져오려면 어떻게 해야 합니까?

**메서드:** 가져오기 마법사(1회 CSV/TXT), 워크플로우 기반 가져오기(변환을 통한 복잡한/반복 가져오기의 경우 **[!UICONTROL Data loading (file)]** 활동), REST API(프로그래밍 방식/실시간 동기화).

**모범 사례:** 작은 샘플로 테스트하고, UTF-8 인코딩을 사용하고, 필드를 올바르게 매핑하고, 중복 제거를 적용하고, 사용량이 적은 대용량 가져오기를 예약합니다.

**관련 항목:**

[가져오기 모범 사례](../start/import.md) | [데이터 로드 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"} | [가져오기 워크플로우 반복](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"}

+++

+++ 가져오는 동안 데이터 품질을 보장하려면 어떻게 해야 합니까?

성공적인 캠페인 실행을 위해서는 데이터 품질이 중요합니다. 데이터가 부실하면 게재 실패, 자원 낭비, 규정 준수 위험 등이 발생합니다. Campaign은 가져오기 프로세스 중에 데이터의 유효성을 검사하고, 정리하고, 보강하는 도구를 제공합니다.

**데이터 유효성 검사 단계:**

1. **가져오기 전 유효성 검사** - 파일 형식, 인코딩(UTF-8), 열 매핑, 필수 필드가 있는지 확인합니다.
2. **중복 제거** - **[!UICONTROL Deduplication]** 활동을 사용하여 전자 메일, ID 또는 사용자 지정 키로 중복을 식별하고 처리합니다.
3. **데이터 보강** - **[!UICONTROL Enrichment]** 활동을 사용하여 기존 Campaign 테이블에서 누락된 데이터를 추가합니다.
4. **형식 표준화** - JavaScript 또는 데이터 강화를 사용하여 전화 번호, 전자 메일 주소, 날짜, 국가 코드를 정규화합니다.
5. **유효성 검사 규칙** - 제약 조건 적용(올바른 전자 메일 형식, 필수 필드, 값 범위)

**일반적인 문제 및 수정 사항:**

* **문자 인코딩 오류**→ 항상 UTF-8 인코딩을 사용합니다.
* **날짜 형식이 일치하지 않음** → YYYY-MM-DD 형식으로 표준화됨
* **잘못된 이메일 주소** → 유효성 검사 규칙 또는 JavaScript을 사용하여 필터링합니다.
* **중복 레코드** → 업데이트 전에 항상 중복 제거 활동 포함
* **필수 필드 누락**→ 기본값을 설정하거나 불완전한 레코드를 거부합니다.

**모범 사례:** 모든 가져오기에 적용할 수 있는 표준 유효성 검사 및 정리 활동을 사용하여 재사용 가능한 &quot;데이터 품질&quot; 워크플로 템플릿을 만듭니다.

**관련 항목:**

[데이터 품질 가이드](../start/import.md) | [중복 제거 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html){target="_blank"} | [데이터 보강 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

+++

+++ Campaign의 일반적인 워크플로우 사용 사례는 무엇입니까?

워크플로우는 다음을 포함한 마케팅 프로세스를 자동화합니다.

**데이터 관리:** 데이터 가져오기/로드, 정리, 데이터 보강, 목록 관리\
**캠페인 자동화:** 환영 시리즈, 생일 캠페인, 재참여, 장바구니 포기\
**고급 타깃팅:** A/B 테스트, 동적 세분화, 잠재 고객 점수, 크로스 채널 오케스트레이션\
**모니터링:** 워크플로/게재 모니터링, 경고, 데이터베이스 유지 관리\
**통합:** CRM 동기화, API 통합, 이벤트 트리거 워크플로

**관련 항목:**

[워크플로우 사용 사례 라이브러리](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [워크플로우 구축](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=ko){target="_blank"} | [워크플로우 모범 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}

+++

+++ 워크플로우로 Campaign 데이터를 업데이트하려면 어떻게 해야 합니까?

대량 데이터베이스 작업에 **[!UICONTROL Update data]** 활동을 사용합니다. 삽입(새 레코드 추가), 업데이트(기존 업데이트 수정), 삽입 또는 업데이트(업데이트), 삭제(일치하는 레코드 제거).

**일반적인 사용:** 프로필 특성 업데이트, 외부 시스템과 동기화, 목록 멤버십 유지, 데이터 정리/중복 제거, 대량 상태 변경 적용.

정확한 일치를 위해 조정 키를 구성하고 업데이트 옵션을 선택합니다.

**관련 항목:**

[데이터 활동 업데이트](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"} | [데이터 관리 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ 데이터 관리 기능을 활용하려면 어떻게 해야 합니까?

데이터 관리 활동을 사용하면 데이터 보강(관련 테이블에서 데이터 추가), 분할(세그먼트 모집단), 중복 제거(중복 제거), 데이터 업데이트(대량 작업), 차원 변경(타깃팅 차원 전환), 교차/결합/제외(모집단 결합/필터링) 등 복잡한 작업을 수행할 수 있습니다.

**일반적인 사용:** 구매/동작 데이터를 보강하고, 대상자를 세그먼트화하고, 중복을 제거하고, 외부 데이터베이스(FDA)를 통합하고, 복잡한 다중 테이블 쿼리를 만듭니다.

**관련 항목:**

[데이터 관리 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"} | [데이터 보강 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

+++

+++ 개인화된 메시지 전송을 자동화할 수 있습니까?

예. 자동화된 워크플로우 구축: 쿼리(대상) → 데이터 보강(개인화 데이터 추가) → 분할(선택적 세그먼트) → 전달(개인화된 메시지) → 스케줄러(반복 실행)를 참조하십시오.

**Personalization:** 프로필 데이터, 동작 데이터, 조건부 콘텐츠, 동적 값을 사용합니다. 일반적인 시나리오: 생일 캠페인, 장바구니 포기, 충성도 프로그램, 답글, 이벤트 트리거 메시지.

**관련 항목:**

[Personalization 안내서](../send/personalize.md) | [워크플로우 사용 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=ko){target="_blank"}

+++

+++ 워크플로우로 하위 집합에서 대상을 분할하려면 어떻게 해야 합니까?

**[!UICONTROL Split]** 활동을 사용하여 모집단을 나눕니다. 필터링 조건(연령, 위치, VIP 상태), 백분율 분포(A/B 테스트), 레코드 제한(첫 번째 N, 상위 X%), 데이터 그룹화(값당 하나의 하위 집합).

**일반적인 사용:** A/B 테스트, 채널 환경 설정 라우팅, 점진적 롤아웃, 세그먼트별 메시징, 부하 분산. 각각의 서브세트는 상이한 프로세싱을 위해 별개의 천이로 흐른다.

**관련 항목:**

[활동 분할](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html){target="_blank"} | [A/B 테스트 가이드](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ 외부 파일에서 수신자 데이터를 업데이트하려면 어떻게 해야 합니까?

예. 워크플로우: 데이터 로드(파일) → 데이터 보강(선택 사항) → 조정(이메일/ID와 같은 일치 키) → 데이터 업데이트(일치하는 레코드 업데이트, 일치하는 레코드가 없는 경우 새로 삽입).

**일반적인 사용:** CRM에서 프로필 특성 업데이트, 구독 상태 새로 고침, 충성도 포인트 동기화, 옵트인/옵트아웃 환경 설정 업데이트.

**모범 사례:** 고유 식별자를 사용하고, 먼저 데이터의 유효성을 검사하고, 샘플로 테스트하고, 일반 업데이트를 예약합니다.

**관련 항목:**

[데이터 가져오기 안내서](../start/import.md) | [데이터 로드 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"} | [데이터 활동 업데이트](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"}

+++

+++ 신규 수신자를 식별하고 타겟팅하려면 어떻게 해야 합니까?

**[!UICONTROL Created date]** 필드를 쿼리하여 특정 일정 내에 추가된 수신자를 선택하십시오.

**자동화된 시작 워크플로:** 스케줄러(매일 실행) → 쿼리(새 수신자 선택) → 중복 제거(선택 사항) → 게재(환영 메시지) → 데이터 업데이트(&quot;환영&quot;으로 표시).

**고급:** 집계 함수를 사용하여 최근 추가 항목을 동적으로 식별하십시오.

**관련 항목:**

[쿼리 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"} | [집계 사용](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html){target="_blank"}

+++

+++ 워크플로우 활동은 어떻게 사용합니까?

네 가지 활동 범주:

**타깃팅:** 쿼리, 분할, 중복 제거, 데이터 보강, 교차, 결합, 제외(대상 정의/세분화)\
**흐름 제어:** 스케줄러, 대기, 테스트, 포크 및 연결, OR 연결, 이동(논리/타이밍 관리)\
**작업:** 배달, 데이터 업데이트, 데이터 로드/추출, JavaScript 코드(작업 수행)\
**이벤트:** 외부 신호, 파일 수집기, HTTP 전송(트리거에 반응)

팔레트에서 드래그하고 두 번 클릭하여 구성, 전환으로 연결.

**관련 항목:**

[타깃팅 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"} | [흐름 제어](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"} | [작업 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html){target="_blank"}

+++

+++ 워크플로우 모범 사례란 무엇입니까?

**디자인:** 이름 지우기, 레이블/설명 추가, 관련 활동 그룹화, 복잡한 프로세스를 더 작은 워크플로우로 나누기\
**성능:** 쿼리 크기 제한, 임시 테이블 사용, 사용량이 적은 일정 예약, 과도한 루프 방지\
**오류 처리:** 오류 경로 추가, 경고 구성, 샘플로 테스트, 로그 검토\
**유지 관리:** 사용되지 않는 워크플로 보관, 버전 제어, 복잡성 제한(&lt;20개 활동), 템플릿 사용\
**보안:** 권한 적용, 임시 데이터 정리, 하드 코딩되지 않은 변수 사용

**관련 항목:**

[워크플로우 모범 사례 가이드](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"} | [워크플로우 모니터링](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

+++

## 캠페인 설정 {#settings}

마케팅 작업을 최적화하기 위해 적절한 설정, 통합 및 구성으로 Campaign 인스턴스를 구성합니다.

+++ Campaign 인터페이스의 언어를 변경할 수 있습니까?

사용 중인 인터페이스에 따라 다릅니다. **클라이언트 콘솔** 언어는 고정되어 있지만 **Campaign 웹 UI**&#x200B;을(를) 통해 개별 사용자가 언어 기본 설정을 변경할 수 있습니다.

**클라이언트 콘솔(데스크톱 응용 프로그램):**

* 언어는 인스턴스가 생성될 때 설정되며 변경할 수 없습니다.
* 클라이언트 콘솔과 서버는 동일한 언어를 사용해야 합니다
* 각 Campaign 인스턴스는 단일 언어로 작동합니다
* 영어 설치의 경우 미국 영어 또는 영국 영어 중에서 선택할 수 있습니다(날짜 및 시간 형식이 다름)

**Campaign 웹 UI:**

* 사용자는 프로필 환경 설정을 통해 인터페이스 언어를 독립적으로 변경할 수 있습니다
* 날짜, 시간 및 숫자에 대한 로케일별 서식을 사용하여 여러 언어를 지원합니다
* 웹 UI 언어 환경 설정은 Campaign 서버 및 클라이언트 콘솔 언어와 독립적입니다


**관련 항목:**

[Campaign 웹 UI에서 언어 변경](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [Campaign 클라이언트 콘솔 시작](connect.md)

+++

+++ Campaign Campaign 컨트롤 패널은 무엇이며 어떻게 액세스할 수 있습니까?

Campaign Campaign 컨트롤 패널은 Campaign 관리자가 Campaign 인스턴스 전반에 대한 설정을 관리하고 사용을 모니터링하여 효율성을 높이는 데 도움이 되는 웹 기반 관리 인터페이스입니다. Adobe 지원에 문의하지 않고도 중요한 인스턴스 구성을 관리할 수 있는 셀프서비스 기능을 제공합니다.

**주요 기능:**

* **하위 도메인 관리** - 하위 도메인을 위임 및 관리하고 SSL 인증서를 모니터링합니다.
* **저장소 모니터링** - 데이터베이스 사용량을 추적하고 저장소 문제를 방지합니다.
* **SFTP 관리** - SFTP 저장소 모니터링, IP 허용 목록 관리 및 SSH 키
* **인스턴스 설정** - IP 허용 목록 구성, URL 권한 관리, 인스턴스 세부 사항 검토
* **활성 프로필 모니터링** - 권한에 대해 활성 프로필 사용 추적
* **성능 모니터링** - 데이터베이스 및 워크플로 성능 모니터링
* **전자 메일 게재 기능** - DMARC, BIMI 및 기타 인증 레코드 구성

**액세스 요구 사항:**

* **관리자 사용자만** - Campaign 컨트롤 패널은 관리자 권한이 있는 사용자로 제한됩니다.
* **Adobe IMS 인증** - Adobe ID과 함께 Adobe Experience Cloud을 통해 액세스
* **Campaign v8 관리 클라우드 서비스** - 호스팅된 인스턴스에만 사용할 수 있습니다.

**추가 리소스:**

[Campaign 컨트롤 패널 설명서](https://experienceleague.adobe.com/ko/docs/control-panel/using/control-panel-home){target="_blank"} | [Campaign 컨트롤 패널 자습서 비디오](https://experienceleague.adobe.com/en/docs/control-panel-learn/tutorials/control-panel-overview){target="_blank"}

+++

+++ 도메인 위임의 절차는 무엇입니까?

하위 도메인은 브랜드나 다양한 트래픽 유형(트랜잭션 메시지, 마케팅 정보 등)을 분리하는 데 사용할 수 있는 도메인의 개별 부분입니다.

>[!NOTE]
>
>Managed Cloud Services 사용자는 Adobe에 문의하여 하위 도메인을 Adobe에 위임할 수 있습니다.

+++

+++ Campaign 인스턴스에 추적 기능을 설정하려면 어떻게 해야 합니까?

Campaign v8은 수신자와 메시지의 상호 작용을 모니터링하는 포괄적인 추적을 제공합니다. 추적을 사용하려면 인스턴스와 메시지 설정을 올바르게 구성해야 합니다.

**추적할 수 있는 항목:**

* **전자 메일 열기** - 추적 픽셀(1x1 투명 이미지) 사용
* **링크 클릭** - 모든 URL이 추적된 링크로 자동 변환됨
* **구독 취소** - 옵트아웃 링크 추적
* **미러 페이지 보기** - 수신자가 웹 버전을 볼 때
* **사용자 지정 매개 변수** - 고급 분석을 위해 URL에 추적 데이터 추가

**주요 구성 단계:**

1. 인스턴스 설정에서 추적 서버 URL 구성(v8용 Adobe에서 관리)
2. 게재 속성에서 추적 활성화
3. 개별 링크 또는 모든 링크에 대한 자동 추적 설정
4. 추적 유효 기간 및 로그 유지 정의

**모범 사례:** 링크를 올바르게 작동하고 데이터가 캡처되는지 확인하기 위해 주 대상자에게 보내기 전에 항상 증명을 사용하여 추적을 테스트하십시오.

**관련 항목:**

[게재 추적 및 모니터링](../send/tracking.md) | [추적된 링크 구성](../send/tracked-links.md) | [추적 테스트](../send/testing-tracking.md)

+++

+++ 이메일 게재 기능을 구성하는 방법

이메일 전달성은 기술 구성, 콘텐츠 품질 및 보낸 사람의 신뢰도에 따라 다릅니다. Campaign v8은 받은 편지함 배치를 최적화하는 도구와 설정을 제공합니다.

**필수 구성 단계:**

* **도메인 인증** - 보내는 도메인을 확인하려면 SPF, DKIM 및 DMARC 레코드를 설정하십시오.
* **IP 준비 중** - 평판을 구축하기 위해 새 IP에 대한 전송 볼륨을 점차 늘립니다.
* **보낸 사람 구성** - 일관되고 인식할 수 있는 보낸 사람 주소와 이름을 사용합니다.
* **바운스 관리** - 하드 및 소프트 바운스를 자동으로 처리하도록 격리 규칙을 구성합니다.
* **피드백 루프** - 불만 처리를 설정하여 스팸 보고서를 관리합니다.

**콘텐츠 모범 사례:**

* SpamAssassin으로 이메일을 테스트하여 스팸 점수 확인
* 적절한 텍스트 대 이미지 비율 유지
* HTML과 함께 일반 텍스트 버전 포함
* 항상 구독 취소 링크 제공
* 스팸 트리거 단어 및 대문자화 방지

**모니터링:** Campaign의 게재 가능성 보고서를 사용하여 바운스 비율, 불만 비율 및 받은 편지함 배치를 추적합니다. Campaign v8의 경우 Adobe은 인프라 수준의 전달성 최적화를 제공합니다.

**관련 항목:**

[Campaign의 게재 기능 기본 정보](../send/about-deliverability.md) | [게재 기능 모범 사례 안내서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=ko){target="_blank"}

+++

+++ Campaign을 연결할 수 있는 외부 데이터베이스는 무엇입니까?

Campaign v8은 주요 엔터프라이즈 데이터베이스 시스템(클라우드 데이터베이스, 엔터프라이즈 데이터베이스, 데이터 웨어하우스, 빅 데이터 플랫폼)에 대한 FDA(Federated Data Access) 연결을 지원합니다.

지원되는 데이터베이스 버전 및 연결 요구 사항은 다양합니다. Campaign v8 버전에 대한 [호환성 매트릭스](compatibility-matrix.md)를 확인하여 특정 데이터베이스에 대한 지원을 확인하고 FDA 커넥터에 대한 올바른 라이선스를 확인하십시오.

[FDA 연결 구성](../connect/fda.md)을 참조하십시오.

+++

+++ Adobe Campaign을 CRM 시스템과 통합할 수 있습니까?

예. Campaign은 주요 CRM 시스템과의 양방향 동기화를 위한 기본 CRM 커넥터를 제공합니다. 연락처 데이터, 리드, 계정, 게재 로그, 추적 데이터 및 참여 지표를 동기화합니다. API를 통해 예약, 수동 및 실시간 동기화 모드를 지원합니다.

Campaign의 CRM 커넥터 도우미를 사용하여 필드를 매핑하고, 테이블을 선택하고, 동기화를 예약합니다. 지원되는 CRM 버전에 대해 [호환성 매트릭스](compatibility-matrix.md)를 확인하십시오.

**관련 항목:**

[CRM 커넥터 구성](../connect/crm.md) | [워크플로 CRM 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html){target="_blank"}

+++

+++ 클라이언트 콘솔 캐시를 지우려면 어떻게 합니까?

클라이언트 콘솔 캐시를 지우면 많은 일반적인 표시 및 기능 문제가 해결됩니다. 캐시는 때때로 손상되거나 오래된 로컬 구성 파일을 저장합니다.

**캐시를 지우는 시기:**

* 새 브랜딩 요소(로고, 색상)가 올바르게 표시되지 않음
* 예기치 않게 내보내기/가져오기 기능 실패
* 구성 변경 후 인터페이스 요소가 업데이트되지 않음
* 성능 문제 또는 콘솔 응답 속도 저하
* 새 클라이언트 콘솔 버전으로 업그레이드 후

**캐시를 지우는 단계:**

1. Campaign 클라이언트 콘솔 열기
2. **[!UICONTROL File]** 메뉴로 이동
3. **[!UICONTROL Clear the local cache...]** 선택
4. 메시지가 표시되면 작업을 확인합니다
5. 클라이언트 콘솔 다시 시작

[클라이언트 콘솔 설치 및 구성](connect.md)에서 자세히 알아보기

+++

+++ 사용자 인터페이스 설정을 구성할 수 있습니까?

예. Campaign 관리자는 조직 브랜딩에 맞게 사용자 인터페이스를 사용자 정의하고 사용자 경험을 최적화할 수 있습니다. 인스턴스 또는 사용자 수준에서 설정을 구성합니다.

**사용자 지정할 수 있는 항목:**

* **브랜딩** - 로고, 색상 및 시각적 ID 요소
* **기본 보기** - 홈 페이지 레이아웃, 폴더 구조 가시성
* **목록 구성** - 기본 열, 정렬 순서, 데이터 목록의 필터
* **탐색** - 사용 가능한 메뉴 항목 및 바로 가기
* **지역 설정** - 날짜/시간 형식, 숫자 형식, 시간대
* **알림** - 전자 메일 알림, 인앱 알림, 워크플로 알림

**구성 수준:**

* **인스턴스 전체** - 모든 사용자에게 적용(관리자 권한 필요)
* **사용자별** - 개별 환경 설정 및 개인 설정

**관련 항목:**

[UI 설정 구성](../config/ui-settings.md) | [사용자 권한](gs-permissions.md)

+++

+++ 사용자 정의 필드 및 테이블을 만들 수 있습니까?

예. Campaign의 유연한 데이터 모델을 사용하면 사용자 지정 필드로 기본 제공 스키마를 확장하고 특정 비즈니스 요구 사항을 충족하도록 완전히 새로운 테이블을 만들 수 있습니다.

**사용자 지정할 수 있는 항목:**

* **기존 테이블에 필드 추가** - 충성도 포인트, 사용자 지정 환경 설정, 외부 ID로 수신자 테이블 확장
* **새 사용자 지정 테이블 만들기** - 제품, 트랜잭션, 충성도 계층, 사용자 지정 엔터티 저장
* **관계 정의** - 사용자 지정 테이블을 기존 Campaign 테이블에 연결
* **양식 확장** - 사용자 정의 필드를 표시하고 편집하려면 UI를 업데이트하십시오.

**일반적인 사용 사례:**

* 추가 프로필 속성 저장(고객 라이프타임 값, 기본 스토어, VIP 상태)
* 사용자 지정 속성으로 제품 카탈로그 관리
* 사용자 지정 이벤트 및 상호 작용 추적
* 데이터 동기화를 위해 외부 시스템 ID 통합
* 산업별 데이터 모델 구축 (소매, 금융, 여행)

**관련 항목:**

[데이터 모델 확장](../dev/extend-schema.md) | [스키마 구조](../dev/schemas.md) | [데이터 모델 모범 사례](../dev/datamodel-best-practices.md)

+++

## 보고 {#reporting}

기본 제공 보고서, 사용자 지정 보고서 및 큐브와 같은 데이터 분석 도구를 포함한 Campaign의 보고 기능에 대한 통찰력을 얻으십시오.

+++ 새 보고서를 만들려면 어떻게 해야 합니까?

Campaign은 기본 제공 보고서, 설명 분석, 클라이언트 콘솔의 사용자 지정 보고서 및 큐브와 같은 여러 보고 옵션을 사용자의 요구 사항과 기술 전문 지식에 따라 제공합니다.

**보고 옵션:**

* **기본 제공 보고서** - **[!UICONTROL Reports]** 탭에서 액세스할 수 있는 바로 사용 가능한 게재, 캠페인 및 추적 보고서
* **설명 분석** - 마법사 기반 인터페이스를 사용하여 데이터에 대한 빠른 통계 보고서
* **사용자 지정 보고서** - 기술 사용자가 보고 편집기를 사용하여 작성한 고급 보고서
* **큐브** - 다차원 데이터 탐색 및 피벗 테이블 분석

**중요:** Campaign은 전문 비즈니스 인텔리전스 도구가 아니라 마케팅 작업 보고를 위해 설계되었습니다. 복잡한 분석 요구 사항에 대해서는 Adobe Analytics 또는 전용 BI 플랫폼과 통합하는 것을 고려하십시오.

**관련 항목:**

[보고 시작](../reporting/gs-reporting.md) | [Campaign 웹 UI 보고서](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

+++ 모집단에 대한 통계 보고서를 디자인하고 공유하려면 어떻게 해야 합니까?

Campaign의 설명 분석 도구를 사용하여 모든 모집단 데이터에 대한 통계 보고서를 신속하게 생성할 수 있습니다. 이 마법사 기반 기능을 사용하면 전문적인 기술 없이도 배포, 트렌드 및 패턴을 분석할 수 있습니다.

**분석할 수 있는 사항:**

* 수신자 인구 분포 및 세분화 분류
* 캠페인 성과 지표 및 응답률
* 프로필 속성(나이, 위치, 환경 설정) 분포
* 게재 통계 및 참여 패턴
* 사용자 정의 필드 값 및 데이터 품질 지표

**만드는 방법:** 목록 또는 쿼리 결과→ 선택합니다. **[!UICONTROL Actions > Analyze]** → 분석 유형(정성 또는 정량)을 마우스 오른쪽 단추→ 클릭하고 → 표시 옵션 구성 → 보고서 생성.

**공유:** 보고서를 Excel/PDF으로 내보내거나 적절한 권한으로 팀 액세스를 위해 **[!UICONTROL Reports]** 폴더에 저장합니다.

[설명 분석](../reporting/built-in-reports.md)에 대해 자세히 알아보기

+++

+++ 데이터에 대한 고급 보고서를 디자인하려면 어떻게 해야 합니까?

클라이언트 콘솔을 사용하여 복잡한 분석 기능을 갖춘 고급 사용자 지정 보고서를 만들 수 있습니다.

클라이언트 콘솔에서 다음을 수행할 수 있습니다.

* SQL 쿼리 및 사용자 지정 계산을 사용하여 복잡한 보고서 작성
* 차트, 테이블 및 피벗 테이블을 사용하여 다중 페이지 보고서 만들기
* 조건부 서식 및 다이내믹 콘텐츠 디자인
* 전체 Campaign 데이터 모델 및 외부 데이터베이스(FDA) 액세스

[사용자 지정 보고서를 만드는 방법(클라이언트 콘솔)](../reporting/custom-reports.md)

+++

+++ 큐브란 무엇이며 보고에 큐브를 사용하려면 어떻게 해야 합니까?

큐브는 비즈니스 사용자가 기술 없이도 피벗 테이블을 통해 Campaign 데이터를 탐색하고 분석할 수 있는 다차원 데이터 구조입니다. 이를 복잡한 보고를 간소화하는 사전 구성된 데이터 모델로 간주합니다. 이 보고 도구는 클라이언트 콘솔과 Campaign 웹 UI 모두에서 사용할 수 있습니다.

* 기술 사용자 는 차원 (시간, 지역, 채널) 및 측정값 (열기, 클릭 수, 매출)을 정의하는 큐브를 만들고 구성합니다.
* 비즈니스 사용자는 보고서를 만들 때 큐브를 선택하고 데이터를 탐색하기 위해 차원을 끌어서 놓습니다
* 데이터는 큐브 구성을 기반으로 자동으로 집계되고 계산됩니다
* 결과를 피벗 테이블, 차트 또는 Excel로 내보낼 수 있습니다

큐브를 사용하여 [데이터 탐색](../reporting/gs-cubes.md)하는 방법 알아보기

+++

+++ 온라인 설문 조사에 대한 응답으로 보고서를 만들 수 있습니까?

예! Campaign에는 온라인 설문 조사를 만들고 설문 조사 응답에 대한 기본 제공 보고서를 생성할 수 있는 설문 조사 모듈이 포함되어 있습니다.

**중요:** 설문 조사 관리는 Campaign v8 엔터프라이즈(FFDA) 배포에서 사용할 수 없습니다. [자세히 알아보기](../architecture/enterprise-deployment.md)

**설문 조사 기능:**

* 여러 페이지 및 질문 유형을 사용하여 온라인 설문 조사 만들기
* 데이터베이스 또는 로컬 변수에서 응답 수집
* 설문 조사 응답 실시간 추적 보기
* 설문 조사 응답에 대한 전용 보고서 생성(질문별 분류, 일반 통계)
* 추가 분석을 위해 설문 조사 응답을 Excel, PDF 또는 CSV로 내보내기
* 타겟팅 워크플로우에서 설문 조사 데이터를 사용하여 캠페인 개인화

**고급 분석:**

* **[!UICONTROL Responses]** 탭에서 설문 조사 응답에 액세스하고 데이터를 내보냅니다
* 워크플로우에서 **[!UICONTROL Survey responses]** 활동을 사용하여 답변을 기반으로 수신자를 타겟팅합니다.
* 세분화 및 개인화를 위해 설문 조사 데이터를 다른 Campaign 데이터와 결합
* 다차원 설문 조사 분석을 위한 사용자 지정 보고서 및 큐브 만들기

**관련 항목:**

[설문 조사 시작](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [설문 조사 보고서](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ 보고서에 대한 액세스 권한을 공유하려면 어떻게 해야 합니까?

Campaign에서 폴더 권한 및 명명된 권한을 통해 보고서 가시성을 제어합니다.

**액세스 제어 메서드:**

* **폴더 권한** - 사용자 그룹에 대한 적절한 액세스 권한이 있는 폴더에 보고서를 배치합니다.
* **명명된 권한** - 보고서를 보거나 만들거나 수정할 수 있는 권한을 할당합니다.
* **컨텍스트 표시** - 보고서 표시 위치 정의(보고서 폴더, 캠페인 탭, 게재 화면)

**설정:** 보고서를 특정 폴더에 저장 → 연산자 그룹의 폴더 액세스를 구성 → 보고서 속성 및 표시 컨텍스트를 정의합니다.

**관련 항목:**

[사용자 지정 보고서](../reporting/custom-reports.md) | [사용자 권한](gs-permissions.md)

+++

+++ 보고서를 다른 형식으로 내보낼 수 있습니까?

예. Campaign은 클라이언트 콘솔과 웹 UI 보고서 모두에 대해 여러 내보내기 형식을 지원하므로 관련자와 쉽게 공유하고 다른 도구와의 통합을 수행할 수 있습니다.

**사용 가능한 내보내기 형식:**

* **Excel(.xlsx)** - 데이터 조작, 추가 분석 및 피벗 테이블에 최적
* **PDF** - 프레젠테이션, 경영진 요약 및 인쇄된 보고서에 이상적
* **CSV** - 다른 시스템 및 BI 도구로의 데이터 가져오기에 적합합니다.
* **OpenDocument(.ods)** - 오픈 소스 스프레드시트 형식
* **XML** - 시스템 통합 및 자동 처리용

**내보내는 방법:**

* **클라이언트 콘솔:** 보고서 열기 → **[!UICONTROL Export]** 버튼→ 클릭하여 형식 선택 → 파일 저장
* **웹 UI:** 대시보드→ 열고 내보내기 아이콘→ 클릭하여 포맷 → 다운로드
* **자동화된 내보내기:** 내보내기 활동이 있는 워크플로우를 사용하여 일반 내보내기를 예약합니다.

**모범 사례:**

* 관련자 분석 및 주석이 필요한 보고서에 Excel 사용
* 경영진에게 보내거나 규정 준수를 위해 보관하는 정적 보고서에 PDF 사용
* 데이터 웨어하우스 또는 외부 분석 도구와의 통합에 CSV 사용
* 내보낸 보고서를 테스트하여 형식 지정 및 데이터 정확도 확인

**관련 항목:**

[사용자 지정 보고서](../reporting/custom-reports.md) | [Campaign 웹 UI 보고서](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

## 개발자 {#developers}

데이터 모델 세부 정보, 스키마, API 및 사용자 지정 기능을 포함하여 개발자를 위한 기술 정보에 액세스합니다.

+++ Campaign 데이터 모델은 무엇입니까?

Campaign의 데이터 모델은 비즈니스 요구 사항에 맞게 확장할 수 있는 기본 제공 테이블(수신자, 게재, 캠페인)로 구성된 스키마 기반 관계형 데이터베이스 구조입니다.

**주요 개념:** 스키마(XML 정의), 기본 제공 테이블, 링크(관계), 열거형(값 목록), 확장(사용자 지정 필드/테이블).

**기본 스키마:** 받는 사람(`nms:recipient`), 게재(`nms:delivery`), 워크플로우(`xtk:workflow`), 캠페인(`nms:operation`), 추적 로그.

워크플로우, 쿼리, 스키마 확장 및 통합에는 데이터 모델을 이해하는 것이 필수적입니다.

**관련 항목:**

[Campaign 데이터 모델](../dev/datamodel.md) | [데이터 모델 모범 사례](../dev/datamodel-best-practices.md)

+++

+++ Campaign 스키마로 작업하는 방법

스키마는 테이블 구조, 필드 속성, 관계, 인덱스 및 액세스 제어를 지정하여 Campaign의 데이터 구조를 XML 형식으로 정의합니다.

**스키마 작업:**

* **을(를) 통한**&#x200B;보기:**[!UICONTROL Administration > Configuration > Data schemas]** 액세스
* **확장:** 확장 스키마(예: `cus:recipient`)를 만들어 핵심 스키마를 수정하지 않고 사용자 지정 필드를 추가합니다.
* **만들기:** 비즈니스별 데이터를 위한 새 테이블을 만듭니다.
* **업데이트:** 변경 내용을 **[!UICONTROL Tools > Advanced > Update database structure]**&#x200B;을(를) 통해 적용

**일반적인 사용:** 받는 사람 테이블에 사용자 지정 필드를 추가하고, 사용자 지정 테이블을 만들고, 관계를 정의하고, 비즈니스별 모델을 구현합니다.

**중요:** 기본 제공 스키마를 직접 수정하지 마십시오. 업그레이드 호환성을 위해서는 항상 확장 스키마를 사용하십시오.

**관련 항목:**

[스키마 시작](../dev/schemas.md) | [스키마 확장](../dev/extend-schema.md)

+++

+++ 사용자 지정 수신자 테이블을 사용하는 방법

표준 수신자 테이블 대신 B2B 계정, 별도의 가입자 데이터, 외부 시스템 또는 다중 브랜드 아키텍처를 타겟팅할 때 사용자 지정 수신자 테이블을 사용합니다.

**구현:** 필수 필드(전자 메일, 기본 키, 제외)를 사용하여 사용자 지정 스키마→ 만들고 대상 매핑→ 구성하고 게재 템플릿 업데이트 → 워크플로/쿼리 조정

**주요 고려 사항:** 필수 게재 필드를 포함해야 하며 워크플로/양식은 프로덕션 마이그레이션 전에 적응하고 테스트해야 합니다.

**모범 사례:** 먼저 표준 받는 사람 테이블을 확장하세요. 복잡성이 추가되어 실제로 필요한 경우에만 사용자 지정 테이블을 사용하십시오.

**관련 항목:**

[사용자 지정 받는 사람 테이블](../dev/custom-recipient.md) | [대상 매핑](../audiences/target-mappings.md)

+++

+++ Campaign에서 쿼리를 정의하는 모범 사례는 무엇입니까?

Campaign의 쿼리 편집기는 워크플로우 활동, 게재 타기팅, 목록, 보고서 및 필터에 사용되는 데이터베이스 쿼리를 SQL 없이 시각적으로 작성합니다.

**모범 사례:**

* 단순하게 시작 - 점진적으로 구축, 각 단계 테스트
* 필터링 차원 사용 - 테이블 관계 활용
* 성능 최적화 - 쿼리된 필드 색인, 복잡한 계산 방지
* 일관성을 위해 사전 정의된 필터 재사용
* 먼저 작은 검체로 테스트합니다.
* 복잡한 쿼리 문서

**일반적인 패턴:** 대상 게재를 열고, 비활성 연락처를 찾고, 비헤이비어로 세그먼트화하고, 이전 받는 사람을 제외합니다.

임시 탐색을 위한 **액세스:** **[!UICONTROL Tools > Generic query editor]**.

**관련 항목:**

[쿼리 편집기](../start/query-editor.md) | [쿼리 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}

+++

+++ 데이터 패키지를 가져오려면 어떻게 해야 합니까?

클라이언트 콘솔에서 **[!UICONTROL Tools > Advanced > Import package]**&#x200B;을(를) 통해 패키지를 가져옵니다. 패키지에는 인스턴스 간에 배포할 Campaign 구성(스키마, 워크플로우, 유형화)과 데이터가 포함되어 있습니다.

**패키지 유형:** 사용자 패키지(사용자 지정 구성), 플랫폼 패키지(Adobe 제공), 데이터 패키지(실제 데이터).

**모범 사례:** 먼저 개발에서 테스트하고, 가져오기 전에 백업하고, 동일한/이전 버전에서 내보냅니다.

[데이터 패키지 작업](../dev/packages.md)에서 자세히 알아보기

+++

+++ Campaign v8 API 목록은 어디에서 찾을 수 있습니까?

Campaign v8은 SOAP API(클라이언트 콘솔 작업), REST API(최신 통합) 및 JavaScript API(워크플로우 스크립팅)를 제공합니다.

**일반적인 사용:** CRM/ERP와 통합, 캠페인 자동화, 데이터 동기화, 모니터링 솔루션 빌드, 외부 인터페이스 만들기.

**액세스:** [Campaign v8 API 설명서](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=ko){target="_blank"}

+++


+++ API에서 워크플로우를 모니터링하려면 어떻게 합니까?

Campaign API를 사용하면 워크플로우를 프로그래밍 방식으로 제어할 수 있습니다(시작, 일시 중지/다시 시작, 중지, 쿼리 상태, 로그 검색, 활동 진행 상황 모니터링).

**API 끝점:** `POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

**명령:** `{"method":"start"}`, `{"method":"pause"}`, `{"method":"resume"}`, `{"method":"stop"}`

**사용 사례:** 모니터링 대시보드를 빌드하고, 자동화된 알림을 구현하고, 외부 스케줄러에서 오케스트레이션하고, 인스턴스 간에 종속성을 만들고, 사용자 지정 보고서를 생성합니다.

**모범 사례:** 포괄적인 거버넌스를 위해 API 모니터링과 감사 추적을 결합합니다.

[API를 통해 워크플로우 제어](../dev/api/controlling-a-workflow.md)를 참조하십시오.

+++

+++ 데이터베이스 구조를 업데이트하려면 어떻게 해야 합니까?

스키마를 수정한 후(필드 추가, 테이블 만들기, 데이터 형식 변경) **[!UICONTROL Tools > Advanced > Update database structure]**&#x200B;을(를) 통해 실제 데이터베이스 구조를 업데이트하여 변경 내용을 적용하십시오.

**필요한 경우:** 필드 추가, 테이블 만들기/확장, 필드 속성 수정, 링크 추가/제거, 인덱스 만들기.

**중요:** 먼저 백업, 개발 테스트, 대규모 변경 사항에 대한 다운타임 계획, Adobe 지원(Managed Cloud Services)과 조정, 일부 변경 사항은 데이터 손실을 초래할 수 있습니다.


**관련 항목:**

[데이터베이스 구조 업데이트](../dev/update-database-structure.md) | [스키마 확장](../dev/extend-schema.md)

+++

## 개인 정보 {#privacy}

Adobe Campaign이 GDPR 및 CCPA와 같은 개인 정보 보호 규정을 준수하고 데이터 주체 요청을 관리하는 데 어떻게 도움이 되는지 이해합니다.

+++ Campaign의 주요 개인 정보 보호 개념은 무엇입니까?

Campaign은 데이터 주체 권한, 동의 및 데이터 보존을 관리하는 도구를 통해 개인 정보 보호 규정(GDPR, CCPA, PDPA, LGPD)을 준수하도록 도와줍니다. 주요 개념으로는 개인정보 보호 규정, 개인 데이터 식별, 데이터 주체 권한(액세스, 삭제, 이동성), 동의 관리 및 데이터 보존 정책 등이 있습니다.

데이터 제어자는 데이터 주체 요청을 처리하고, 동의 레코드를 유지 관리하며, 투명한 데이터 사용을 보장합니다.

[개인 정보 관리](../start/privacy.md)에 대해 자세히 알아보기

+++

+++ Campaign에서 개인 정보 보호 규정 준수를 보장하려면 어떻게 해야 합니까?

Campaign은 개인 정보 보호 규정을 준수하기 위한 도구를 제공하지만 법적 책임은 사용자에게 있습니다. 개인 정보 보호 프로그램을 위해 법률 고문과 협력하십시오.

**필수 작업:**

* 데이터 주제 요청(액세스, 삭제) 처리를 위한 프로세스 수립
* 타임스탬프 및 범위 추적을 사용하여 동의 관리 구현
* 모든 마케팅 이메일에 구독 취소 링크 포함
* 데이터 소스 감사 및 사용하지 않는 데이터 제거
* 최소 권한 액세스 제어 적용

Campaign은 개인 정보 보호 핵심 서비스 통합, 동의 추적, 자동 삭제 워크플로우 및 규정 준수를 위한 감사 추적을 제공합니다.

[개인 정보 관리](../start/privacy.md)에 대해 자세히 알아보기

+++

+++ Campaign에서 사용자 동의를 수집하고 관리하려면 어떻게 해야 합니까?

유효한 동의에는 적극적이고 구체적이며 정보에 기반한 취소 가능한 계약이 필요합니다. 사용자는 사전 선택된 상자나 침묵이 동의가 아닌 명시적인 조치를 취해야 합니다. 서로 다른 목적(번들 제외)에 대한 별도의 동의를 제공하고 명확한 설명을 제공하며 타임스탬프가 있는 레코드를 유지 관리합니다.

**모범 사례:** 세분화된 옵트인 옵션을 제공하고, 동의를 정기적으로 새로 고치고, 기본 설정 센터에 쉽게 액세스할 수 있도록 하고, 동의를 신뢰로 구축합니다.

**Campaign의 기술 구현:**

Campaign은 동의 추적을 위해 구독 서비스, 환경 설정 센터, 옵트아웃 플래그 및 사용자 지정 동의 필드를 제공합니다.

* 동의 필드(날짜, 유형, 소스)에 대한 수신자 스키마 확장
* 각 동의 유형에 대한 구독 서비스 만들기
* 기본 설정 센터 웹 양식 작성
* 워크플로우를 사용하여 타깃팅에서 동의 적용
* 감사 추적 유지

구현이 규정 요구 사항을 충족하는지 확인하려면 법률 자문을 구하십시오.

**관련 항목:**

[구독 서비스](../start/subscriptions.md) | [개인 정보 및 동의](../start/privacy.md#consent-retention-roles) | [개인 정보 관리](../start/privacy.md)

+++

+++ 삭제 요청을 처리할 때 어떤 데이터가 삭제됩니까?

Campaign은 데이터 주체와 연결된 모든 데이터(수신자 프로필, 게재 및 추적 로그, 소유권 관계가 있는 사용자 지정 데이터, 구독 내역)를 자동으로 삭제합니다.

**작동 방식:** Campaign은 받는 사람에 대한 링크가 스키마 정의에서 `integrity="own"`을(를) 갖는 모든 데이터를 삭제하여 관련 테이블에 걸쳐 연속 삭제를 보장합니다.

스키마에서 링크 무결성을 수정하여 삭제 범위를 사용자 지정할 수 있지만 먼저 법률 자문을 구하십시오. 삭제는 영구적이며 실행 취소할 수 없습니다.

**관련 항목:**

[개인 정보 관리](../start/privacy.md) | [스키마 링크](../dev/schemas.md)

+++

+++ 개인 정보 삭제가 게재 보고서에 영향을 줍니까?

아니요. Campaign 보고서는 개별 로그의 라이브 쿼리가 아닌 미리 계산된 집계된 지표(총 전송, 열기, 클릭 수)를 기반으로 합니다. 개별 수신자 데이터를 삭제해도 내역 집계 통계는 변경되지 않습니다.

전체 게재 통계 및 성능 지표는 그대로 유지되지만 개별 추적 로그 및 개인 세부 정보는 제거됩니다. 이렇게 하면 데이터 주체 권한을 준수하면서 마케팅 분석을 유지할 수 있습니다.

**관련 항목:**

[개인 정보 관리](../start/privacy.md) | [보고서](../reporting/gs-reporting.md)

+++

+++ 삭제된 데이터를 다시 가져올 수 없도록 하려면 어떻게 해야 합니까?

Campaign뿐만 아니라 모든 소스 시스템에서 데이터를 삭제해야 합니다. 데이터는 종종 외부 시스템(CRM, 전자 상거래, 데이터 웨어하우스)에서 흐릅니다.

**필수 작업:** 모든 데이터 원본을 식별하고, 원본 시스템에서 삭제하고, 제외/제외 목록에 추가하고, 삭제 플래그를 사용하도록 가져오기 워크플로우를 업데이트하고, 프로세스를 문서화합니다.

데이터 제어자는 전체 기술 생태계에서 완전한 데이터 제거를 담당합니다.

**관련 항목:**

[개인 정보 관리](../start/privacy.md) | [워크플로우 가져오기](../config/workflows.md)

+++

+++ 삭제된 사용자가 다시 옵트인할 수 있습니까?

예. 데이터 주체는 삭제 후 다시 옵트인할 수 있습니다. Campaign은 이전에 삭제된 데이터에 대한 링크 없이 완전히 새로운 수신자 레코드를 만듭니다. 프로필은 깨끗한 슬레이트로 시작됩니다.

Campaign의 감사 추적은 삭제 이벤트와 새 프로필 생성을 모두 기록하며, 규정 준수를 입증하고 삭제 후 새 옵트인이 자유롭게 부여되었음을 보여 줍니다.

**관련 항목:**

[개인 정보 관리](../start/privacy.md) | [구독](../start/subscriptions.md)

+++

## 여전히 도움이 필요하십니까? {#get-help}

찾고 있는 항목을 찾을 수 없습니까? 다음은 Adobe Campaign v8을 성공적으로 사용할 수 있는 추가 리소스입니다.

### 커뮤니티 지원

다른 Campaign 사용자 및 Adobe 전문가와 연결하여 지식을 공유하고 답변을 얻을 수 있습니다.

* **[Adobe Campaign 커뮤니티](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}** - 질문하고, 솔루션을 공유하고, Campaign 커뮤니티에 연결합니다.
* **[Experience League 포럼](https://experienceleaguecommunities.adobe.com/){target="_blank"}** - 모든 Adobe 제품에서 토론 찾아보기
* **[Campaign 커뮤니티 운영 시간](https://experienceleague.adobe.com/){target="_blank"}** - Adobe 전문가와 실시간 세션에 참여

### 설명서 및 학습

포괄적인 안내서, 튜토리얼 및 교육 자료를 이용할 수 있습니다.

* **[캠페인 튜토리얼](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html){target="_blank"}** - 단계별 비디오 가이드 및 실습 튜토리얼
* **[새로운 기능](whats-new.md)** - 최신 기능
* **[릴리스 정보](release-notes.md)** - 현재 및 이전 릴리스 정보
* **[버전 및 업그레이드](upgrades.md)** - Campaign 버전, 업그레이드 및 버전 확인 방법에 대해 알아보기

### 기술 리소스

자세한 기술 설명서 및 개발자 리소스를 확인하십시오.

* **[캠페인 API](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=ko){target="_blank"}** - 전체 API 참조 설명서
* **[호환성 매트릭스](compatibility-matrix.md)** - 지원되는 시스템 및 버전
* **[버전 및 업그레이드 FAQ](upgrades.md)** - 버전을 확인하고 업그레이드에 대해 알아봅니다.

### 지원 및 서비스

Adobe 지원 팀의 도움을 받고 인스턴스를 관리합니다.

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** - 지원 사례 로그 및 사용자 관리
* **[Adobe 고객 지원 센터](https://helpx.adobe.com/kr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - 지원 팀에 문의
* **[Campaign 컨트롤 패널](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ko){target="_blank"}** - Campaign 인스턴스 설정 관리
* **[시스템 상태](https://status.adobe.com/){target="_blank"}** - Adobe 서비스 상태 확인

### 교육 및 인증

공식 Adobe 교육 및 인증 프로그램을 통해 기술을 향상시키십시오.

* **[Experience League 도움말](https://experienceleague.adobe.com/en/browse/campaign/campaign-v8){target="_blank"}** - Campaign v8에 대한 도움말 리소스(웹 UI 및 클라이언트 콘솔)
* **[Adobe 디지털 학습 서비스](https://learning.adobe.com/){target="_blank"}** - 공식 강사 주도 및 자습형 교육 과정
* **[Adobe Campaign 인증](https://experienceleague.adobe.com/docs/certification/program/overview.html){target="_blank"}** - 전문 인증을 통해 전문성 확인
* **[Experience League 학습 경로](https://experienceleague.adobe.com/?lang=en#dashboard/learning){target="_blank"}** - 안내식 학습 여정

### 기타 유용한 리소스

* **[Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=ko){target="_blank"}** - Classic v7 사용자를 위한 참조
* **[Campaign 웹 UI 설명서](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - 새 웹 인터페이스 안내서
* **[게재 가능성 모범 사례](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=ko){target="_blank"}** - 전자 메일 게재 최적화

