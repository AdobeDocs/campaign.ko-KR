---
title: Campaign v8 FAQ
description: 설정, 구성, 메시징, 워크플로 등에 대한 일반적인 Adobe Campaign v8 질문에 대한 답변을 얻을 수 있습니다
feature: Overview
role: User
level: Beginner
keywords: FAQ, Campaign v8, 질문, 답변, 도움말, 지원, 문제 해결
version: Campaign v8
hide: true
hidefromtoc: true
source-git-commit: 825421f9b25830daad6bdf5c8a58a1c58b272835
workflow-type: tm+mt
source-wordcount: '12510'
ht-degree: 6%

---

# 자주 묻는 질문 {#faq}

Adobe Campaign v8에 대해 가장 일반적인 질문에 대한 빠른 답변을 얻으십시오. 이제 막 시작했거나 고급 구성 도움말을 찾고 있는 경우 아래 주제별로 구성된 답변을 찾을 수 있습니다.

Campaign을 **처음 사용하시겠습니까?** 시작: [일반 질문](#general) 및 [주요 개념](#key-concepts).\
**기술 지원이 필요하십니까?** [개발자](#developers) 및 [캠페인 설정](#settings)을 확인하세요.\
**답변을 찾을 수 없습니까?** [커뮤니티 포럼](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=ko){target="_blank"}을 방문하거나 [지원 팀에 문의](#get-help)하세요.

**팁:** Ctrl+F(Mac의 Cmd+F)를 사용하여 이 페이지에서 특정 키워드를 검색합니다. 질문을 클릭하여 답변을 확장합니다.


## 일반 질문 {#general}

연결, 업그레이드 및 지원 방법 등 Adobe Campaign v8에 대해 가장 일반적인 질문에 대한 답변을 얻을 수 있습니다.

+++ Campaign v8에 연결하려면 어떻게 해야 합니까?

Adobe Campaign에 연결하려면 Campaign 클라이언트 콘솔을 다운로드하여 설치해야 합니다.

자세한 내용을 보려면 [여기](connect.md)를 클릭하십시오.

Campaign v8.6 릴리스부터 중앙 Adobe Experience Cloud 환경을 통해 사용할 수 있는 **Campaign 웹 사용자 인터페이스**&#x200B;에 액세스할 수 있습니다. Experience Cloud은 Adobe의 디지털 마케팅 애플리케이션, 제품 및 서비스 통합 제품군입니다.

Adobe Experience Cloud에 연결하고 Adobe Campaign 웹 인터페이스 [에 액세스하는 방법은 이 페이지에서](campaign-ui.md#ac-web-ui)알아볼 수 있습니다. [Adobe Campaign Web 사용자 인터페이스 설명서](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/campaign-web-home){target="_blank"}에서 자세히 알아보십시오.


**관련 항목:**

[클라이언트 콘솔 설치](connect.md) | [Campaign 사용자 인터페이스](campaign-ui.md) | [사용자 권한](gs-permissions.md)

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

+++ Campaign을 최신 버전으로 업그레이드하려면 어떻게 해야 합니까?

Adobe Campaign은 정기적으로 업데이트됩니다. 일부 버전은 새로운 기능, 개선 사항 및 수정 사항이 포함되어 매년 출시됩니다. 또한, 누적 수정 사항만 있는 빌드를 주기적으로 릴리스합니다.

이러한 정기 업데이트 빈도는 최신 업데이트를 직접 경험해 보고 사용 환경을 안전하게 지키며 Adobe 제품 경험을 향상시키는 것을 목표로 합니다. 이 때문에 Adobe Campaign의 최신 버전을 실행하는 것이 매우 중요하다고 생각합니다.

**참고:** Managed Cloud Services 사용자는 새 릴리스를 통해 Adobe에서 인스턴스를 업그레이드합니다.

[Campaign 버전 및 업그레이드에 대해 자세히 알아보세요](upgrades.md).

+++

+++ 이메일 게재 기능을 구성하는 방법

모든 발신자의 마케팅 프로그램 성공에 중요한 구성 요소인 이메일 게재 기능의 특징은 기준과 규칙이 계속 변한다는 것입니다. 이 디지털 세상을 효과적으로 탐색하려면 주요 전달성 트렌드를 고려하여 이메일 전략을 정기적으로 조정함으로써 대상자에게 가장 효과적으로 도달해야 합니다.

[게재 가능성 모범 사례](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=ko){target="_blank"}에 대해 알아보려면 이 안내서를 참조하세요.

[이 안내서에서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=ko){target="_blank"} Campaign의 전달성을 구현하는 방법을 알아보십시오.

**관련 항목:**

[전달성 정보](../send/about-deliverability.md) | [메시지 콘텐츠 제어](../send/control-message-content.md) | [게재 기능 모니터링](../send/monitoring-deliverability.md) | [SpamAssassin](../send/spamassassin.md)

+++

+++ 게재가 오류 없이 전송되도록 하려면 어떻게 해야 합니까?

성공적인 전달을 위해 다음 단계를 수행합니다.

**보내기 전:**

* 게재 분석을 실행하여 오류 감지(개인화 누락, 잘못된 수신자, 콘텐츠 문제)
* 테스트 증명을 전송하여 렌더링 및 개인화 확인
* 준비 중 경고 검토
* 대상 모집단 수 확인

**전송 중 및 전송 후:**

* 게재 대시보드에서 실시간 통계(전송, 게재, 바운스, 오류) 모니터링
* 게재 로그에서 메시지 수준 상태 확인
* 성공률, 바운스 비율 및 오류 메시지 추적
* 격리된 주소 검토

**모범 사례:**

* 오류 임계값에 대한 경고 설정
* 대용량의 웨이브(일괄 전송) 사용
* 먼저 작은 볼륨으로 테스트합니다.
* 정기적으로 수신자 데이터베이스 정리
* 보낸 사람의 신뢰도 모니터링

[게재 모니터링](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=ko){target="_blank"} 및 [게재 모범 사례](delivery-best-practices.md)에 대해 자세히 알아보세요.

+++

+++ 워크플로 실행을 모니터링할 수 있습니까?

예. Campaign은 워크플로우 실행을 모니터링하는 여러 도구를 제공합니다.

* **[워크플로우 대시보드](https://experienceleague.adobe.com/ko/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"}** - 각 워크플로우 활동에 대한 실시간 상태, 진행 상황 및 오류를 봅니다.
* **[워크플로 로그](https://experienceleague.adobe.com/ko/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#displaying-logs){target="_blank"}** - 자세한 실행 로그에 액세스하여 문제를 해결합니다.
* **[Heatmap](https://experienceleague.adobe.com/ko/docs/campaign/automation/workflows/monitoring-workflows/heatmap){target="_blank"}** - 워크플로우 활동을 시각화하고 성능 병목 현상을 식별합니다.
* **[감사 추적](../reporting/audit-trail.md)** - 워크플로에 대한 모든 수정 사항을 추적합니다.
* **[경고](https://experienceleague.adobe.com/ko/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators){target="_blank"}** - 워크플로 오류 또는 지연에 대한 알림 설정

워크플로우를 모니터링하려면 워크플로우를 열고 **로그** 탭을 클릭합니다. 실패한 활동은 빨간색으로 강조 표시되며, 이를 클릭하여 오류 세부 정보를 볼 수 있습니다.

[워크플로 실행 모니터링](https://experienceleague.adobe.com/ko/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} 및 [워크플로 모범 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=ko){target="_blank"}에 대해 자세히 알아보세요.

+++

+++ 어떤 시스템과 구성 요소가 Campaign v8과 호환됩니까?

[Adobe Campaign 호환성 매트릭스](compatibility-matrix.md)에서 Campaign 최신 빌드에 대해 지원되는 모든 시스템 및 구성 요소 목록을 가져올 수 있습니다.

+++

+++ Campaign을 다운로드하는 방법은 무엇인가요?

Adobe 다운로드 센터에서 설치 프로그램과 클라이언트 콘솔을 다운로드할 수 있습니다.

관리 사용자로 Adobe [소프트웨어 배포](https://experience.adobe.com/#/downloads/content/software-distribution/ko/campaign.html){target="_blank"}에 액세스하여 Adobe Campaign을 다운로드합니다.

이 페이지에서 [&#x200B; 배포 센터에 대해 자세히 알아보세요](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=ko){target="_blank"}.

+++

+++ 도메인 위임의 절차는 무엇입니까?

하위 도메인은 브랜드나 다양한 트래픽 유형(트랜잭션 메시지, 마케팅 정보 등)을 분리하는 데 사용할 수 있는 도메인의 개별 부분입니다.

>[!NOTE]
>
>Managed Cloud Services 사용자는 Adobe에 문의하여 하위 도메인을 Adobe에 위임할 수 있습니다.

+++

+++ Campaign Classic v7 사용자는 Campaign v8로 마이그레이션할 수 있나요?

기존 Campaign Classic v7 환경에서의 자동 마이그레이션은 아직 불가능합니다.

Campaign v8은 현재 **관리 클라우드 서비스로만 사용할 수 있으며** 온-프레미스 또는 하이브리드 환경에 배포할 수 없습니다.

마이그레이션 프로세스에 대한 자세한 내용은 Adobe 담당자에게 문의하십시오.

+++


+++ 문제를 기록하려면 어떻게 해야 합니까?

사례를 만들면 Adobe 제품에 발생하는 모든 문제에 대해 Adobe 고객 지원 팀으로 문의할 수 있습니다. 문제를 확인하거나 해결하려면 Adobe Admin Console을 통해 Adobe 고객 지원 센터와 채팅할 수 있습니다.

문제를 기록하거나 새 시스템에서 채팅 세션을 시작하려면 [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"}에 연결하십시오.

새 시스템에서는 올바른 권한을 가진 각 사용자에 대해 새 개인 계정이 필요합니다. Adobe ID로 로그인할 수 없는 경우 Experience League를 통해 액세스를 요청하면 고객 지원 팀에서 가능한 한 빨리 설정을 완료합니다. [자세히 알아보기](https://helpx.adobe.com/kr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

Campaign 커뮤니티 가입: 기존 질문에서 답변을 검색하거나 전문가에게 질문할 수 있습니다. [대화에 참여](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=ko){target="_blank"}

+++


## 주요 개념 {#key-concepts}

효과적으로 시작하기 위한 인증, 사용자 인터페이스, 워크플로우 및 핵심 기능을 포함한 기본 Campaign 개념에 대해 알아봅니다.

+++ Adobe ID으로 Campaign v8에 연결할 수 있습니까?

예! IMS(Adobe Identity Management System)와의 통합 덕분에 사용자는 Adobe ID을 사용하여 Adobe Campaign 콘솔에 연결합니다. 이 통합은 다음과 같은 이점을 제공합니다.

* 모든 Experience Cloud 솔루션에 동일한 ID를 사용할 수 있습니다.
* 서로 다른 통합으로 Adobe Campaign을 사용하는 경우 연결이 기억됩니다.
* 보안 암호 관리 정책.
* 페더레이션 ID 계정 사용(외부 ID 공급자).

Adobe ID을 사용하여 Campaign v8에 액세스하는 방법에 대해 [자세히 알아보기](connect.md).

+++

+++ Campaign의 버전은 무엇입니까?

Campaign 클라이언트 콘솔의 **도움말 > 정보...[&#x200B; 메뉴에서 버전 및 빌드 번호](upgrades.md#version)를** 확인합니다.

+++

+++ Campaign Classic v7과 Campaign v8 간의 차이점은 무엇입니까?

Campaign v8은 Managed Cloud Services용으로 설계된 차세대 Campaign 버전입니다. 인프라, 보안, 전달성 및 모니터링에서 상당한 향상을 가져옵니다.

Adobe Campaign v8은 **관리 Cloud Service**&#x200B;로만 사용할 수 있으며 온-프레미스 또는 하이브리드 환경에 배포할 수 없습니다.

[Campaign Classic v7에서 v8로의 전환에 대해 자세히 알아보세요](v7-to-v8.md).

+++

+++ 사용자 권한을 설정하려면 어떻게 해야 합니까?

Campaign 관리자는 조직의 사용자에 대한 권한을 설정할 수 있습니다.

다음은 권한을 부여하거나 거부한 권한 및 제한 세트입니다.

* 특정 기능에 액세스
* 특정 데이터에 액세스
* 데이터 만들기, 수정 및/또는 삭제

Campaign v8의 사용자 권한에 대해 [자세히 알아보기](../start/gs-permissions.md).

**관련 항목:**

[사용 권한 시작](gs-permissions.md) | [사용자 권한 관리](manage-permissions.md) | [폴더에 권한 추가](folder-permissions.md)

+++

+++ 알아야 하는 Campaign 사용자 인터페이스 개념은 무엇입니까?

Adobe Campaign 사용자 인터페이스 기본 사항에 대한 자세한 내용은 [이 섹션](campaign-ui.md)을 참조하세요.

Campaign v8.6 릴리스부터 중앙 Adobe Experience Cloud 환경을 통해 사용할 수 있는 새로운 **Campaign 웹 사용자 인터페이스**&#x200B;에 액세스할 수 있습니다.

[Adobe Campaign 웹 사용자 인터페이스 설명서에서 자세히 알아보세요](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

+++

+++ 메시지 대상자를 선택하려면 어떻게 해야 합니까?

Adobe Campaign을 사용하면 다양한 전략을 사용하여 대상자를 만들고 대상 수신자를 선택할 수 있습니다.

Campaign v8에서 대상을 정의하는 방법에 대해 [자세히 알아보기](../audiences/gs-audiences.md).

+++

+++ 워크플로란?

Adobe Campaign에는 애플리케이션 서버의 여러 모듈에 걸쳐 전체 프로세스 및 작업을 오케스트레이션하는 워크플로가 포함되어 있습니다. 이 포괄적인 그래픽 환경을 사용하면 세분화, 캠페인 실행, 파일 처리, 인력 참여 등의 프로세스를 디자인할 수 있습니다. 워크플로 엔진은 이러한 프로세스를 실행하고 추적합니다.

예를 들어 워크플로에서 서버에서 파일을 다운로드하고 압축을 해제한 다음 Adobe Campaign 데이터베이스에 포함된 레코드를 가져올 수 있습니다.

워크플로에는 알림을 받거나 프로세스를 선택하고 승인할 수 있는 운영자가 한 명 이상 포함될 수도 있습니다. 이러한 방식으로 게재 작업을 만들고, 콘텐츠를 사용하여 작업하도록 한 명 이상의 운영자에게 작업을 할당하고, 대상을 지정하고, 게재를 시작하기 전에 교정쇄를 승인할 수 있습니다.

워크플로우에 대해 [자세히 알아보기](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=ko){target="_blank"}. 또한 [워크플로 모범 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=ko){target="_blank"}를 참조할 수 있습니다.

**관련 항목:**

[워크플로우 시작](../config/workflows.md) | [첫 번째 워크플로우 구축](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=ko){target="_blank"} | [워크플로우 사용 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [워크플로우 실행 모니터링](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=ko){target="_blank"}

+++

+++ 첫 번째 이메일을 만들고 보내는 방법

Campaign v8에서 첫 번째 이메일을 만드는 절차에는 다음과 같은 몇 가지 주요 단계가 포함됩니다.

1. **게재 만들기** - 템플릿 또는 처음부터 새 이메일 게재를 만들어 시작합니다.
1. **대상자 정의** - 쿼리, 목록 또는 워크플로를 사용하여 대상 받는 사람을 선택합니다.
1. **콘텐츠 디자인** - 이메일 디자이너를 사용하여 개인화된 메시지를 만들 수 있습니다.
1. **증명을 사용하여 테스트** - 테스트 이메일을 전송하여 콘텐츠 및 개인화의 유효성을 검사합니다.
1. **분석 및 보내기** - 게재 분석을 실행하여 오류를 확인한 다음 이메일을 보냅니다.

Campaign v8은 이메일 생성을 위한 두 가지 인터페이스를 제공합니다.

* **클라이언트 콘솔** - 고급 기능을 갖춘 모든 기능을 갖춘 데스크톱 응용 프로그램
* **Campaign 웹 UI** - 보다 빠른 이메일 작성을 위한 현대적이고 직관적인 웹 인터페이스

[이메일 디자인 및 유효성 검사에 대해 자세히 알아보기](../send/email.md) Campaign v8에서.

**관련 항목:**

[첫 번째 게재 만들기](create-message.md) | [게재 템플릿 작업](../send/create-templates.md) | [게재 모범 사례](delivery-best-practices.md) | [전자 메일 콘텐츠 정의](../send/defining-the-email-content.md) | [미리 보기 및 증명](../send/preview-and-proof.md) | [구성 및 보내기](../send/configure-and-send.md) | [콘텐츠 개인화](../send/personalize.md)

+++

+++ SMS 메시지를 보내는 방법

Campaign v8에서 SMS 메시지를 보내려면 초기 구성이 필요한 다음 간단한 게재 프로세스를 따릅니다.

**초기 설정(1회 구성):**

1. **SMS 채널 구성** - SMS 게재 설정 및 외부 계정 설정
1. **SMPP 연결 구성** - SMPP 프로토콜을 통해 SMS 서비스 공급자에 연결합니다.
1. **연결 테스트** - SMS 공급자와의 연결을 확인합니다.
1. **라우팅 설정** - SMS 메시지가 공급자를 통해 라우팅되는 방법을 정의합니다.

**SMS 만들기 및 보내기:**

1. **SMS 게재 만들기** - 템플릿에서 새 SMS 게재를 시작합니다.
1. **받는 사람 정의** - 전화 번호 필드를 사용하여 휴대폰 대상자를 선택합니다.
1. **SMS 콘텐츠 작성** - 메시지 만들기(표준 160자 이상, 연결 사용)
1. **개인화 추가** - 각 수신자와 관련된 동적 필드 포함
1. **증명 보내기** - SMS 게재를 테스트하여 콘텐츠 및 게재의 유효성을 검사합니다.
1. **분석 및 보내기** - 분석을 실행하고 대상자에게 보내기

**주요 SMS 기능:**

* **여러 SMPP 커넥터** - 다양한 SMS 공급자 및 프로토콜 지원
* **게재 보고서** - 보낸 메시지, 배달된 메시지 및 실패한 메시지를 추적합니다.
* **문자 인코딩** - GSM7, 유니코드 및 특수 문자 지원
* **긴 SMS 지원** - 긴 텍스트를 위한 자동 메시지 연결
* **양방향 SMS** - 워크플로우로 인바운드 SMS 응답 처리

[Campaign v8에서 SMS 구성 및 전송에 대해 자세히 알아봅니다](../send/sms/sms.md).

**관련 항목:**

[SMS 시작](../send/sms/sms.md) | [SMS 게재 설정](../send/sms/sms-delivery-settings.md) | [SMPP 외부 계정 설정](../send/sms/smpp-external-account.md) | [SMS 게재 만들기](../send/sms/create-sms.md) | [SMS 콘텐츠](../send/sms/sms-content.md) | [SMS 증명 보내기](../send/sms/sms-proofs.md) | [SMS 모니터링](../send/sms/sms-monitor.md)

+++

+++ 푸시 알림을 전송하는 방법

Campaign v8에서 푸시 알림을 보내려면 모바일 앱 통합을 구성하고 매력적인 알림 만들기를 해야 합니다.

**초기 설정(1회 구성):**

1. **푸시 채널 구성** - Campaign에서 푸시 알림 채널 설정을 설정합니다.
1. **Campaign SDK 통합** - Adobe Campaign SDK을 모바일 앱에 추가(또는 데이터 수집 사용)
1. **모바일 앱 구성** - Campaign에서 iOS 및 Android 앱 등록
1. **인증서 설정** - APNs 인증서(iOS) 및 FCM 키(Android) 구성
1. **등록 테스트** - 장치가 토큰을 등록하고 받을 수 있는지 확인

**푸시 알림 만들기 및 전송:**

1. **푸시 게재 만들기** - 템플릿에서 새 푸시 알림 시작
1. **플랫폼 선택** - iOS, Android 또는 두 플랫폼 모두 선택
1. **대상 정의** - 모바일 앱 구독 데이터를 사용하여 앱 구독자를 타깃팅합니다.
1. **디자인 알림** - 제목, 메시지 및 리치 미디어 콘텐츠 만들기
1. **동작 구성** - 클릭 동작, 딥링크 및 사용자 지정 데이터 설정
1. **테스트 알림 보내기** - 보내기 전에 실제 장치에서 유효성 확인
1. **분석 및 보내기** - 타깃팅을 검토하고 모바일 대상자에게 보냅니다.

**푸시 알림 기능:**

* **리치 푸시 알림** - 이미지, 비디오 및 대화형 단추 포함(iOS 및 Android)
* **Personalization** - 사용자 프로필 및 동작을 기반으로 하는 다이내믹 콘텐츠
* **딥링크** - 사용자를 특정 앱 화면 또는 콘텐츠로 보냅니다.
* **예약** - 사용자 시간대에 따라 최적의 시간에 전송
* **A/B 테스트** - 다른 메시지를 테스트하고 참여를 최적화합니다.
* **추적** - 열기, 클릭 수, 전환 모니터링

**플랫폼별 기능:**

* **iOS** - 자동 알림, 알림 범주, 사운드 사용자 지정
* **Android** - 리치 푸시 템플릿, 알림 채널, 사용자 지정 레이아웃

[푸시 알림 구성에 대해 자세히 알아보기](../send/push-settings.md) Campaign v8에서.

**관련 항목:**

[푸시 알림 만들기 및 보내기](../send/push.md) | [푸시 알림 채널 구성](../send/push-settings.md) | [Android 리치 푸시 디자인](../send/rich-push-android.md) | [iOS 리치 푸시 디자인](../send/rich-push-ios.md) | [데이터 수집으로 구성](../send/push-data-collection.md) | [추적 및 모니터링](tracking.md)

+++

+++ 랜딩 페이지를 만드는 방법

Adobe Campaign 디지털 콘텐츠 편집기를 사용하여 랜딩 페이지를 디자인하고 데이터베이스 필드가 있는 매핑을 정의할 수 있습니다.

Campaign v8 설명서에서 [자세히 알아보기](../dev/landing-pages.md).

Campaign 웹 사용자 인터페이스를 사용하여 랜딩 페이지를 만들고 게시할 수도 있습니다. - [자세히 알아보기](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}.

+++

+++ 게재를 추적하려면 어떻게 합니까?

전용 [게재 보고서](../reporting/delivery-reports.md)를 통해 Campaign v8로 전송된 게재를 추적한 다음 게재를 모니터링할 수 있습니다.

이 페이지[에서 Campaign &#x200B;](../start/tracking.md)의 추적 관리에 대해 자세히 알아보세요.

**관련 항목:**

[메시지 추적 및 모니터링](tracking.md) | [게재 보고서](../reporting/delivery-reports.md) | [게재 실패 이해](../send/delivery-failures.md) | [추적된 링크 구성](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"}

+++

+++ 오류 메시지를 번역하는 방법

외국어로 오류 메시지가 표시됩니까? 모든 오류 메시지와 해당 번역이 [이 페이지](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=ko){target="_blank"}에 나열됩니다.

+++

+++ 웹 양식을 만들고 Campaign에서 답변을 수집할 수 있습니까?

예. 양식 논리 및 유효성 검사를 완벽하게 제어하기 위해 **Campaign 웹 응용 프로그램 및 Forms**(클라이언트 콘솔)을 사용하여 웹 양식을 만들거나 구독 및 리드 생성을 위한 최신 드래그 앤 드롭 인터페이스와 함께 **Campaign 랜딩 페이지**(웹 UI)를 사용하십시오. 둘 다 데이터를 Campaign에 직접 수집하고 워크플로우와 통합하여 자동화된 작업을 수행합니다.

[웹 응용 프로그램 및 양식에 대해 자세히 알아보기](../dev/webapps.md) | [Campaign 웹 UI 랜딩 페이지](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++



## Campaign v8과 이전 버전 {#v7-differences}

아키텍처, 배포, 마이그레이션 경로, 기능 변경 사항을 포함하여 Campaign v8과 이전 버전(Classic v7 및 Standard)의 주요 차이점을 이해합니다. Campaign Classic v7 또는 Campaign Standard 출신이든 새로운 기능과 원활하게 전환하는 방법에 대해 알아보십시오.

+++ Campaign v8과 이전 버전 간의 주요 차이점은 무엇입니까?

Campaign v8은 Adobe Campaign을 완전히 새롭게 디자인한 것으로, 최신 클라우드 기반 아키텍처를 위해 설계되었으며 Campaign Classic v7 및 Campaign Standard에 비해 상당한 개선을 제공합니다.

**배포 모델:**

* **v8:** 관리 Cloud Services만 해당 - Adobe에서 완전히 호스팅 및 관리됨
* **v7/Standard:** 온-프레미스, 하이브리드 또는 호스팅 옵션을 사용할 수 있습니다.
* **이점:** 제로 인프라 관리, 자동 확장, 엔터프라이즈급 보안, 사전 예방적 모니터링

**아키텍처 및 성능:**

* PostgreSQL 데이터베이스를 사용하는 **v8:** FFDA(Enhanced Full FDA) 아키텍처
* **v8:** 일괄 처리 처리량이 시간당 최대 **2천만 개의 작업에 도달함**
* **v8:** 시간당 **1백만 건의 트랜잭션 메시지 처리량**
* **v8:** 실시간 데이터 탐색 및 빠른 대상 구축(분 대 시간)
* **이점:** 대규모 운영 및 복잡한 캠페인에 대한 성능 향상

**사용자 인터페이스:**

* **v8:** 클라이언트 콘솔과 함께 새로운 **Campaign 웹 사용자 인터페이스** - 직관적이고 접근성이 뛰어나며 마케터에게 이상적입니다
* **v8:** 끌어서 놓기 기능이 있는 현대적이고 반응형 디자인
* **v8:** 간소화된 캠페인 만들기 및 관리 워크플로
* **v8:** Campaign Standard 인터페이스와 유사한 점이 많습니다
* **이점:** 더 빠른 온보딩, 더 쉬운 캠페인 실행, 더 나은 접근성, 최소한의 학습 곡선

**새로운 주요 기능:**

* 이미지, 비디오, 대화형 단추, 회전 메뉴 및 타이머를 포함한 **푸시 알림**
* 브랜드 정렬 점수가 있는 콘텐츠 생성(이메일, SMS, 푸시)용 **AI Assistant**
* 안정성과 호환성이 향상된 **업그레이드된 SMS 인프라(SMS v2.0)**
* 원활한 컨텐츠 관리를 위한 **Adobe Experience Manager as a Cloud Service 통합**
* Campaign Standard 사용자를 위한 동적 보고를 포함하여 **향상된 보고**

**업그레이드 및 유지 관리:**

* **v8:** Adobe에서 관리하는 자동 업그레이드 - 항상 지속적인 게재 모델을 사용하여 안정적인 최신 버전에서
* **v7/표준:** 수동 업그레이드 계획 및 실행 필요
* **이점:** 유지 관리 부담 감소, 새로운 기능에 즉시 액세스, 다운타임 없음

**API 및 통합:**

* 향상된 성능과 안정성을 갖춘 **v8:** 최신 REST API
* **v8:** Adobe Experience Cloud 및 Adobe Experience Platform과의 원활한 통합
* **이점:** 손쉬운 통합, 향상된 상호 운용성, 최신 개발 사례

[Campaign v8 주요 기능에 대해 자세히 알아보기](whats-new.md)

**관련 항목:**

[Campaign Classic v7에서 v8로](v7-to-v8.md) | [v7에서 v8로의 전환 안내서](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"} | [Campaign Standard에서 v8로](acs-to-v8.md) | [Campaign Standard 전환](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [Campaign v8 채택 안내서](https://experienceleague.adobe.com/ko/docs/campaign-web/acs-to-ac/home){target="_blank"} | [Campaign v8 기능 매트릭스](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [Campaign v8 아키텍처](../architecture/architecture.md)
* [가드레일 및 제한 사항](ac-guardrails.md)

+++

+++ Campaign Classic v7 또는 Campaign Standard에서 v8로 마이그레이션해야 합니까?

**Campaign v8은 필요한 조직에 적합합니다.**

* **대량 캠페인** - 향상된 성능과 안정성으로 수백만 개의 메시지를 보냅니다(시간당 2천만 회의 작업).
* **엔터프라이즈 확장성** - 성능 문제 없이 데이터베이스 및 캠페인 확장
* **최신 웹 사용자 인터페이스** - 보다 빠른 캠페인 만들기와 향상된 사용자 경험을 위한 직관적이고 반응적인 Campaign Web UI
* **클라우드 기반의 이점** - 자동 업데이트, 관리되는 인프라, 탄력적인 확장 및 사전 모니터링 활용
* **장기 지원** - Campaign v8은 Adobe의 전략 플랫폼으로, 향후 몇 년 이내에 지원 종료에 도달할 수 있습니다
* **IT 오버헤드 감소** - 인프라 관리 및 업그레이드 계획 제거
* **고급 기능** - AI Assistant, 리치 푸시, 향상된 SMS, Adobe Experience Platform 통합

**Campaign Standard 사용자용:**

Campaign Standard 사용자는 이제 Campaign v8 Managed Cloud Services로 전환할 수 있습니다. 주요 이점은 다음과 같습니다.

* **익숙한 인터페이스** - Campaign 웹 UI는 Campaign Standard과 많은 유사성을 공유하여 학습 곡선을 최소화합니다.
* **기능 패리티** - 주요 Campaign Standard 기능이 v8(동적 보고, 중앙 브랜딩, REST API, 랜딩 페이지, 시각적 조각)에 추가되었습니다.
* **향상된 지원** - 원활한 전환과 지속적인 플랫폼 모니터링을 통한 최고 수준의 지원
* **데이터 마이그레이션** - 중단을 최소화하면서 Campaign Standard의 모든 데이터를 가져옵니다.
* **일관된 사용자 환경** - 익숙한 워크플로 및 인터페이스를 사용하여 계속 작업

**Campaign Classic v7 사용자용:**

Campaign v8은 핵심 Campaign 기능을 유지하면서 다음과 같은 실질적인 개선 사항을 제공합니다.

* **이중 인터페이스** - 강력한 클라이언트 콘솔과 최신 Campaign 웹 UI에 모두 액세스
* **향상된 성능** - 쿼리 성능 및 데이터 처리가 크게 개선되었습니다.
* **클라우드의 이점** - 자동 업그레이드, 보안 패치, Adobe에서 관리하는 백업/복구
* **최신 아키텍처** - PostgreSQL을 사용하여 FFDA 아키텍처를 개선하여 확장성 향상

**마이그레이션을 고려해야 하는 시기:**

* 현재 Campaign 인스턴스가 대규모 데이터 볼륨(수백만 개의 프로필)을 처리합니다.
* 복잡한 워크플로우 또는 타겟팅에서 성능 문제가 발생합니다.
* 인프라 관리 및 유지 관리 비용 절감
* Adobe Experience Cloud 또는 Adobe Experience Platform과의 원활한 통합 필요
* 주요 업그레이드 또는 인프라 갱신을 계획하고 있습니다.
* **미래에 대비하는 기술을 사용하려고 합니다** - 이전 버전은 지원이 종료됩니다
* **팀에 최신 인터페이스가 필요합니다** - Campaign Web UI는 마케터에게 더 나은 접근성을 제공합니다

**마이그레이션 고려 사항:**

* Adobe은 마이그레이션 지원, 지침 및 도구를 제공합니다.
* v8은 Cloud Service에서만 관리됩니다(온-프레미스 또는 하이브리드 배포 없음)
* 일부 기술 구현은 다를 수 있습니다. [기능 매트릭스](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/capability-matrix){target="_blank"}를 검토하십시오.
* 데이터 마이그레이션 및 테스트에는 계획 및 자원이 필요합니다.
* **Campaign Standard 사용자의 경우** - 워크플로가 중단되는 것을 최소화하면서 전환을 원활하게 수행할 수 있도록 설계되었습니다.

**다음 단계:**

Adobe 담당자에게 문의하여 다음을 수행합니다.

* 마이그레이션 준비 상태 및 일정 평가
* 사용 사례에 대한 구체적인 이점 이해
* 마이그레이션 전략 및 리소스 할당 계획
* 마이그레이션 도구 및 지원 액세스

**관련 항목:**

**Campaign Classic v7 사용자용:** [Campaign Classic v7에서 v8로](v7-to-v8.md) | [v7에서 v8 세부 안내서](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}

**Campaign Standard 사용자의 경우:** [Campaign Standard에서 v8로 전환](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [Campaign v8 채택 안내서](https://experienceleague.adobe.com/ko/docs/campaign-web/acs-to-ac/home){target="_blank"} | [Campaign Standard에서 v8까지 개요](https://experienceleague.adobe.com/ko/docs/campaign-web/acs-to-ac/overview){target="_blank"} | [마케터용 시작하기](https://experienceleague.adobe.com/ko/docs/campaign-web/acs-to-ac/marketers){target="_blank"} | [관리자/개발자용 시작하기](https://experienceleague.adobe.com/ko/docs/campaign-web/acs-to-ac/admin-developers){target="_blank"}

**일반 리소스:** [Campaign v8 기능 매트릭스](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [호환성 매트릭스](compatibility-matrix.md)

+++

+++ Campaign v8의 주요 용어 및 기능 차이점은 무엇입니까?

Campaign v8은 대부분의 Campaign Classic v7 및 Campaign Standard 기능을 개선했지만, 일부 기능은 클라우드 기반 아키텍처로 인해 변경되었으며 일부 용어는 버전마다 다릅니다.

**용어 차이점(Campaign Standard에서 v8까지):**

* **사용자 지정 리소스**&#x200B;은(는) 이제 **스키마**&#x200B;입니다.
* **메시지**&#x200B;은(는) **게재**&#x200B;이라고 합니다.
* **제품 사용자**&#x200B;이(가) 이제 **운영자**&#x200B;입니다.
* **역할**&#x200B;이(가) **명명된 권한**(으)로 구성되어 있습니다.
* **보안 그룹**&#x200B;은(는) 이제 **운영자 그룹**&#x200B;입니다.
* **조직 단위**&#x200B;는 **폴더 권한**&#x200B;을 통해 관리됩니다.

**Campaign 웹 UI 용어 업데이트:**

Campaign 웹 UI에서 다음 용어가 업데이트되었습니다(클라이언트 콘솔은 기존 용어를 사용).

* **받는 사람**&#x200B;이(가) 이제 **프로필**&#x200B;입니다.
* **시드 주소**&#x200B;이(가) 이제 **테스트 프로필**&#x200B;입니다.
* **게재 분석**&#x200B;이(가) 이제 **게재 준비**&#x200B;입니다(**준비** 단추 클릭).
* **전자 메일 미리 보기**&#x200B;는 **콘텐츠 시뮬레이션** 단추를 통해 사용할 수 있습니다.
* **목록**&#x200B;은(는) 이제 **대상**&#x200B;입니다.

**v8에서 사용할 수 없음:**

* **온-프레미스 및 하이브리드 배포** - v8은 관리 클라우드 서비스만 해당
* **직접 데이터베이스 액세스** - 대신 제공된 API 및 도구 사용
* **고객 관리 인프라** - Adobe에서 모든 인프라를 관리합니다.
* **수동 빌드 업그레이드** - 이제 자동(Adobe 관리)

**v8의 다른 구현:**

* **기술 워크플로우** - 일부 클라우드 아키텍처에 최적화된 워크플로는 다르게 작동할 수 있습니다.
* **데이터베이스 구조** - 향상된 FFDA 아키텍처를 사용하려면 스키마를 조정해야 할 수 있습니다.
* **사용자 지정 통합** - 클라우드 기반 아키텍처에 대한 업데이트가 필요할 수 있음
* **낮은 수준의 사용자 지정** - 관리 환경에서 다른 접근 방식이 필요한 경우도 있습니다.

**v8에서 개선되거나 대체됨:**

* **업그레이드 빌드** - 수동 대신 연속 게재 모델이 있는 자동
* **성능 조정** - Adobe 인프라 최적화에 의해 처리됨
* **보안 패치** - Adobe에서 자동으로 적용
* **백업 및 복구** - 서비스의 일부로 Adobe에서 관리
* **사용자 인터페이스** - 클라이언트 콘솔과 함께 새로운 Campaign 웹 UI

**v8로 전환하는 Campaign Standard 사용자를 위해 추가된 기능:**

* **동적 보고** - 인구 통계 분석을 사용하여 사용자 지정 가능한 실시간 보고서
* **중앙 브랜딩** - 브랜드 시각적 및 기술적 지침을 정의합니다.
* **REST API** - 통합 만들기 및 에코시스템 구축
* **랜딩 페이지 개선 사항** - Campaign Standard의 향상된 기능 패리티
* **시각적 조각** - 전자 메일 및 콘텐츠 템플릿에 재사용 가능한 시각적 구성 요소

**중요:** 대부분의 마케팅 및 운영 기능은 v8에서 사용 가능하고 개선되었습니다. 기술 및 인프라 수준 기능은 클라우드 환경에서 Adobe이 관리합니다.

**관련 항목:**

[기능 매트릭스](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [호환성 매트릭스](compatibility-matrix.md) | [보호 기능 및 제한 사항](ac-guardrails.md) | [v7에서 v8로의 전환 안내서](v7-to-v8.md)
* [Campaign Standard에서 v8로 전환](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++

## 프로필 및 대상자 {#audiences}

캠페인 프로필 관리, 대상자 만들기, 데이터 가져오기 및 수신자 타겟팅에 대한 질문에 대한 답변을 찾을 수 있습니다.

+++ 수신자를 만드는 방법

개별 프로필에 대해 클라이언트 콘솔에서 수동으로 수신자를 만들거나, 대량 추가를 위해 파일에서 가져오기(CSV/TXT), 자체 등록을 위해 웹 양식을 사용하거나, 외부 시스템의 API를 통해 통합할 수 있습니다. 가져오기 워크플로우를 사용하여 반복되는 데이터를 로드합니다.

[수동으로 프로필 만들기](../audiences/create-profiles.md) | [파일에서 프로필 가져오기](../audiences/import-profiles.md) | [웹 양식으로 프로필 수집](../audiences/collect-profiles.md)

+++

+++ 프로필을 가져오는 방법

Campaign은 가져오기 마법사를 사용한 간단한 파일 가져오기, 복잡한 변환을 위한 워크플로우 기반 가져오기, SFTP에서 예약된 워크플로우를 사용한 반복 가져오기, 프로그래밍 방식의 통합을 위한 API 가져오기 등 다양한 가져오기 방법을 제공합니다.

파일 가져오기의 경우 데이터 파일(CSV/TXT, UTF-8 인코딩)을 준비하고, 가져오기 마법사 또는 워크플로우를 사용하고 열을 Campaign 필드에 매핑하고, 업데이트/삽입 규칙을 정의하고 작은 샘플로 먼저 테스트합니다. 반복 가져오기에 워크플로우를 사용하고 중복 제거 규칙을 적용합니다.

[데이터 가져오기 안내서](../start/import.md) | [가져오기 워크플로우 반복](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=ko){target="_blank"} | [데이터 로드 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=ko){target="_blank"}

+++

+++ 마케팅 캠페인의 대상 모집단을 정의하려면 어떻게 해야 합니까?

Campaign은 시각적 기준으로 쿼리를 빌드하거나, 기존 목록 또는 세그먼트를 타겟팅하거나, 외부 파일(CSV, TXT)에서 수신자를 가져오거나, 사전 정의된 필터를 적용하는 등 다양한 타겟팅 방법을 제공합니다. AND/OR 논리와 기준을 결합하고, 특정 모집단을 제외하고, 제어 그룹을 사용하고, A/B 테스트를 위해 분할할 수 있습니다. 보내기 전에 항상 대상 모집단 크기를 미리 봅니다.

[캠페인 대상 정의](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=ko){target="_blank"} | [쿼리 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=ko){target="_blank"} | [대상자 만들기](../audiences/create-audiences.md)

+++

+++ 프로필 목록을 만들려면 어떻게 해야 합니까?

목록은 게재에서 타겟팅하고 캠페인 간에 재사용할 수 있는 정적 수신자 세트입니다.

**세 가지 생성 방법:**

* **수동 만들기:** **[!UICONTROL Profiles and Targets > Lists]**(으)로 이동하여 **[!UICONTROL Create]**&#x200B;을(를) 클릭합니다. 쿼리, 개별 선택 또는 폴더에서 수신자를 추가합니다.

* **워크플로 자동화:** **[!UICONTROL List update]** 활동을 사용하여 쿼리 결과 또는 가져온 데이터에서 자동으로 목록을 만들고 유지 관리합니다.

* **가져오는 중:** 프로필을 가져올 때 목록을 만들어 재사용 가능한 그룹으로 저장합니다.

**팁:** 정기 업데이트가 필요한 목록에는 워크플로우를 사용하고 일회성 세그먼테이션을 수행하려면 수동으로 만드십시오.

[대상자 만들기](../audiences/create-audiences.md) | [업데이트 활동 나열](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html?lang=ko){target="_blank"}

+++

+++ 메시지를 보내기 전에 모집단 중복을 제거하려면 어떻게 해야 합니까?

워크플로우에서 **[!UICONTROL Deduplication]** 활동을 사용하여 배달하기 전에 중복 수신자를 제거합니다. **[!UICONTROL Query]**&#x200B;과(와) **[!UICONTROL Delivery]** 활동 사이에 배치한 다음 중복 제거 기준(일반적으로 이메일 주소 또는 수신자 ID)과 보관할 레코드를 선택하십시오.

**팁:** 각 사용자가 메시지를 한 번만 받도록 하려면 보내기 전에 항상 중복 제거를 수행하세요.

[중복 제거 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=ko){target="_blank"}

+++

+++ 뉴스레터 가입자를 식별하고 타겟팅하는 방법

Campaign은 정보 서비스를 통해 뉴스레터 구독을 자동으로 추적합니다. 구독자를 타겟팅하려면:

* **[!UICONTROL Query]** 활동을 사용하고 **[!UICONTROL Subscriptions]**&#x200B;에서 필터링하고 뉴스레터 서비스를 선택하세요.
* **[!UICONTROL To > Subscribers of an information service]**&#x200B;을(를) 선택하여 게재에서 바로 구독자를 타겟팅합니다.
* **[!UICONTROL Subscription Services]** 워크플로우 활동으로 구독자 목록 작성

Campaign은 구독/구독 취소 기록을 추적하고 옵트인/옵트아웃을 자동으로 관리합니다.

[구독 관리](../start/subscriptions.md) | [쿼리 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=ko){target="_blank"}

+++

+++ 대상 모집단에서 프로필을 제외하는 가장 좋은 방법은 무엇입니까?

워크플로우에서 **[!UICONTROL Exclusion]** 활동을 사용하여 대상에서 원치 않는 프로필을 제거하십시오. 타겟팅 활동 뒤에 배치하고 제외할 모집단을 정의합니다.

[제외 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html?lang=ko){target="_blank"}

+++

+++ Campaign에서 외부 프로필을 가져오지 않고 사용할 수 있습니까?

예. Campaign v8을 사용하면 Adobe Campaign에 로드하지 않고 외부 데이터베이스에 저장된 외부 프로필을 사용하여 작업할 수 있습니다. [자세히 알아보기](../audiences/external-profiles.md)

+++

+++ 게재에 대한 테스트 프로필을 만들려면 어떻게 해야 합니까?

테스트 프로필은 프로덕션 데이터베이스에 영향을 주지 않고 증명을 보내고 게재를 확인하는 데 사용되는 특수 수신자입니다. **[!UICONTROL Profiles and Targets > Test profiles]**&#x200B;에서 만들거나 **[!UICONTROL Seed addresses]** 기능을 사용하여 품질 보증 및 받은 편지함 모니터링을 위해 게재에 테스트 수신자를 자동으로 추가하십시오.

[테스트 프로필](../audiences/test-profiles.md)

+++

## 메시지 디자인 {#design}

이메일 템플릿, 개인화 기술 및 다국어 콘텐츠를 포함하여 Campaign v8에서 효과적인 마케팅 메시지를 디자인하는 방법을 알아봅니다. 향상된 시각적 편집 환경을 위해 클라이언트 콘솔에서 메시지를 디자인하거나 Campaign 웹 UI에서 최신 **이메일 Designer**&#x200B;을(를) 사용하십시오.

+++ Campaign에서 전자 메일을 디자인하는 우수 사례는 무엇입니까?

주요 지침: 모바일 반응형 디자인 확인, 인라인 CSS와 함께 HTML 4.0/XHTML 호환 코드 사용, 대체 텍스트로 이미지 최적화(100KB 미만), 개인화 병합 필드 사용, 보내기 전에 이메일 클라이언트 간 테스트, 일반 텍스트 버전 포함. 최적의 전달성을 위해 500KB 미만의 총 이메일 크기를 목표로 합니다.

[전자 메일 디자인 가이드](../send/email.md) | [게재 모범 사례](delivery-best-practices.md)

+++

+++ 게재 템플릿이란 무엇입니까?

게재 템플릿은 여러 캠페인에서 재사용할 모든 설정 및 매개 변수를 저장하는 사전 구성된 게재입니다. 템플릿에는 타겟 규칙, 콘텐츠 디자인, 개인화, 기술 설정(발신자, 회신) 및 유형화 규칙이 포함됩니다. 한 번 만든 다음 재사용하여 일관성을 유지하고 캠페인 생성 속도를 높일 수 있습니다.

[게재 템플릿 만들기](../send/create-templates.md)

+++

+++ Campaign에서 전자 메일을 만들기 위해 기존 HTML을 쉽게 가져올 수 있습니까?

예. 직접 복사/붙여넣기를 통해 콘텐츠 편집기에 HTML 콘텐츠를 가져오거나, 컴퓨터에서 파일을 업로드하거나, URL에서 로드합니다. HTML에서 인라인 CSS와 함께 이메일 호환 코드(HTML 4.0/XHTML)를 사용하고 공용 서버에서 이미지를 호스팅하는지 확인하십시오. Campaign은 가져온 HTML에 개인화 및 추적을 자동으로 추가합니다.

**팁:** 이메일 디자인 환경을 최적화하려면 Campaign 웹 UI에서 원시 Designer을 가져오는 대신 최신 드래그 앤 드롭 기능과 기본 제공 반응형 템플릿을 제공하는 **이메일 HTML**&#x200B;을(를) 사용하십시오.

[HTML 콘텐츠 가져오기](../send/defining-the-email-content.md)

+++

+++ Campaign에서 구독 기반 뉴스레터를 만들려면 어떻게 해야 합니까?

예. Campaign의 정보 서비스를 사용하여 뉴스레터 구독을 관리합니다. 주요 기능에는 자동 옵트인/옵트아웃 처리, 구독 추적, 규정 준수 관리(GDPR, CAN-SPAM), 다중 뉴스레터 지원, 가입 양식을 위한 웹 통합 및 구독자에 대한 타겟팅 게재가 포함됩니다.

[구독 관리](../start/subscriptions.md)

+++

+++ 메시지를 개인화하려면 어떻게 해야 합니까?

Campaign은 수신자 데이터, 동작 및 환경 설정을 기반으로 관련성 있고 타깃팅된 메시지를 만들 수 있는 개인화 기능을 제공합니다.

**Personalization 옵션:**

* **개인화 필드** - 수신자 데이터 삽입(예: `"Hello {{firstName}}")`)
* **개인화 블록** - 미리 정의된 콘텐츠 블록 또는 사용자 지정 콘텐츠 블록 사용
* **조건부 콘텐츠** - 수신자 기준에 따라 다른 콘텐츠 표시
* **동작 데이터** - 검색 기록, 구매 패턴 또는 참여 지표 활용

보내기 전에 개인화를 테스트하여 병합 필드 및 조건부 논리가 올바르게 작동하는지 확인하십시오.

[Personalization 안내서](../send/personalize.md) | [개인화 필드](../send/personalization-fields.md) | [조건부 콘텐츠](../send/conditions.md)

+++

+++ 다국어 메시지를 보낼 수 있습니까?

예. Campaign v8은 다국어 기능을 제공하며 **Campaign 웹 UI**&#x200B;는 가장 쉬운 접근 방식을 제공합니다. 웹 UI는 언어 변형이 포함된 기본 다국어 게재를 제공합니다. 언어 변형을 게재에 추가하면 Campaign에서 수신자의 선호 언어를 기반으로 적절한 버전을 자동으로 전송합니다. 이메일, 푸시 알림, SMS 및 트랜잭션 메시지에 사용할 수 있습니다.

주요 기능: 자동 콘텐츠 복제, 자동 언어 기반 전송, 기본 언어 대체 및 간편한 변형 관리.

또한 클라이언트 콘솔은 조건부 콘텐츠 및 워크플로를 사용하여 다국어 콘텐츠를 지원하지만 더 많은 수동 구성이 필요합니다.

[다국어 게재(웹 UI)](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [조건부 콘텐츠(클라이언트 콘솔)](../send/conditions.md)

+++

+++ Webform을 현지화할 수 있습니까?

예. Campaign 웹 애플리케이션은 다국어 현지화 기능을 지원합니다. 수신자 프로필 또는 브라우저 설정을 기반으로 자동 언어 감지를 사용하여 모든 양식 요소(레이블, 버튼, 메시지, 오류 텍스트)에 대한 번역을 정의합니다. 단일 웹 애플리케이션 내에서 여러 언어 버전이 지원되며 필요한 경우 기본 언어로 대체됩니다.

[웹 애플리케이션 로컬라이제이션](../dev/webapps.md)

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

[AI Assistant 개요](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [AI Assistant 사용 사례](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [브랜드 정렬](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## 메시지 테스트 및 보내기 {#send}

성공적인 캠페인 전달을 위해 마케팅 메시지를 테스트, 유효성 검사, 전송 및 추적하기 위한 모범 사례에 대해 알아봅니다.

+++ 게재 분석이란 무엇입니까?

게재 분석은 보내기 전에 Campaign이 실행되는 유효성 검사 단계입니다. 대상 모집단을 계산하고, 콘텐츠를 확인하고, 오류를 확인하고, 유형화 규칙을 적용하고, 게재 볼륨을 예측합니다.

Campaign은 경고 및 오류를 표시하는 로그를 생성합니다. 오류는 전달을 차단하며 수정해야 합니다. 경고는 도움이 됩니다. 보내기 전에 항상 분석 로그를 검토하십시오.

[게재 분석 안내서](../send/delivery-analysis.md)

+++

+++ 증명을 만들어야 하는 이유는 무엇입니까?

증명은 기본 대상자에게 보내기 전에 게재를 확인하는 테스트 메시지입니다. 증명을 사용하여 개인화를 확인하고, 이메일 클라이언트 간에 콘텐츠 렌더링을 테스트하고, 링크 및 추적 작업을 확인하고, 이미지 및 첨부 파일을 확인하고, 모바일 응답성을 확인합니다.

증명을 사용하면 수천 명의 수신자에게 도달하기 전에 오류를 포착하고, 관련자 승인을 활성화하고, 받은 편지함 배치를 테스트할 수 있습니다. 여러 이메일 클라이언트 및 장치에 증명을 보내고, 프로덕션이 전송되기 전에 항상 승인을 받습니다.

[증명 및 미리보기 안내서](../send/preview-and-proof.md)

+++

+++ Adobe Campaign에서 시드 주소를 사용하는 방법

시드 주소는 대상 기준과 일치하지 않고 테스트, 품질 보증 및 모니터링을 위해 모든 게재에 자동으로 추가되는 특수 수신자입니다. 지속적인 모니터링, 받은 편지함 배치 테스트, DM 유효성 검사 및 관련자 가시성에 유용합니다.

**증명과의 주요 차이점:**

* **시드 주소** - 프로덕션 게재에 자동으로 추가되며 전송 볼륨에 계산됩니다.
* **증명** - 프로덕션 전에 테스트가 전송되고, 볼륨에 포함되지 않으며, 유효성 검사에 사용됩니다.

**[!UICONTROL Resources > Campaign management > Seed addresses]**&#x200B;의 시드 주소를 관리합니다. 게재 지표에 영향을 주지 않도록 목록을 작게 유지합니다.

[시드 주소 가이드](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html?lang=ko){target="_blank"}

+++

+++ 메시지를 보내기 전에 승인 프로세스를 설정하려면 어떻게 해야 합니까?

Campaign은 메시지를 보내기 전에 품질 기준을 충족하는 승인 워크플로우를 제공합니다. 캠페인 또는 게재 수준에서 콘텐츠, 타겟, 추출(DM) 및 예산에 대한 승인을 구성합니다.

**설치:**

**[!UICONTROL Administration > Access management > Operator groups]**&#x200B;에서 연산자 그룹을 만든 다음 캠페인 또는 게재 속성에서 승인 그룹을 할당하십시오. Campaign은 변경 사항을 승인, 거부 또는 요청할 수 있는 검토자에게 알림 이메일을 보냅니다.

**독립 실행형 게재의 경우(캠페인에 포함되지 않음):**

**증명을 승인 프로세스로 사용**. 확인을 위해 승인 그룹에 증명을 보내고, 관련자가 최신 버전을 검토하도록 변경한 후 항상 새 증명을 보냅니다.

[게재 유효성 검사](../send/preview-and-proof.md) | [캠페인 승인](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=ko){target="_blank"}

+++

+++ 유형화 규칙이란 무엇입니까?

유형화 규칙은 메시지 보내기의 유효성을 검사하고 최적화하기 위해 게재 분석 중에 적용되는 자동화된 비즈니스 논리입니다. 마케팅 정책 준수를 보장하고, 전달성을 보호하며, 고객 피로도를 방지합니다.

**기본 규칙 유형:**

* **필터링 규칙** - 수신자 제외(차단 목록에 추가된, 구독 취소, 격리됨)
* **압력 규칙** - 받는 사람이 너무 많으면 메시지 빈도를 제어합니다.
* **용량 규칙** - 처리 용량 또는 ISP 제한에 대한 메시지 볼륨 제한
* **제어 규칙** - 메시지 유효성 확인(제목 줄, 구독 취소 링크, 보낸 사람 형식)

규칙은 유형화로 그룹화되고 게재 분석 중에 적용됩니다. Campaign은 규칙에 따라 수신자를 제외하거나, 게재를 차단하거나, 경고를 생성할 수 있습니다.

[유형화 규칙 안내서](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=ko){target="_blank"}

+++

+++ 전자 메일을 웨이브로 보내려면 어떻게 해야 합니까?

예. 웨이브 전송은 예약된 간격으로 전송된 여러 배치로 게재를 분할합니다. 이는 대량 캠페인이 서버 로드 밸런스를 조정하고, ISP 제한을 방지하고, 새 IP를 사용하여 보낸 사람의 신뢰도를 높이고, 예약된 일괄 처리 사이에서 옵트아웃/바운스를 관리하는 데 필수적입니다.

**구성:**

게재 속성에서 웨이브 전송을 활성화하고 웨이브 수(또는 배치 크기), 웨이브 간 간격 및 웨이브 분포(선형 또는 사용자 지정 백분율)를 정의합니다. Campaign은 자동으로 대상 모집단을 분할하고 각 웨이브를 일정에 따라 전송합니다.

대규모 캠페인에 웨이브를 사용하고, 계속하기 전에 첫 번째 웨이브 성능을 모니터링하고, 웨이브 간 충분한 시간을 사용하여 바운스 및 옵트아웃을 처리할 수 있습니다.

[웨이브 전송 구성](../send/configure-and-send.md#sending-using-multiple-waves)

+++

+++ Campaign에서 전자 메일을 만드는 주요 단계는 무엇입니까?

Campaign v8에서 이메일을 만드는 절차에는 게재 만들기, 타겟 대상자 정의, 콘텐츠 디자인, 개인화 추가, 설정 구성(보낸 사람, 제목, 회신), 게재 분석 실행, 테스트를 위한 증명 보내기, 마지막으로 보내거나 예약하는 주요 단계가 포함됩니다.

**주요 단계:**

1. **게재 만들기** - 전자 메일을 채널로 선택하고 선택적으로 게재 템플릿을 선택합니다.
1. **대상 정의** - 쿼리, 목록 또는 가져온 파일을 사용하여 받는 사람 대상 선택
1. **콘텐츠 디자인** - 이메일 편집기(웹 UI 이메일 Designer 또는 클라이언트 콘솔 편집기)를 사용하여 메시지를 만듭니다.
1. **개인화 추가** - 동적 필드, 개인화 블록 및 조건부 콘텐츠 삽입
1. **설정 구성** - 보낸 사람 주소, 제목 줄, 회신 주소 및 게재 매개 변수를 설정합니다.
1. **게재 분석 실행** - Campaign이 콘텐츠를 확인하고 대상을 계산하며 오류를 확인합니다.
1. **증명 보내기** - 승인 그룹으로 전자 메일을 테스트하여 렌더링 및 콘텐츠의 유효성을 검사합니다.
1. **보내기 또는 예약** - 주 대상 또는 일정에 즉시 보내 나중 날짜로 보냅니다.

**두 가지 인터페이스 옵션:**

* **Campaign 웹 UI** - 향상된 이메일 Designer, AI Assistant 및 다국어 기능을 갖춘 최신 인터페이스
* **클라이언트 콘솔** - 고급 타깃팅 및 워크플로 기능을 갖춘 기존 인터페이스

**팁:** 최신 디자인 도구를 사용하여 보다 빠르고 직관적인 이메일을 만들려면 Campaign 웹 UI를 사용하십시오. 복잡한 타겟팅 또는 고급 워크플로우 기반 캠페인에는 클라이언트 콘솔을 사용하십시오.

[첫 번째 전자 메일 만들기](create-message.md) | [전자 메일 디자인 가이드](../send/email.md)

+++

+++ 게재를 예약하는 방법

Campaign을 사용하면 향후 전송을 위해 게재를 예약하여 전송 시간을 최적화하고 캠페인을 조정할 수 있습니다.

**예약 옵션:**

* **게재 속성** - 즉시 보내거나, 특정 날짜/시간에 대해 예약하거나, 시간/일별로 연기합니다.
* **캠페인 수준** - 캠페인 내의 모든 게재를 조정합니다.
* **워크플로우 스케줄러 활동** - 반복 게재, 복잡한 패턴 및 이벤트 트리거 캠페인의 경우

Campaign은 또한 연락 날짜 최적화(수신자당 가장 적합한 전송 시간)와 시간대 적응(모든 수신자에 대해 동일한 현지 시간)을 지원합니다.

[게재 예약 보내기](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ 전자 메일에 첨부 파일을 추가할 수 있습니까?

예. Campaign은 정적 첨부 파일(모든 수신자에 대해 동일한 파일) 및 개인화된 첨부 파일(프로필 데이터에 따라 수신자마다 다른 파일)을 지원합니다. 게재 속성의 **[!UICONTROL Attachments]** 섹션에 첨부 파일을 추가합니다.

**중요 고려 사항:**

* 최적의 전달성을 위해 첨부 파일을 1MB 미만으로 유지
* 첨부 파일이 스팸 필터를 트리거할 수 있습니다. 보내기 전에 철저히 테스트하십시오.
* 이메일 클라이언트(.exe, .zip, .js)에 의해 일반적으로 차단되는 파일 형식을 피하십시오.
* 대용량 파일의 경우 추적된 다운로드 링크를 대신 사용하는 것이 좋습니다.

프로덕션 전송 전에 안전한 파일 형식(PDF, JPEG, PNG, DOCX)을 사용하고 시드 주소로 테스트합니다.

[이메일 첨부 파일 안내서](../send/email.md#attachments)

+++

+++ 이메일 게재에서 추적된 링크를 구성하려면 어떻게 해야 합니까?

Campaign은 이메일의 모든 URL을 추적된 링크로 자동 변환하여 수신자 참여를 모니터링합니다. 게재의 **[!UICONTROL Tracking]** 섹션에 액세스하여 각 링크에 대한 추적 설정을 구성합니다.

**구성 옵션:**

* **추적 활성화/비활성화** - 링크당 추적 제어
* **링크 레이블** - 보고를 위한 수사적 이름을 추가합니다(예: &quot;Shop Now CTA&quot;).
* **링크 범주** - 집계된 분석을 위해 유형별 링크 그룹화
* **추적 형식** - 클릭 수, 열기 수 또는 둘 다 추적

Campaign은 콘텐츠 링크, 미러 페이지 링크, 구독 취소 링크를 추적하며, 이메일 열기를 위한 선택적 추적 픽셀을 포함할 수 있습니다. 의미 있는 레이블 및 범주를 사용하여 보고를 단순화하고 높은 성과를 보이는 콘텐츠를 신속하게 식별할 수 있습니다.

[링크 추적 가이드](../start/tracking.md) | [추적 모범 사례](../send/send.md)

+++

+++ 게재 및 추적 로그는 어디에서 액세스할 수 있습니까?

각 게재 대시보드에서 직접 게재 및 추적 로그에 액세스합니다. 클라이언트 콘솔에서 하단의 **[!UICONTROL Delivery]** 탭을 클릭합니다. Campaign 웹 UI에서 **[!UICONTROL Logs]** 섹션으로 이동합니다.

**사용 가능한 로그:**

* **게재 로그** - 받는 사람 세부 정보 및 상태가 포함된 보낸 메시지(보냄, 보류, 실패)
* **추적 로그** - 타임스탬프를 사용한 수신자 상호 작용(열기, 클릭)
* **제외 로그** - 이유(격리, 유형화 규칙, 중복)가 있는 제외된 받는 사람
* **브로드캐스트 로그** - 다시 시도 및 오류를 포함한 전송 기록 완료

이러한 로그를 사용하여 게재 문제를 해결하고, 참여를 분석하고, 목록 위생 상태를 유지합니다.

[게재 모니터링](../send/send.md) | [추적 가이드](../start/tracking.md)

+++

+++ 게재 보고서는 어디에서 얻을 수 있습니까?

Campaign은 게재 성과, 수신자 참여 및 캠페인 효과를 분석하는 포괄적인 기본 제공 보고서를 제공합니다. 모든 게재의 **[!UICONTROL Reports]** 탭, 캠페인 대시보드 또는 캠페인 간 분석을 위한 글로벌 **[!UICONTROL Reports]** 메뉴에서 보고서에 액세스합니다.

**주요 보고서 포함:**

* **게재 요약** - 통계, 열기, 클릭, 바운스 및 구독 취소 전송
* **핫 클릭** - 링크 성능의 시각적 히트맵
* **추적 표시기** - 클릭스루 비율 및 참여 지표
* **게재 불가** - 실패 이유가 있는 바운스 분석

보고서는 클라이언트 콘솔과 최신 시각화가 포함된 Campaign 웹 UI 모두에서 사용할 수 있습니다.

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

[격리 관리 가이드](../send/quarantines.md) | [바운스 관리](../send/delivery-failures.md)

+++

## 워크플로 {#workflows}

워크플로우를 사용하여 Adobe Campaign에서 프로세스를 자동화하고, 데이터를 관리하고, 복잡한 마케팅 캠페인을 오케스트레이션하는 방법을 살펴봅니다.

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

[워크플로우 구축](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=ko){target="_blank"} | [워크플로우 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"} | [워크플로우 모범 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=ko){target="_blank"} | [워크플로우 사용 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ Campaign에서 데이터를 가져오려면 어떻게 해야 합니까?

필요에 따라 여러 메서드를 사용하여 데이터를 Campaign에 가져옵니다.

**간단한 파일 가져오기:**

* 가져오기 마법사를 사용하여 안내가 있는 인터페이스를 통한 일회성 CSV/TXT 가져오기
* 수동 업로드 및 빠른 데이터 로드에 이상적

**워크플로 기반 가져오기:**

* 복잡한 가져오기에 대해 **[!UICONTROL Data loading (file)]** 활동을 사용하여 워크플로우 만들기
* 데이터 변환, 데이터 보강 및 데이터 중복 제거 추가
* SFTP, 로컬 디렉터리 또는 클라우드 저장소에서 반복 가져오기 예약

**API 통합:**

* 외부 시스템에서 프로그래밍 방식으로 데이터를 가져오려면 REST API를 사용하십시오
* CRM, 전자 상거래 또는 기타 플랫폼과 실시간 동기화에 이상적

**모범 사례:** 항상 작은 샘플로 테스트하고, UTF-8 인코딩을 사용하고, 필드를 올바르게 매핑하고, 중복 제거 규칙을 적용하고, 사용량이 적은 시간 동안 큰 가져오기를 예약하십시오.

**관련 항목:**

[가져오기 모범 사례](../start/import.md) | [데이터 로드 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=ko){target="_blank"} | [가져오기 워크플로우 반복](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=ko){target="_blank"}

+++

+++ Campaign의 일반적인 워크플로우 사용 사례는 무엇입니까?

Campaign 워크플로우는 거의 모든 마케팅 프로세스를 자동화할 수 있습니다. 다음은 가장 일반적인 사용 사례입니다.

**데이터 관리:**

* **데이터 가져오기 및 로드** - SFTP, API 또는 클라우드 저장소에서 파일 가져오기 자동화
* **데이터 정리** - 프로필 중복 제거, 형식 표준화, 잘못된 레코드 제거
* **데이터 보강** - 외부 데이터 또는 계산된 필드를 사용하여 프로필을 개선합니다.
* **목록 관리** - 동작 또는 조건에 따라 세그먼트를 자동으로 업데이트

**Campaign 자동화:**

* **시작 시리즈** - 새 구독자에 대한 자동 온보딩 전자 메일 트리거
* **생일 캠페인** - 고객의 생일 또는 기념일에 개인화된 메시지를 보냅니다.
* **다시 참여** - 비활성 구독자를 Win-back 캠페인으로 타깃팅합니다.
* **장바구니 포기** - 장바구니에 항목을 남긴 고객에게 미리 알림 보내기

**고급 타깃팅:**

* **A/B 테스트** - 대상을 분할하고 다른 콘텐츠 변형을 테스트합니다.
* **동적 세분화** - 실시간 동작 또는 특성을 기반으로 세그먼트를 만듭니다.
* **리드 점수** - 참여를 기반으로 리드 점수를 계산하고 업데이트합니다.
* **크로스 채널 오케스트레이션** - 전자 메일, SMS 및 푸시 메시지 조정

**모니터링 및 경고:**

* **워크플로 모니터링** - 워크플로 상태를 추적하고 실패 시 경고를 보냅니다.
* **게재 모니터링** - 캠페인 성과 및 바운스 비율 모니터링
* **데이터베이스 유지 관리** - 이전 로그 및 임시 데이터 자동 정리

**통합 및 동기화:**

* **CRM 동기화** - 고객 데이터를 Salesforce, Dynamics 등과 계속 동기화합니다.
* **API 통합** - 전자 상거래 플랫폼, 분석 도구 또는 사용자 지정 시스템과 연결
* **이벤트가 트리거된 워크플로** - 웹 사이트 또는 앱의 실시간 이벤트에 반응합니다.

**관련 항목:**

[워크플로우 사용 사례 라이브러리](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [워크플로우 구축](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=ko){target="_blank"} | [워크플로우 모범 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=ko){target="_blank"} | [워크플로우 타깃팅](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html?lang=ko){target="_blank"} | [데이터 관리 워크플로](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/about-data-management.html){target="_blank"}

+++

+++ 워크플로우로 Campaign 데이터를 업데이트하려면 어떻게 해야 합니까?

워크플로우의 **[!UICONTROL Update data]** 활동을 사용하여 데이터베이스에서 대량 작업을 수행합니다.

**지원되는 작업:**

* **삽입** - 데이터베이스에 새 레코드 추가
* **업데이트** - 일치하는 조건에 따라 기존 레코드를 수정합니다.
* **삽입 또는 업데이트** - 새 레코드를 추가하거나 기존 레코드를 업데이트(업데이트)
* **삭제** - 특정 조건과 일치하는 레코드 제거

**일반적인 사용 사례:**

* 데이터 보강 후 프로필 속성 업데이트
* 외부 시스템과 데이터 동기화
* 동작을 기반으로 목록 멤버십 유지 관리
* 데이터 정리 및 중복 제거
* 벌크 상태 변경 적용(예: 옵트아웃, 격리)

레코드를 정확하게 일치하도록 조정 키를 구성하고 업데이트 옵션(모든 필드를 업데이트하거나 빈 필드만 업데이트)을 선택합니다.

**관련 항목:**

[데이터 활동 업데이트](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=ko){target="_blank"} | [데이터 관리 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ 데이터 관리 기능을 활용하려면 어떻게 해야 합니까?

Campaign의 데이터 관리 활동을 통해 복잡한 타겟팅 및 세그멘테이션을 위해 워크플로우 내에서 정교한 데이터 작업을 수행할 수 있습니다.

**주요 데이터 관리 활동:**

* **데이터 보강** - 관련 테이블 또는 외부 원본의 데이터를 작업 모집단에 추가합니다.
* **분할** - 조건에 따라 모집단을 세그먼트화하거나 임의로 분할합니다.
* **중복 제거** - 지정된 키를 기준으로 중복 레코드를 제거합니다.
* **데이터 업데이트** - 일괄 삽입, 업데이트 또는 삭제 작업을 수행합니다.
* **차원 변경** - 타겟팅 차원 전환(예: 수신자에서 구독으로)
* **교차/결합/제외** - 여러 모집단을 결합하거나 필터링합니다.

**일반적인 사용 사례:**

* 구매 내역 또는 비헤이비어 데이터로 프로필 보강
* 서로 다른 메시지를 위해 대상을 여러 그룹으로 세그먼트화
* 게재 전 중복 제거
* 외부 데이터베이스의 데이터 통합(FDA - Federated Data Access)
* 복잡한 다중 테이블 쿼리 및 조인 만들기

이러한 활동을 사용하면 주 수신자 테이블에서 직접 데이터를 사용하지 않고 고급 데이터베이스 작업을 수행할 수 있습니다.

**관련 항목:**

[데이터 관리 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"} | [워크플로 타깃팅](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html?lang=ko){target="_blank"} | [데이터 보강 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=ko){target="_blank"}

+++

+++ 개인화된 메시지 전송을 자동화할 수 있습니까?

예. 워크플로우를 통해 수신자 데이터, 동작 및 사용자 지정 기준에 따라 완전히 자동화된 개인화된 메시지 캠페인을 사용할 수 있습니다.

**자동화 워크플로 구조:**

1. **쿼리** - 조건에 따라 대상 대상 선택
1. **데이터 보강** - 관련 테이블에서 개인화 데이터 추가
1. **분할** - 다른 메시지 변형에 대한 그룹으로 세그먼트화(선택 사항)
1. **게재** - 병합 필드를 사용하여 개인화된 메시지를 보냅니다.
1. **스케줄러** - 자동화된 캠페인에 대한 반복 실행을 설정합니다.

**Personalization 옵션:**

* 수신자 프로필 데이터(이름, 위치, 환경 설정) 사용
* 행동 데이터(구매 내역, 참여 점수) 포함
* 세그먼트 또는 속성을 기반으로 조건부 콘텐츠 적용
* 동적 값(충성도 포인트, 만료 날짜) 계산

일반적인 시나리오: 생일 캠페인, 장바구니 포기, 충성도 프로그램, 되찾기 캠페인 및 이벤트 트리거 메시지.

**관련 항목:**

[Personalization 안내서](../send/personalize.md) | [워크플로우 사용 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=ko){target="_blank"} | [데이터 보강 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=ko){target="_blank"}

+++

+++ 워크플로우로 하위 집합에서 대상을 분할하려면 어떻게 해야 합니까?

**[!UICONTROL Split]** 활동을 사용하여 기준이나 배포 규칙에 따라 단일 모집단을 여러 하위 집합으로 나눕니다.

**분할 메서드:**

* **필터링 조건** - 기준(예: 연령 그룹, 위치, VIP 상태)을 기반으로 하위 집합을 만듭니다.
* **백분율 분포** - A/B 테스트를 위해 무작위로 동일하거나 사용자 지정 백분율로 분할합니다.
* **레코드 제한** - 하위 집합 크기 제한(처음 N개 레코드, 상위 X%, 무작위 선택)
* **데이터 그룹화** - 고유 값당 하나의 하위 집합(예: 국가당 하나의 하위 집합)을 만듭니다.

**일반적인 사용 사례:**

* 컨트롤 그룹으로 A/B 테스트
* 채널 환경 설정 라우팅(이메일과 SMS)
* 점진적 롤아웃(10%, 90%로 보내기)
* 세그먼트별 메시징(VIP, 일반, 신규 고객)
* 여러 게재 서버 간 로드 밸런싱

각각의 분할된 서브세트는 별개의 전환으로 흘러가며, 각각의 그룹에 대해 상이한 프로세싱 또는 전달을 허용한다.

**관련 항목:**

[활동 분할](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html?lang=ko){target="_blank"} | [A/B 테스트 가이드](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ 외부 파일에서 수신자 데이터를 업데이트하려면 어떻게 해야 합니까?

예. 워크플로우를 사용하여 외부 파일(CSV, TXT)의 값으로 Campaign 데이터를 업데이트합니다.

**워크플로 구조:**

1. **데이터 로드(파일)** - 외부 파일 로드 및 열 매핑
1. **데이터 보강**(선택 사항) - 추가 데이터 또는 변형 추가
1. **조정** - 파일 레코드와 데이터베이스 레코드(예: 전자 메일 주소, 받는 사람 ID)를 일치시키는 키를 정의합니다.
1. **데이터 업데이트** - 업데이트 옵션 선택:
   * 일치하는 레코드만 업데이트
   * 기존 필드 또는 빈 필드만 업데이트
   * 일치하는 항목을 찾을 수 없는 경우 새 레코드 삽입

**일반적인 시나리오:**

* CRM 내보내기에서 프로필 속성 업데이트
* 외부 시스템에서 구독 상태 새로 고침
* 충성도 점수 또는 고객 점수 동기화
* 옵트인/옵트아웃 환경 설정 업데이트
* 동작 데이터를 사용하여 프로필 강화

**모범 사례:** 조정에 고유 식별자를 사용하고, 업데이트 전에 데이터를 확인하고, 작은 샘플로 테스트하고, 지속적인 동기화를 위해 정기적인 업데이트를 예약합니다.

**관련 항목:**

[데이터 가져오기 안내서](../start/import.md) | [데이터 로드 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=ko){target="_blank"} | [데이터 활동 업데이트](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=ko){target="_blank"}

+++

+++ 신규 수신자를 식별하고 타겟팅하려면 어떻게 해야 합니까?

쿼리 활동과 함께 워크플로우를 사용하여 최근에 추가된 수신자를 식별하고 자동화된 시작 캠페인을 트리거합니다.

**쿼리 접근 방식:**

**[!UICONTROL Created date]** 필드에 쿼리 필터링을 만들어 특정 기간 내에 추가된 수신자를 선택합니다(예: 지난 24시간, 지난 주).

**자동화된 시작 워크플로 구조:**

1. **스케줄러** - 매일 또는 특정 간격으로 실행
1. **쿼리** - 마지막 실행 이후 만든 받는 사람 선택
1. **중복 제거**(선택 사항) - 중복 항목 없음
1. **게재** - 환영 메시지 보내기
1. **데이터 업데이트**(선택 사항) - 받는 사람을 &quot;환영&quot;으로 표시

**집계 포함 고급 기법:**

집계 함수를 사용하여 가장 최근 추가 항목을 동적으로 식별하고, 정교한 새 수신자 검색을 위해 이전에 처리된 수신자와 비교합니다.

**관련 항목:**

[쿼리 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=ko){target="_blank"} | [집계 사용](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=ko){target="_blank"} | [시작 프로그램](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=ko){target="_blank"}

+++

+++ 워크플로우 활동은 어떻게 사용합니까?

캠페인 워크플로우는 각각 특정 목적을 제공하는 네 가지 주요 활동 범주를 사용하여 빌드됩니다.

**타깃팅 활동** - 대상 정의 및 세분화

* 쿼리, 분할, 중복 제거, 데이터 보강, 교차, 결합, 제외
* 이를 사용하여 수신자를 선택하고, 모집단을 세그먼트화하고, 데이터 소스를 결합합니다

**흐름 제어 활동** - 워크플로 논리 및 시간 관리

* 스케줄러, 대기, 테스트, 포크 및 조인, OR-조인, 이동
* 실행 흐름 제어, 조건 추가 및 병렬 경로 관리

**작업 활동** - 작업 수행 및 메시지 보내기

* 게재, 데이터 업데이트, 데이터 로드(파일), 데이터 추출(파일), JavaScript 코드
* 데이터베이스 작업, 파일 전송 및 메시지 전송 실행

**이벤트 활동** - 외부 트리거에 반응

* 외부 신호, 파일 수집기, HTTP 전송, SMS, 이메일
* 수신 데이터 및 외부 시스템 상호 작용 처리

활동을 사용하려면 팔레트에서 워크플로 캔버스로 드래그하고 두 번 클릭하여 매개 변수를 구성한 다음 전환과 연결합니다.

**관련 항목:**

[타깃팅 활동 참조](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=ko){target="_blank"} | [흐름 제어 활동 참조](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=ko){target="_blank"} | [작업 활동 참조](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=ko){target="_blank"} | [이벤트 활동 참조](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html?lang=ko){target="_blank"}

+++

+++ 워크플로우 모범 사례란 무엇입니까?

효율적이고 유지 관리적이며 안정적인 워크플로를 구축하려면 다음 모범 사례를 따르십시오.

**디자인 및 조직:**

* 워크플로우 및 활동에 명확하고 설명적인 이름 사용
* 문서 논리에 레이블 및 설명 추가
* 가독성을 위해 시각적으로 관련 활동 그룹화
* 복잡한 프로세스를 여러 개의 소규모 워크플로우로 나눕니다.

**성능 최적화:**

* 적절한 필터로 쿼리 결과 크기 제한
* 중간 데이터 저장소에 임시 테이블 사용
* 사용량이 적은 시간 동안 리소스 집약적인 워크플로 예약
* 불필요한 루프 및 과도한 반복 방지

**오류 처리 및 모니터링:**

* 감독자가 있는 오류 처리 경로 추가
* 실패한 워크플로우에 대한 경고 구성
* 전체 실행 전에 작은 데이터 샘플로 테스트
* 성능 문제에 대한 실행 로그를 정기적으로 검토합니다.

**유지 관리 및 거버넌스:**

* 오래된 워크플로 보관 또는 삭제
* 버전 제어 워크플로 변경 사항 및 문서 수정
* 워크플로우 복잡성 제한(20개 이하의 활동 목표)
* 반복 패턴에 워크플로우 템플릿 사용

**보안 및 데이터 관리:**

* 적절한 연산자 권한 적용
* 워크플로우 정리로 임시 데이터 정리
* 값을 하드 코딩하지 않음 - 변수 및 옵션 사용
* 성과가 낮은 워크플로를 정기적으로 검토하고 최적화합니다.

**관련 항목:**

[워크플로우 모범 사례 가이드](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=ko){target="_blank"} | [워크플로우 구축](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=ko){target="_blank"} | [워크플로우 모니터링](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=ko){target="_blank"}

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


[Campaign 웹 UI에서 언어 변경](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [Campaign 클라이언트 콘솔 시작](connect.md)

+++

+++ 다른 Adobe 솔루션과 함께 Campaign v8을 사용할 수 있습니까?

예. Campaign v8은 Adobe Experience Cloud 솔루션과 원활하게 통합되어 강력한 통합 마케팅 에코시스템을 구축합니다. 관리 Cloud Service인 v8은 Adobe의 엔터프라이즈 애플리케이션과 기본적으로 통합되도록 설계되었습니다.

**주요 통합 사용 가능:**

* **Adobe Experience Platform** - 통합 고객 프로필 및 실시간 데이터 활용
* **Adobe Analytics** - 채널 간 캠페인 성과 및 고객 행동을 측정합니다.
* **Adobe Target** - 고객 세그먼트 및 동작을 기반으로 콘텐츠 개인화
* **Adobe Experience Manager** - 콘텐츠 만들기 및 에셋 관리 중앙 집중화
* **Adobe Audience Manager** - 플랫폼 간 대상 세그먼트 빌드 및 활성화

**이점:** 통합 고객 데이터, 일관된 사용자 환경, 간소화된 워크플로 및 향상된 개인화 기능.

**설정:** Adobe 솔루션과 통합하려면 Campaign v8 관리 클라우드 서비스에 대해 자동으로 구성된 Adobe Identity Management System(IMS) 인증이 필요합니다.

[Adobe Campaign 통합](../connect/integration.md) | [Adobe ID과 연결](connect.md)

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

[게재 추적 및 모니터링](tracking.md) | [추적된 링크 구성](../send/email.md)

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

[Campaign의 게재 기능 기본 정보](../send/about-deliverability.md) | [게재 기능 모범 사례 안내서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=ko){target="_blank"}

+++

+++ Campaign을 연결할 수 있는 외부 데이터베이스는 무엇입니까?

Campaign v8은 주요 엔터프라이즈 데이터베이스 시스템에 대한 FDA(Federated Data Access) 연결을 지원하므로 기존 데이터 인프라를 활용할 수 있습니다.

**지원되는 데이터베이스:**

* **클라우드 데이터베이스:** Amazon Redshift, Google BigQuery, Snowflake, Azure Synapse Analytics
* **엔터프라이즈 데이터베이스:** Oracle, Microsoft SQL Server, PostgreSQL, MySQL
* **데이터 웨어하우스:** Teradata, Vertica, SAP HANA
* **빅 데이터:** 하이브를 통한 Hadoop

**플랫폼별 고려 사항:** 지원되는 데이터베이스 버전 및 연결 요구 사항은 다양합니다. Campaign v8 as a Managed Cloud Service에는 외부 데이터베이스 액세스에 대한 특정 네트워크 및 보안 요구 사항이 있을 수 있습니다.

**중요:** 항상 Campaign v8 버전에 대한 공식 호환성 매트릭스를 확인하여 특정 데이터베이스 버전에 대한 지원을 확인하고 외부 데이터베이스 커넥터에 대한 적절한 라이선스를 확인하십시오.

[호환성 매트릭스](compatibility-matrix.md) | [FDA 연결 구성](../connect/fda.md)

+++

+++ Adobe Campaign을 CRM 시스템과 통합할 수 있습니까?

예. Campaign은 Campaign과 CRM 시스템 간의 원활한 양방향 동기화를 위한 기본 CRM 커넥터를 제공하여 플랫폼 간에 고객 데이터의 일관성을 보장합니다.

**지원되는 CRM 시스템:**

* **Salesforce** - 잠재 고객, 연락처, 계정, 기회, 캠페인
* **Microsoft Dynamics 365** - 연락처, 계정, 잠재 고객, 사용자 지정 엔터티
* 사용자 정의 API 통합을 통한 기타 CRM

**동기화 내용:**

* **CRM에서 캠페인으로:** 연락처 레코드, 계정 정보, 잠재 고객, 사용자 지정 필드, 세분화 데이터
* **Campaign에서 CRM으로:** 게재 로그, 추적 데이터, 참여 지표, 캠페인 응답, 구독 상태

**동기화 모드:**

* **예약됨** - 정의된 간격(시간별, 일별)으로 자동 동기화
* **수동** - 연산자에 의해 트리거된 주문형 동기화
* **실시간** - 즉시 업데이트(사용자 지정 개발)를 위해 API를 통해

**구성:** Campaign의 기본 제공 CRM 커넥터 도우미를 사용하여 CRM 필드를 Campaign 특성에 매핑하고, 동기화할 테이블을 선택하고, 동기화를 예약합니다. 커넥터가 충돌 해결을 처리하고 데이터 일관성을 유지합니다.

**모범 사례:** 읽기 전용 동기화로 시작하여 매핑을 테스트한 다음 양방향 동기화를 사용하도록 설정하십시오. 동기화 로그에서 오류를 모니터링하고 두 시스템에서 깨끗한 데이터를 유지합니다.

[CRM 커넥터 구성](../connect/crm.md) | [워크플로 CRM 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html?lang=ko){target="_blank"}

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



[클라이언트 콘솔 설치 및 구성](connect.md)

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
* **연산자 그룹** - 모든 그룹 멤버가 상속한 설정


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


[데이터 모델 확장](../dev/extend-schema.md) | [스키마 구조](../dev/schemas.md) | [데이터 모델 모범 사례](../dev/datamodel-best-practices.md)

+++

## 보고 {#reporting}

기본 제공 보고서, 사용자 지정 보고서 및 큐브와 같은 데이터 분석 도구를 포함한 Campaign의 보고 기능에 대한 통찰력을 얻으십시오.

+++ 새 보고서를 만들려면 어떻게 해야 합니까?

Campaign은 요구 사항과 기술 전문 지식에 따라 여러 보고 옵션을 제공합니다. 기본 제공 보고서를 사용하거나, 클라이언트 콘솔에서 사용자 지정 보고서를 만들거나, Campaign 웹 UI에서 시각적 대시보드를 디자인할 수 있습니다.

**보고 옵션:**

* **기본 제공 보고서** - **[!UICONTROL Reports]** 탭에서 액세스할 수 있는 바로 사용 가능한 게재, 캠페인 및 추적 보고서
* **설명 분석** - 마법사 기반 인터페이스를 사용하여 데이터에 대한 빠른 통계 보고서
* **사용자 지정 보고서** - 기술 사용자가 보고 편집기를 사용하여 작성한 고급 보고서
* **웹 UI 대시보드** - 드래그 앤 드롭 인터페이스가 있는 최신 시각적 보고서 및 대시보드
* **큐브** - 다차원 데이터 탐색 및 피벗 테이블 분석

**중요:** Campaign은 전문 비즈니스 인텔리전스 도구가 아니라 마케팅 작업 보고를 위해 설계되었습니다. 복잡한 분석 요구 사항에 대해서는 Adobe Analytics 또는 전용 BI 플랫폼과 통합하는 것을 고려하십시오.

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

[기술 분석](../reporting/built-in-reports.md)

+++

+++ 데이터에 대한 고급 보고서를 디자인하려면 어떻게 해야 합니까?

Campaign은 고급 사용자 지정 보고서를 만들기 위한 두 가지 접근 방식, 즉 복잡한 분석을 위한 클라이언트 콘솔의 기술 보고서와 보다 쉬운 보고서 작성을 위한 시각적 대시보드를 제공합니다.

클라이언트 콘솔에서 다음을 수행할 수 있습니다.

* SQL 쿼리 및 사용자 지정 계산을 사용하여 복잡한 보고서 작성
* 차트, 테이블 및 피벗 테이블을 사용하여 다중 페이지 보고서 만들기
* 조건부 서식 및 다이내믹 콘텐츠 디자인
* 전체 Campaign 데이터 모델 및 외부 데이터베이스(FDA) 액세스


[사용자 지정 보고서 만들기(클라이언트 콘솔)](../reporting/custom-reports.md)

+++

+++ 큐브란 무엇이며 보고에 큐브를 사용하려면 어떻게 해야 합니까?

큐브는 비즈니스 사용자가 기술 없이도 피벗 테이블을 통해 Campaign 데이터를 탐색하고 분석할 수 있는 다차원 데이터 구조입니다. 이를 복잡한 보고를 간소화하는 사전 구성된 데이터 모델로 간주합니다.


* 기술 사용자 는 차원 (시간, 지역, 채널) 및 측정값 (열기, 클릭 수, 매출)을 정의하는 큐브를 만들고 구성합니다.
* 비즈니스 사용자는 보고서를 만들 때 큐브를 선택하고 데이터를 탐색하기 위해 차원을 끌어서 놓습니다
* 데이터는 큐브 구성을 기반으로 자동으로 집계되고 계산됩니다
* 결과를 피벗 테이블, 차트 또는 Excel로 내보낼 수 있습니다


[큐브로 데이터 탐색](../reporting/gs-cubes.md)

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

**기본 제공 설문 조사 보고서:**

* **일반 보고서** - 시간 경과에 따른 응답 트렌드, 원본 및 언어별 분포
* **응답 분류** - 각 질문에 대한 자세한 답변 분류
* **설명서 보고서** - 설문 조사 구조의 시각적 표시

**고급 분석:**

* **[!UICONTROL Responses]** 탭에서 설문 조사 응답에 액세스하고 데이터를 내보냅니다
* 워크플로우에서 **[!UICONTROL Survey responses]** 활동을 사용하여 답변을 기반으로 수신자를 타겟팅합니다.
* 세분화 및 개인화를 위해 설문 조사 데이터를 다른 Campaign 데이터와 결합
* 다차원 설문 조사 분석을 위한 사용자 지정 보고서 및 큐브 만들기


[설문 조사 시작](https://experienceleague.adobe.com/ko/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [설문 조사 보고서](https://experienceleague.adobe.com/ko/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ 보고서에 대한 액세스 권한을 공유하려면 어떻게 해야 합니까?

Campaign은 다양한 사용자 그룹과 보고서를 공유하고 역할 및 책임에 따라 가시성 및 액세스 권한을 제어하는 유연한 옵션을 제공합니다.

**보고서 액세스 제어:**

* **폴더 권한** - 사용자 그룹에 대한 적절한 읽기/쓰기 권한이 있는 폴더에 보고서를 배치합니다.
* **명명된 권한** - 보고서를 보거나 만들거나 수정할 수 있는 특정 권한을 할당합니다.
* **컨텍스트 표시** - **[!UICONTROL Reports]** 폴더, 캠페인 탭 또는 게재 화면에서 보고서가 표시되는 위치를 정의합니다.
* **웹 UI 공유** - Campaign 웹 UI를 통해 팀 구성원과 대시보드 링크를 공유합니다.

**액세스를 구성하는 방법:**

1. 클라이언트 콘솔의 특정 폴더에 보고서 저장
2. 관련 운영자 그룹에 대한 폴더 액세스 권한 구성
3. 보고서 유형, 표시 컨텍스트 및 가용성과 같은 보고서 등록 정보를 정의합니다.
4. 광범위한 롤아웃 전에 대상 그룹의 사용자와 액세스를 테스트하십시오.

**모범 사례:** 맞춤화된 액세스 권한을 사용하여 다양한 팀(마케팅, 운영, 관리)에 대한 전용 보고서 폴더를 만듭니다. 보고서 목적을 문서화하고 일정을 새로 고칩니다.

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

[사용자 지정 보고서](../reporting/custom-reports.md) | [Campaign 웹 UI 보고서](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

## 개발자 {#developers}

데이터 모델 세부 정보, 스키마, API 및 사용자 지정 기능을 포함하여 개발자를 위한 기술 정보에 액세스합니다.

+++ Campaign 데이터 모델은 무엇입니까?

Campaign의 데이터 모델은 마케팅 데이터가 구성되고 관련되는 방식을 정의하는 스키마 기반 관계형 데이터베이스 구조입니다. 핵심 마케팅 개체(수신자, 게재, 캠페인)에 대한 기본 제공 테이블로 구성되며 특정 비즈니스 요구 사항을 충족하도록 확장할 수 있습니다.

**주요 데이터 모델 개념:**

* **스키마** - 테이블 구조, 필드 및 관계를 설명하는 XML 정의
* **기본 제공 테이블** - 핵심 마케팅 엔터티(수신자, 게재, 워크플로, 캠페인)
* **링크** - 테이블 간의 관계(1-1, 1-N, N-N)
* **열거형** - 드롭다운 필드에 대해 미리 정의된 값 목록
* **확장** - 표준 모델에 추가된 사용자 지정 필드 및 테이블

**기본 제공 스키마:**

* **받는 사람(nms:recipient)** - 고객 프로필 및 연락처 정보
* **게재(nms:delivery)** - 이메일, SMS 및 푸시 캠페인
* **워크플로(xtk:workflow)** - 자동화 프로세스
* **캠페인(nms:operation)** - 마케팅 캠페인 오케스트레이션
* **추적 로그** - 열기, 클릭 수 및 참여 데이터

**중요한 이유:** 워크플로우를 만들고, 쿼리를 빌드하고, 스키마를 확장하고, 사용자 지정 통합을 개발하는 데 데이터 모델을 이해하는 것은 필수적입니다. 스키마 기반 접근 방식은 데이터 일관성을 보장하고 강력한 쿼리 기능을 가능하게 합니다.

[Campaign 데이터 모델](../dev/datamodel.md) | [데이터 모델 모범 사례](../dev/datamodel-best-practices.md)

+++

+++ Campaign 스키마로 작업하는 방법

스키마는 Campaign 데이터 구조의 기반이며 테이블, 필드 및 관계를 XML 형식으로 정의합니다. 스키마를 이해하는 것은 사용자 지정, 통합 및 고급 워크플로우 개발에 중요합니다.

**스키마가 정의하는 항목:**

* **테이블 구조** - 데이터베이스 테이블 및 해당 응용 프로그램 개체
* **필드 속성** - 데이터 형식, 레이블, 유효성 검사 규칙 및 기본값
* **관계** - 테이블(조인)과 카디널리티 간의 링크
* **인덱스** - 쿼리 성능을 위한 데이터베이스 최적화
* **액세스 제어** - 사용자가 보고 수정할 수 있는 필드

**스키마 작업:**

* **스키마 보기:** 클라이언트 콘솔에서 **[!UICONTROL Administration > Configuration > Data schemas]**&#x200B;을(를) 통한 액세스
* **스키마 확장:** 확장 스키마(예: `cus:recipient` 확장 `nms:recipient`)를 만들어 코어 스키마를 수정하지 않고 사용자 지정 필드를 추가합니다.
* **사용자 지정 스키마 만들기:** 비즈니스별 데이터에 대해 완전히 새 테이블을 만듭니다.
* **데이터베이스 업데이트:** **[!UICONTROL Tools > Advanced > Update database structure]**&#x200B;을(를) 사용하여 스키마 변경 적용

**일반적인 사용 사례:**

* 수신자 테이블(회사 ID, 충성도 계층, 환경 설정)에 사용자 정의 필드 추가
* 제품, 스토어 또는 트랜잭션에 대한 사용자 지정 테이블 만들기
* 사용자 지정 테이블과 기본 제공 테이블 간의 관계 정의
* 비즈니스별 데이터 모델 구현

**중요:** 기본 제공 스키마를 직접 수정하지 마십시오. 업그레이드 호환성과 Adobe 지원을 유지하려면 항상 확장 스키마를 사용하십시오.

[스키마 시작](../dev/schemas.md) | [스키마 확장](../dev/extend-schema.md)

+++

+++ 사용자 지정 수신자 테이블을 사용하는 방법

Campaign을 사용하면 타깃팅에 다른 데이터 구조(예: B2B 계정, 구독자, 잠재 고객 또는 외부 연락처)가 필요한 경우 기본 제공 수신자 테이블 대신 사용자 지정 테이블을 사용할 수 있습니다.

**사용자 지정 받는 사람 테이블을 사용하는 이유:**

* 개인 연락처 대신 B2B 회사 또는 조직 단위를 타깃팅합니다.
* 주 고객 데이터베이스에서 가입자 데이터 분리
* 다른 시스템의 기존 고객 테이블 사용
* 별도의 연락처 테이블을 사용하여 다중 브랜드 아키텍처 구현
* 특정 데이터 거버넌스 요구 사항 준수

**구현 단계:**

1. 수신자 테이블 구조를 정의하는 사용자 정의 스키마 만들기
2. 필수 필드(이메일, 기본 키, 제외 플래그) 포함
3. 테이블을 게재와 연결하도록 대상 매핑 구성
4. 새 대상 매핑을 사용하도록 게재 템플릿 업데이트
5. 사용자 지정 테이블을 참조하도록 워크플로우 및 쿼리 조정

**주요 고려 사항:**

* 사용자 정의 수신자 테이블에는 게재에 대한 필수 필드(이메일, 제외, 추적)가 포함되어야 합니다.
* 워크플로 및 양식은 사용자 정의 구조와 작동하도록 조정되어야 합니다
* 일부 기본 기능에는 사용자 정의가 필요할 수 있습니다
* 프로덕션 캠페인을 마이그레이션하기 전에 테스트하는 것이 중요합니다.

**모범 사례:** 사용자 지정 테이블을 고려하기 전에 표준 받는 사람 테이블을 확장하여 시작합니다. 사용자 지정 수신자 테이블은 복잡성을 추가하며 실제로 필요한 경우에만 사용해야 합니다.

[사용자 지정 받는 사람 테이블](../dev/custom-recipient.md) | [대상 매핑](../audiences/target-mappings.md)

+++

+++ Campaign에서 쿼리를 정의하는 모범 사례는 무엇입니까?

Campaign의 쿼리 편집기는 SQL 지식 없이 데이터베이스 쿼리를 빌드할 수 있는 강력한 시각적 도구입니다. 이를 마스터하는 것은 효과적인 타겟팅, 세그멘테이션 및 데이터 분석에 필수적입니다.

**쿼리가 사용되는 위치:**

* **워크플로우 활동** - 쿼리, 분할, 데이터 업데이트, 데이터 보강 활동
* **게재 타깃팅** - 캠페인에 대한 수신자 모집단 정의
* **목록** - 동적 또는 정적 받는 사람 목록 만들기
* **보고서** - 사용자 지정 데이터 추출 및 분석 빌드
* **필터** - 재사용 가능한 타깃팅 기준 만들기

**쿼리 모범 사례:**

* **단순하게 시작** - 쿼리를 점진적으로 빌드하고 각 단계에서 테스트합니다.
* **필터링 차원 사용** - 테이블(수신자 → 게재 → 추적 로그) 간의 관계를 활용합니다.
* **성능 최적화** - 자주 쿼리되는 필드를 인덱싱하므로 복잡한 계산 필드를 사용하지 마십시오.
* **사전 정의된 필터 활용** - 일관성을 위해 기존 필터를 재사용 및 결합
* **작은 샘플로 테스트** - 전체 데이터베이스에서 실행하기 전에 쿼리 논리의 유효성을 검사합니다.
* **복잡한 쿼리 문서** - 유지 관리 및 지식 전달에 대한 설명 추가

**일반적인 쿼리 패턴:**

* 특정 게재를 연 대상 수신자: 수신자에 연결된 추적 로그를 필터링합니다
* 비활성 연락처 찾기: 마지막 게재 일자 또는 추적 활동에 대해 쿼리
* 비헤이비어로 세그먼트: 게재, 추적 및 프로필 기준 결합
* 이전 수신자 제외: 세트 작업 사용(결합, 교차, 제외)

**워크플로우 외부에서 임시 데이터베이스 탐색 및 데이터 추출을 위해 일반 쿼리 편집기에 액세스:** **[!UICONTROL Tools > Generic query editor]**.

[쿼리 편집기](../start/query-editor.md) | [워크플로우의 쿼리 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=ko){target="_blank"}

+++

+++ 데이터 패키지를 가져오려면 어떻게 해야 합니까?

데이터 패키지를 사용하면 인스턴스 간에 Campaign 구성(스키마, 워크플로우, 유형화, 필터)과 데이터를 내보내고 가져올 수 있습니다. 이는 개발에서 프로덕션으로 구성을 배포하거나 조직 간 구성 요소를 공유하는 데 필수적입니다.

**패키지할 수 있는 항목:**

* **구성 개체** - 스키마, 워크플로, 유형화 규칙, 양식, 필터
* **캠페인 구성 요소** - 게재 템플릿, 캠페인 템플릿, 콘텐츠 블록
* **응용 프로그램 설정** - 연산자, 연산자 그룹, 폴더 구조
* **데이터** - 받는 사람 목록, 시드 주소, 콘텐츠 조각
* **사용자 지정 개발** - JavaScript 코드, SQL 스크립트, 웹 응용 프로그램


**패키지 유형:**

* **사용자 패키지** - 만들고 내보내는 사용자 지정 구성
* **플랫폼 패키지** - Adobe 제공 기능 및 업데이트
* **데이터 패키지** - 구조뿐만 아니라 실제 데이터 레코드를 포함합니다.

**모범 사례:**

* 항상 동일한 또는 이전 Campaign 버전에서 패키지를 내보냅니다.
* 프로덕션 전 개발 환경에서 패키지 가져오기 테스트
* 패키지 내용 및 종속성 문서
* 패키지 XML 파일에 버전 제어 사용
* 주요 패키지를 가져오기 전에 인스턴스 백업

[데이터 패키지 작업](../dev/packages.md)

+++

+++ Campaign v8 API 목록은 어디에서 찾을 수 있습니까?

Campaign v8은 SOAP API(클라이언트 콘솔 상호 작용) 및 REST API(최신 통합)를 모두 다루는 포괄적인 API 설명서를 제공합니다. API 참조에는 사용 가능한 모든 메서드, 매개 변수 및 응답 형식이 포함됩니다.

**Campaign API 유형:**

* **SOAP API** - Campaign 클라이언트 콘솔 작업, 스키마 조작 및 워크플로우 제어를 위한 기존 API
* **REST API** - 외부 시스템 통합, 프로필 관리 및 이벤트 트리거를 위한 최신 HTTP API
* **JavaScript API** - 워크플로우 활동 및 사용자 지정 비즈니스 논리를 위한 서버측 스크립팅 API

**API 설명서 리소스:**

* **전체 API 참조:** 메서드 서명, 매개 변수 및 예제를 포함한 포괄적인 SOAP API 설명서
* **REST API 안내서:** 프로필, 이벤트 및 조직 단위에 대한 최신 REST 끝점
* 워크플로우 스크립트 및 웹 애플리케이션에서 사용할 수 있는 **JavaScript API:** 서버측 함수

**일반적인 API 사용 사례:**

* CRM, ERP 또는 맞춤형 애플리케이션과 Campaign 통합
* 캠페인 작업 및 워크플로우 실행 자동화
* 실시간으로 시스템 간 데이터 동기화
* 맞춤형 모니터링 및 경고 솔루션 구축
* Campaign 데이터 및 작업을 위한 외부 인터페이스 만들기

**액세스:** [Campaign v8 API 설명서](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=ko){target="_blank"}

+++


+++ API에서 워크플로우를 모니터링하려면 어떻게 합니까?

Campaign API를 사용하면 프로그래밍 방식으로 워크플로우 실행을 제어하고 모니터링할 수 있으므로 외부 모니터링 시스템, 자동화된 경고 및 사용자 지정 오케스트레이션 솔루션을 사용할 수 있습니다.

**API를 통해 수행할 수 있는 작업:**

* **워크플로우 시작** - 프로그래밍 방식으로 워크플로우 실행을 트리거합니다.
* **워크플로 일시 중지/다시 시작** - 워크플로 실행 흐름 제어
* **워크플로 중지** - 실행 중인 워크플로 종료
* **워크플로 상태 쿼리** - 워크플로가 실행 중인지, 일시 중지되었는지, 완료되었는지 확인
* **로그 검색** - 워크플로우 실행 로그 및 오류 메시지에 액세스
* **활동 진행 상황 모니터링** - 개별 워크플로우 활동 완료 추적

**API 메서드:**

* `xtk:workflow#Start` - 워크플로 인스턴스 시작
* `xtk:workflow#Pause` - 실행 중인 워크플로 일시 중지
* `xtk:workflow#Stop` - 워크플로우 실행 중지
* `xtk:workflow#GetState` - 현재 워크플로 상태 가져오기
* `xtk:workflow#GetLogs` - 실행 로그 검색

**일반적인 사용 사례:**

* 워크플로우 상태를 보여 주는 사용자 정의 모니터링 대시보드 구축
* 워크플로우가 실패하거나 너무 오래 실행되는 경우 자동 경고 구현
* 외부 스케줄러 또는 이벤트 시스템에서 워크플로우 오케스트레이션
* 여러 Campaign 인스턴스 간에 워크플로우 종속성 만들기
* 사용자 지정 워크플로우 실행 보고서 생성

**모범 사례:** 포괄적인 워크플로우 거버넌스를 위해 API 모니터링과 워크플로우 감사 추적을 결합합니다. 외부 모니터링 도구를 사용하여 워크플로 SLA 및 성능 지표를 추적합니다.

[API를 통해 워크플로우 제어](../dev/api/controlling-a-workflow.md)

+++

+++ 데이터베이스 구조를 업데이트하려면 어떻게 해야 합니까?

Campaign 스키마 수정(필드 추가, 테이블 생성, 데이터 유형 변경) 후 변경 사항을 적용하려면 물리적 데이터베이스 구조를 업데이트해야 합니다. 이렇게 동기화하면 데이터베이스가 스키마 정의와 일치합니다.

**데이터베이스 업데이트가 필요한 경우:**

* 기존 스키마에 새 필드 추가
* 사용자 지정 표 만들기 또는 기본 제공 표 확장
* 필드 속성 수정(데이터 유형, 길이, 필수 상태)
* 표 간 링크 추가 또는 제거
* 쿼리 최적화를 위한 새 색인 생성


**중요 고려 사항:**

* **먼저 백업** - 구조를 변경하기 전에 항상 데이터베이스를 백업하십시오.
* **개발에서 테스트** - 프로덕션 전에 개발 환경에서 스키마 변경 내용의 유효성을 검사합니다.
* **가동 중지 시간 계획** - 대규모 구조 변경은 간단한 유지 관리 기간이 필요할 수 있습니다.
* **관리 클라우드 서비스의 경우** - Adobe 지원을 통해 주요 변경 사항 조정
* **가역성** - 일부 변경(예: 필드 제거)으로 인해 데이터가 손실될 수 있습니다.

**모범 사례:** 스키마 버전 관리 및 변경 내용 추적을 사용합니다. 유지 관리 및 문제 해결을 위한 모든 사용자 정의 스키마 수정 사항을 문서화합니다.

[데이터베이스 구조 업데이트](../dev/update-database-structure.md) | [스키마 확장](../dev/extend-schema.md)

+++

+++ Campaign v8의 제한 사항은 무엇입니까?

Campaign v8에서는 아키텍처 변경 사항(특히 FFDA 배포 시)을 통해 성능이 크게 향상되었지만 Campaign Classic v7과는 일부 차이점도 있습니다. 이러한 사항을 이해하면 마이그레이션을 계획하고 적절한 기대치를 설정하는 데 도움이 됩니다.

**기본 v8 고려 사항:**

* **FFDA 아키텍처** - 엔터프라이즈 배포에서는 다양한 데이터 액세스 패턴의 클라우드 데이터베이스(Snowflake)를 사용합니다.
* **단위 업데이트** - 데이터 업데이트는 API 또는 직접 데이터베이스 액세스를 통해 수행하는 것이 아니라 워크플로우에서 수행해야 합니다.
* **실시간 쓰기** - 빈도가 높은 개별 업데이트가 아닌 일괄 작업에 최적화되었습니다.
* **데이터 모델** - 일부 스키마 사용자 지정에는 다른 접근 방식이 필요합니다.
* **외부 데이터베이스 액세스** - FDA(Federated Data Access) 구성이 v7과 다릅니다

**FFDA 배포에서 사용할 수 없는 기능:**

* 설문 조사(표준 v8 배포에서 사용 가능)
* 마케팅 리소스 관리(MRM)
* 일부 특정 커넥터 구성

**마이그레이션 고려 사항:**

* 직접 데이터베이스 쓰기를 사용하는 사용자 지정 코드에는 리팩터링이 필요합니다.
* API 통합에는 일괄 처리에 대한 적응이 필요할 수 있습니다
* 워크플로우는 데이터 작업에 대한 FFDA 모범 사례를 따라야 합니다
* 테스트는 사용자 정의 개발 사항의 유효성을 검사하는 데 필수적입니다

**중요:** Adobe에서 v8을 지속적으로 향상함에 따라 이러한 제한 사항이 발전하고 있습니다. 현재 상태 및 로드맵은 최신 설명서를 참조하십시오.

[Campaign v7에서 v8로의 마이그레이션](../start/v7-to-v8.md#limitations) | [FFDA 아키텍처](../architecture/enterprise-deployment.md)

+++

## 개인 정보 {#privacy}

Adobe Campaign이 GDPR 및 CCPA와 같은 개인 정보 보호 규정을 준수하고 데이터 주체 요청을 관리하는 데 어떻게 도움이 되는지 이해합니다.

+++ Campaign의 주요 개인 정보 보호 개념은 무엇입니까?

Campaign은 데이터 주체 권한, 동의 및 데이터 보존을 관리하는 도구를 통해 개인 정보 보호 규정(GDPR, CCPA, PDPA, LGPD)을 준수하도록 도와줍니다. 주요 개념으로는 개인정보 보호 규정, 개인 데이터 식별, 데이터 주체 권한(액세스, 삭제, 이동성), 동의 관리 및 데이터 보존 정책 등이 있습니다.

데이터 제어자는 데이터 주체 요청을 처리하고, 동의 레코드를 유지 관리하며, 투명한 데이터 사용을 보장합니다.

[개인 정보 보호 관리](../start/privacy.md)

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

[개인 정보 보호 관리](../start/privacy.md)

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

[구독 서비스](../start/subscriptions.md) | [개인 정보 및 동의](../start/privacy.md#consent-retention-roles) | [개인 정보 관리](../start/privacy.md)

+++

+++ 삭제 요청을 처리할 때 어떤 데이터가 삭제됩니까?

Campaign은 데이터 주체에 연결된 모든 데이터(수신자 프로필, 게재 및 추적 로그, 소유권 관계가 있는 사용자 지정 데이터, 구독 내역 및 웹 추적 데이터)를 자동으로 삭제합니다.

**작동 방식:** Campaign은 받는 사람에 대한 링크가 스키마 정의에서 `integrity="own"`을(를) 갖는 모든 데이터를 삭제하여 관련 테이블에 걸쳐 연속 삭제를 보장합니다.

스키마에서 링크 무결성을 수정하여 삭제 범위를 사용자 지정할 수 있지만 먼저 법률 자문을 구하십시오. 삭제는 영구적이며 실행 취소할 수 없습니다.

[개인 정보 관리](../start/privacy.md) | [스키마 링크](../dev/schemas.md)

+++

+++ 개인 정보 삭제가 게재 보고서에 영향을 줍니까?

아니요. Campaign 보고서는 개별 로그의 라이브 쿼리가 아닌 미리 계산된 집계된 지표(총 전송, 열기, 클릭 수)를 기반으로 합니다. 개별 수신자 데이터를 삭제해도 내역 집계 통계는 변경되지 않습니다.

전체 게재 통계 및 성능 지표는 그대로 유지되지만 개별 추적 로그 및 개인 세부 정보는 제거됩니다. 이렇게 하면 데이터 주체 권한을 준수하면서 마케팅 분석을 유지할 수 있습니다.

[개인 정보 관리](../start/privacy.md) | [보고서](../reporting/gs-reporting.md)

+++

+++ 삭제된 데이터를 다시 가져올 수 없도록 하려면 어떻게 해야 합니까?

Campaign뿐만 아니라 모든 소스 시스템에서 데이터를 삭제해야 합니다. 데이터는 종종 외부 시스템(CRM, 전자 상거래, 데이터 웨어하우스)에서 흐릅니다.

**필수 작업:** 모든 데이터 원본을 식별하고, 원본 시스템에서 삭제하고, 제외/제외 목록에 추가하고, 삭제 플래그를 사용하도록 가져오기 워크플로우를 업데이트하고, 프로세스를 문서화합니다.

데이터 제어자는 전체 기술 생태계에서 완전한 데이터 제거를 담당합니다.

[개인 정보 관리](../start/privacy.md) | [워크플로우 가져오기](../config/workflows.md)

+++

+++ 삭제된 사용자가 다시 옵트인할 수 있습니까?

예. 데이터 주체는 삭제 후 다시 옵트인할 수 있습니다. Campaign은 이전에 삭제된 데이터에 대한 링크 없이 완전히 새로운 수신자 레코드를 만듭니다. 프로필은 깨끗한 슬레이트로 시작됩니다.

Campaign의 감사 추적은 삭제 이벤트와 새 프로필 생성을 모두 기록하며, 규정 준수를 입증하고 삭제 후 새 옵트인이 자유롭게 부여되었음을 보여 줍니다.

[개인 정보 관리](../start/privacy.md) | [구독](../start/subscriptions.md)

+++

## 여전히 도움이 필요하십니까? {#get-help}

찾고 있는 항목을 찾을 수 없습니까? 다음은 Adobe Campaign v8을 성공적으로 사용할 수 있는 추가 리소스입니다.

### 커뮤니티 지원

다른 Campaign 사용자 및 Adobe 전문가와 연결하여 지식을 공유하고 답변을 얻을 수 있습니다.

* **[Adobe Campaign 커뮤니티](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=ko){target="_blank"}** - 질문하고, 솔루션을 공유하고, Campaign 커뮤니티에 연결합니다.
* **[Experience League 포럼](https://experienceleaguecommunities.adobe.com/?profile.language=ko){target="_blank"}** - 모든 Adobe 제품에서 토론 찾아보기
* **[Campaign 커뮤니티 운영 시간](https://experienceleague.adobe.com/ko){target="_blank"}** - Adobe 전문가와 실시간 세션에 참여

### 설명서 및 학습

포괄적인 안내서, 튜토리얼 및 교육 자료를 이용할 수 있습니다.

* **[Campaign v8 설명서 홈](../campaign-home.md)** - 전체 제품 설명서
* **[캠페인 튜토리얼](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html?lang=ko){target="_blank"}** - 단계별 비디오 가이드 및 실습 튜토리얼
* **[새로운 기능](whats-new.md)** - 최신 기능
* **[릴리스 정보](release-notes.md)** - 현재 및 이전 릴리스 정보
* **[버전 및 업그레이드](upgrades.md)** - Campaign 버전, 업그레이드 및 버전 확인 방법에 대해 알아보기
* **[모범 사례](delivery-best-practices.md)** - 일반적인 작업에 대해 권장되는 접근 방식

### 기술 리소스

자세한 기술 설명서 및 개발자 리소스를 확인하십시오.

* **[캠페인 API](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=ko){target="_blank"}** - 전체 API 참조 설명서
* **[Campaign GitHub](https://github.com/AdobeDocs/campaign.kr)** - 문서에 참여
* **[기술 노트](https://experienceleague.adobe.com/ko/docs/campaign/technotes-ac/technotes-home){target="_blank"}** - 심화 기술 문서
* **[호환성 매트릭스](compatibility-matrix.md)** - 지원되는 시스템 및 버전
* **[버전 및 업그레이드 FAQ](upgrades.md#upgrades-faq)** - 버전을 확인하고 업그레이드에 대해 알아봅니다.

### 지원 및 서비스

Adobe 지원 팀의 도움을 받고 인스턴스를 관리합니다.

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** - 지원 사례 로그 및 사용자 관리
* **[Adobe 고객 지원 센터](https://helpx.adobe.com/kr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - 지원 팀에 문의
* **[Campaign 컨트롤 패널](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ko){target="_blank"}** - Campaign 인스턴스 설정 관리
* **[시스템 상태](https://status.adobe.com/){target="_blank"}** - Adobe 서비스 상태 확인

### 교육 및 인증

공식 Adobe 교육 및 인증 프로그램을 통해 기술을 향상시키십시오.

* **[Adobe 디지털 학습 서비스](https://learning.adobe.com/){target="_blank"}** - 공식 강사 주도 및 자습형 교육 과정
* **[Adobe Campaign 인증](https://experienceleague.adobe.com/docs/certification/program/overview.html?lang=ko){target="_blank"}** - 전문 인증을 통해 전문성 확인
* **[Experience League 학습 경로](https://experienceleague.adobe.com/ko?lang=en#dashboard/learning){target="_blank"}** - 안내식 학습 여정

### 기타 유용한 리소스

* **[Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=ko){target="_blank"}** - Classic v7 사용자를 위한 참조
* **[Campaign 웹 UI 설명서](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - 새 웹 인터페이스 안내서
* **[게재 가능성 모범 사례](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=ko){target="_blank"}** - 전자 메일 게재 최적화
* **[제품 업데이트](https://experienceleague.adobe.com/ko/docs/release-notes/experience-cloud/current){target="_blank"}** - 최신 Adobe Experience Cloud 업데이트

**마지막 업데이트:** 2025년 11월 | **적용 대상:** Campaign v8.6 이상

*오류를 발견했거나 개선을 제안하시겠습니까? [GitHub에서 이 페이지 편집](https://github.com/AdobeDocs/campaign.ko-KR/edit/main/help/v8/start/campaign-faq-comprehensive.md)*

