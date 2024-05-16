---
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: b364b557bdf060e022196786a970517056eb2bf7
workflow-type: tm+mt
source-wordcount: '870'
ht-degree: 93%

---

# 최신 릴리스{#latest-release}

Adobe Campaign은 정기적으로 업데이트됩니다. 이러한 정기 업데이트 빈도는 최신 업데이트를 직접 경험해 보고 사용 환경을 안전하게 지키며 Adobe 제품 경험을 향상시키는 것을 목표로 합니다. Adobe는 모든 고객에게 최신 버전으로 업그레이드할 것을 강력히 권장합니다. 

Adobe는 새 버전이 나올 때마다 Managed Cloud Services 사용자의 인스턴스를 업그레이드합니다. Adobe이 귀하에게 연락하여 환경을 업그레이드합니다. Campaign 클라이언트 콘솔은 **Campaign 서버와 동일한 버전으로 업그레이드**&#x200B;되어야 합니다. 이 [페이지](../start/connect.md#upgrade-ac-console)에서 클라이언트 콘솔을 업그레이드하는 방법을 알아보십시오.

또한 고객은 [호환성 매트릭스](compatibility-matrix.md)에 나열된 최신 지원 버전의 시스템을 사용하고 있는지 확인하십시오.

## 릴리스 8.7.1 {#release-8-7-1}

_2024년 5월 2일_

