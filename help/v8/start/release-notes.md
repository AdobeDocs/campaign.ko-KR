---
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 65efda7469c5ad35e8d03703951c3d1480b015f4
workflow-type: ht
source-wordcount: '781'
ht-degree: 100%

---

# 최신 릴리스 {#latest-release}

Adobe Campaign은 정기적으로 업데이트됩니다. 이러한 정기 업데이트 빈도는 최신 업데이트를 직접 경험해 보고 사용 환경을 안전하게 지키며 Adobe 제품 경험을 향상시키는 것을 목표로 합니다. Adobe는 모든 고객에게 최신 버전으로 업그레이드할 것을 강력히 권장합니다. 이 페이지에는 최신 Campaign v8 릴리스(콘솔)의 최신 릴리스와 함께 새로운 기능, 개선 및 수정 사항이 나와 있습니다. [이 페이지](upgrades.md)에서 Campaign 버전 및 업데이트에 대해 자세히 알아보십시오.

Adobe는 새 버전이 나올 때마다 Managed Cloud Services 사용자의 인스턴스를 업그레이드합니다. Adobe이 귀하에게 연락하여 환경을 업그레이드합니다. Campaign 클라이언트 콘솔은 **Campaign 서버와 동일한 버전으로 업그레이드**&#x200B;되어야 합니다. [이 페이지](../start/connect.md#upgrade-ac-console)에서 클라이언트 콘솔을 업그레이드하는 방법을 알아보십시오.

또한 고객은 [호환성 매트릭스](compatibility-matrix.md)에 나열된 최신 지원 버전의 시스템을 사용하고 있는지 확인하십시오.

## 릴리스 8.5.3 {#release-8-5-3}

_2024년 5월 28일 수요일_

### OAuth 서버 간 자격 증명으로 마이그레이션 {#change-8-5-3}

이 버전부터 서비스 계정(JWT) 자격 증명이 Adobe에 의해 더 이상 사용되지 않으며, Adobe 솔루션 및 앱과 Campaign 아웃바운드 통합이 이제 OAuth 서버 간 자격 증명을 사용합니다. [자세히 알아보기](#change-8-7-1)

### 수정 사항 {#fixes-8-5-3}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-59544, NEO-52542


## 5월 업데이트 {#may-updates}

다음 변경 사항은 5월에 릴리스되었으며 이제 Campaign v8 사용자가 사용할 수 있습니다.

* **새로운 향상된 보안 추가 기능**: 네트워크 연결을 더욱 안전하게 만들고 리소스에 대한 향상된 보안을 제공하기 위해 Adobe Campaign에서는 보안 CMK 통합 및 보안 VPN 터널링의 두 가지 기능이 포함된 향상된 새 보안 추가 기능을 제공합니다. [자세히 보기](../config/enhanced-security.md)


## 릴리스 8.7.1 {#release-8-7-1}

_2024년 5월 2일_

>[!AVAILABILITY]
>
>이 릴리스는 **제한 공개**(LA) 상태입니다. 이는 **Adobe Campaign Standard에서 Adobe Campaign v8**&#x200B;로 마이그레이션하는 고객으로 제한되며 다른 환경에는 배포할 수 없습니다.
>
>Campaign v8로 전환하는 Campaign Standard 사용자라면 [Campaign v8 웹 사용자 인터페이스 설명서](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}를 통해 전환 과정을 자세히 확인할 수 있습니다.

### 새로운 기능 {#new-8-7-1}

* **리치 푸시 알림 템플릿** - 이제 Android를 통해 리치 푸시 알림을 전송할 수 있습니다. 리치 푸시 알림은 이미지, 대화형 버튼 또는 기타 리치 미디어 콘텐츠와 같은 멀티미디어 요소를 통합하여 단순한 문자 메시지를 뛰어 넘는 향상된 형태의 모바일 알림입니다. [자세히 보기](../send/rich-push.md).

* **브랜딩** - Campaign Standard로 마이그레이션한 사용자로서 기술 관리자는 이제 하나 이상의 브랜드를 정의하여 브랜드의 정체성에 영향을 미치는 매개 변수를 중앙 집중화할 수 있습니다. 여기에는 브랜드 로고, 랜딩 페이지의 액세스 URL의 도메인 또는 메시지 추적 설정이 포함됩니다. 이러한 브랜드를 만들어 메시지 또는 랜딩 페이지에 연결할 수 있습니다. 이 구성은 템플릿에서 관리됩니다. [자세히 보기](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=ko){target="_blank"}

* **Rest API** - Campaign Standard를 마이그레이션한 사용자는 Rest API를 사용하여 Adobe Campaign을 위한 통합을 만들고, 사용하는 기술 패널과 Adobe Campaign을 연결하여 고유한 에코시스템을 구축할 수 있습니다. [자세히 보기](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=ko){target="_blank"}

* **다이내믹 보고** - Campaign Standard를 마이그레이션한 사용자는 완전히 맞춤화가 가능한 실시간 보고서를 제공하는 다이내믹 보고에 액세스하여 마케팅 활동의 영향을 측정할 수 있습니다. 이 기능은 프로필 데이터에 대한 액세스를 추가하여 열기 및 클릭과 같은 기능적 이메일 캠페인 데이터 외에도 성별, 도시, 연령과 같은 프로필 차원별로 인구통계학적 분석을 지원합니다. [자세히 보기](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=ko){target="_blank"}

### 호환성 업데이트 {#comp-8-7-1}

* 이제 Databricks는 Adobe Campaign FDA(Federated Data Access)를 통해 외부 데이터베이스로 지원됩니다. [이 페이지](compatibility-matrix.md#FederatedDataAccessFDA)에서 자세히 알아보십시오.

### OAuth 서버 간 자격 증명으로 마이그레이션 {#change-8-7-1}

이 버전부터 서비스 계정(JWT) 자격 증명이 Adobe에 의해 더 이상 사용되지 않으며, Adobe 솔루션 및 앱과 Campaign 아웃바운드 통합이 이제 OAuth 서버 간 자격 증명을 사용합니다. Adobe은 Campaign-Analytics 통합 또는 Experience Cloud Triggers 통합과 같은 아웃바운드 통합을 위해 JWT를 OAuth로 마이그레이션합니다.

Campaign과 인바운드 통합을 구현했다면 기술 계정을 마이그레이션해야 합니다. 마이그레이션 방법은 [이 설명서](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}에 자세히 나와 있습니다. **2025년 1월 27일**&#x200B;까지는 기존 서비스 계정(JWT) 자격 증명을 계속 사용할 수 있습니다. 

### 일반 개선 사항 {#improvements-8-7-1}

* 여러 스키마가 32비트에서 64비트로 변경되었습니다. 이는 Campaign Standard에서 마이그레이션하는 고객에게만 적용됩니다. [자세히 보기](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=ko){target="_blank"}

* 이제 Campaign 테이블에서 `lastModified` 및 `created` 속성에 기본적으로 서버 날짜 및 시간이 입력됩니다. 이제 `createdBy-id` 속성 값이 기본적으로 현재 로그인 ID로 채워집니다. API 호출에서 사용자가 제공한 값은 무시됩니다. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

* 애플리케이션 간 모든 통신에 대한 보안을 강화하기 위해 이제 외부 API 호출에도 mTLS를 지원합니다.

### 수정 사항 {#fixes-8-7-1}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054