>[!AVAILABILITY]
>
>이 릴리스는 **제한 공개**(LA) 상태입니다. 이는 **Adobe Campaign Standard에서 Adobe Campaign v8**&#x200B;로 마이그레이션하는 고객으로 제한되며 다른 환경에는 배포할 수 없습니다.
>
>Campaign Standard 사용자가 Campaign v8로 전환하는 경우에서 이 전환에 대해 자세히 알아보십시오. [Campaign v8 웹 사용자 인터페이스 설명서](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### 새로운 기능 {#new-8-7-1}

* **리치 푸시 알림 템플릿** - 이제 Android를 통해 리치 푸시 알림을 전송할 수 있습니다. 리치 푸시 알림은 이미지, 대화형 버튼 또는 기타 리치 미디어 콘텐츠와 같은 멀티미디어 요소를 통합하여 단순한 문자 메시지를 뛰어 넘는 향상된 형태의 모바일 알림입니다. [자세히 보기](../send/rich-push.md).

* **브랜딩** - Campaign Standard로 마이그레이션한 사용자로서 기술 관리자는 이제 하나 이상의 브랜드를 정의하여 브랜드의 정체성에 영향을 미치는 매개 변수를 중앙 집중화할 수 있습니다. 여기에는 브랜드 로고, 랜딩 페이지의 액세스 URL의 도메인 또는 메시지 추적 설정이 포함됩니다. 이러한 브랜드를 만들어 메시지 또는 랜딩 페이지에 연결할 수 있습니다. 이 구성은 템플릿에서 관리됩니다. [자세히 보기](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=ko){target="_blank"}

* **Rest API** - Campaign Standard를 마이그레이션한 사용자는 Rest API를 사용하여 Adobe Campaign을 위한 통합을 만들고 사용하는 기술 패널과 Adobe Campaign을 연결하여 고유한 에코시스템을 구축할 수 있습니다. [자세히 보기](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=ko){target="_blank"}

* **다이내믹 보고** - Campaign Standard를 마이그레이션한 사용자는 완전히 맞춤화가 가능한 실시간 보고서를 제공하는 다이내믹 보고에 액세스하여 마케팅 활동의 영향을 측정할 수 있습니다. 이 기능은 프로필 데이터에 대한 액세스를 추가하여 열기 및 클릭과 같은 기능적 이메일 캠페인 데이터 외에도 성별, 도시, 연령과 같은 프로필 차원별로 인구통계학적 분석을 지원합니다. [자세히 보기](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=ko){target="_blank"}

<!--
* **New Enhanced security add-on**: To make your network connection more secure and provide improved security for your resources, Adobe Campaign offers a new Enhanced security add-on, which includes two features: Secure CMK integration and Secure VPN tunneling.
-->

### 호환성 업데이트 {#comp-8-7-1}

이제 Databricks는 Adobe Campaign FDA(Federated Data Access)를 통해 외부 데이터베이스로 지원됩니다. [이 페이지](compatibility-matrix.md#FederatedDataAccessFDA)에서 자세히 알아보십시오.

### 일반 개선 사항 {#improvements-8-7-1}

* 여러 스키마가 32비트에서 64비트로 변경되었습니다. 이는 Campaign Standard에서 마이그레이션하는 고객에게만 적용됩니다. [자세히 보기](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=ko){target="_blank"}

* 이제 Campaign 테이블에서 lastModified, created, createdBy-id 속성은 기본적으로 서버 날짜 및 시간으로 채워집니다. API 호출에서 사용자가 제공한 값은 무시됩니다. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

### 수정 사항 {#fixes-8-7-1}

다음 문제는 아래 릴리스에서 해결되었습니다.
NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054

## 릴리스 8.6.2 {#release-8-6-2}

_2024년 2월 23일_

### 수정 사항 {#fixes-8-6-2}

이 릴리스에서는 다음 문제가 해결되었습니다.

* 중간 소싱 인스턴스에서 발생할 수 있는 성능 문제를 해결했습니다(NEO-72595).

## 릴리스 8.6.1 {#release-8-6-1}

_2024년 2월 14일_

### 새로운 기능 {#new-8-6-1}

* 이번 릴리스부터 중앙 Adobe Experience Cloud 환경을 통해 사용할 수 있는 새로운 **Campaign Web 사용자 인터페이스**&#x200B;에 액세스할 수 있습니다. Experience Cloud는 Adobe의 디지털 마케팅 애플리케이션, 제품 및 서비스 통합 제품군입니다. 직관적인 인터페이스에서 클라우드 애플리케이션, 제품 기능, 서비스에 빠르게 액세스할 수 있습니다. [이 페이지에서](campaign-ui.md#ac-web-ui) Adobe Experience Cloud에 연결하여 Adobe Campaign Web 인터페이스에 액세스하는 방법을 알아보십시오.


* Adobe Campaign v8은 이제 **Adobe Experience Manager as a Cloud Service**&#x200B;와 통합되어 Adobe Campaign Web 사용자 인터페이스를 통해서만 작성이 가능합니다. [자세히 알아보기](../connect/ac-aem.md)

* 이제 Adobe Campaign 인스턴스에 Adobe Experience Cloud 통합 패키지가 설치되어 있어도 Experience Cloud Assets과 함께 **Adobe Experience Manager Assets 라이브러리**&#x200B;를 사용할 수 있습니다. [자세히 알아보기](../connect/ac-aem.md#assets-library)

### 일반 개선 사항 {#improvements-8-6-1}

* Campaign v8.6은 **이메일 게재 추적 지표**&#x200B;에 대한 처리량이 향상되었습니다. 최적화된 프로세스로 추적 수집 및 컴퓨팅 시간이 단축되고 게재 주요 지표를 훨씬 빠르게 확인할 수 있습니다.


### 전달성 업데이트 {#deliverability-8-6-1}

* 2024년 2월까지 Google 또는 Yahoo!를 통해 5,000개가 넘는 이메일 메시지를 보내는 모든 회사는 도메인 기반 메시지 인증 보고 및 적합성(DMARC)이라는 인증 기술을 사용하기 시작해야 합니다. Adobe Campaign에서 사용하는 모든 하위 도메인에 대해 DMARC 레코드를 설정해야 합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=ko){target="_blank"}

* 2024년 6월 1일부터 Google 및 Yahoo!는 발신자에게 원클릭 목록-구독 취소를 준수하도록 요구할 것입니다. 이제 Adobe Campaign에서 이 옵션을 지원합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=ko#one-click-list-unsubscribe){target="_blank"}


### 수정 사항 {#fixes-8-6-1}

다음 문제는 아래 릴리스에서 해결되었습니다.
NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789