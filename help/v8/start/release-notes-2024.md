---
title: Campaign v8(콘솔) 2024 릴리스 정보
description: 2024 Campaign v8 릴리스의 기능 및 개선 사항 목록
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
source-git-commit: 041df8d2d6128d72a04008affbc9680ba5b640a1
workflow-type: tm+mt
source-wordcount: '1308'
ht-degree: 81%

---

# 2024 릴리스 정보 {#2024-rn}

이 페이지에는 **2024 Campaign v8 릴리스**&#x200B;의 새로운 기능, 개선 사항 및 수정 사항이 나와 있습니다.

>[!BEGINSHADEBOX]

**이 페이지에서**

* Campaign v8.7 - [릴리스 8.7.1](#release-8-7-1)
* Campaign v8.6 - [릴리스 8.6.1](#release-8-6-1) | [릴리스 8.6.2](#release-8-6-2) | [릴리스 8.6.3](#release-8-6-3)
* Campaign v8.5 - [릴리스 8.5.3](#release-8-5-3)

>[!ENDSHADEBOX]



## 릴리스 8.7.1 {#release-8-7-1}

_2024년 5월 2일_

>[!AVAILABILITY]
>
>이 릴리스는 **제한 공개**(LA) 상태입니다. 이는 **Adobe Campaign Standard에서 Adobe Campaign v8**&#x200B;로 마이그레이션하는 고객으로 제한되며 다른 환경에는 배포할 수 없습니다.
>
>Campaign v8로 전환하는 Campaign Standard 사용자라면 [Campaign v8 웹 사용자 인터페이스 설명서](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/acs-migration){target="_blank"}를 통해 전환 과정을 자세히 확인할 수 있습니다.

### 새로운 기능 {#new-8-7-1}

* **리치 푸시 알림 템플릿** - 이제 Android를 통해 리치 푸시 알림을 전송할 수 있습니다. 리치 푸시 알림은 이미지, 대화형 버튼 또는 기타 리치 미디어 콘텐츠와 같은 멀티미디어 요소를 통합하여 단순한 문자 메시지를 뛰어 넘는 향상된 형태의 모바일 알림입니다. [자세히 보기](../send/rich-push-ios.md).

* **브랜딩** - Campaign Standard로 마이그레이션한 사용자로서 기술 관리자는 이제 하나 이상의 브랜드를 정의하여 브랜드의 아이덴티티에 영향을 미치는 매개 변수를 중앙 집중화할 수 있습니다. 여기에는 브랜드 로고, 랜딩 페이지의 액세스 URL의 도메인 또는 메시지 추적 설정이 포함됩니다. 이러한 브랜드를 만들어 메시지 또는 랜딩 페이지에 연결할 수 있습니다. 이 구성은 템플릿에서 관리됩니다. [자세히 보기](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=ko){target="_blank"}

* **Rest API** - Campaign Standard를 마이그레이션한 사용자는 Rest API를 사용하여 Adobe Campaign을 위한 통합을 만들고, 사용하는 기술 패널과 Adobe Campaign을 연결하여 고유한 에코시스템을 구축할 수 있습니다. [자세히 보기](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=ko){target="_blank"}

* **다이내믹 보고** - Campaign Standard를 마이그레이션한 사용자는 완전히 맞춤화가 가능한 실시간 보고서를 제공하는 다이내믹 보고에 액세스하여 마케팅 활동의 영향을 측정할 수 있습니다. 이 기능은 프로필 데이터에 대한 액세스를 추가하여 열기 및 클릭과 같은 기능적 이메일 캠페인 데이터 외에도 성별, 도시, 연령과 같은 프로필 차원별로 인구통계학적 분석을 지원합니다. [자세히 보기](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=ko){target="_blank"}

### 호환성 업데이트 {#comp-8-7-1}

다음 FDA 커넥터가 추가되었습니다. 이 [페이지](compatibility-matrix.md#FederatedDataAccessFDA)를 참조하세요.

* 이제 데이터 블록은 Adobe Campaign FDA(Federated Data Access)를 통해 외부 데이터베이스로 지원됩니다.

* 이제 새로운 Amazon Redshift FDA ODBC 커넥터를 사용할 수 있습니다. 향상된 연결성, 쉬운 유지 관리 및 향상된 호환성을 제공합니다. 이 새 버전은 다음과 같은 개선 사항을 제공합니다.

   * 새 커넥터는 최신 FDA 커넥터에 맞는 ODBC 인터페이스를 기반으로 합니다. 이를 통해 장기적인 지원이 보장됩니다.
   * 또한 s3 버킷을 사용하는 새로운 데이터 로드 메커니즘을 도입하여 성능이 크게 향상되었습니다.

  레거시 커넥터는 계속 사용할 수 있습니다. 새로운 기능을 사용해 보려면 Adobe 담당자에게 문의하십시오.

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



## 릴리스 8.6.3 {#release-8-6-3}

_2024년 7월 30일_

### 새로운 기능 {#new-8-6-3}

* **리치 푸시 알림** - 이제 리치 푸시 알림을 전송할 수 있습니다. 리치 푸시 알림은 이미지, 대화형 버튼 또는 기타 리치 미디어 콘텐츠와 같은 멀티미디어 요소를 통합하여 단순한 문자 메시지를 뛰어 넘는 향상된 형태의 모바일 알림입니다. 이번 버전에서는 이제 iOS 및 Android 앱에서 리치 푸시 알림을 위한 템플릿 세트를 사용할 수 있습니다. [자세히 보기](../send/rich-push-android.md).

* 이 버전부터 서비스 계정(JWT) 자격 증명이 Adobe에 의해 더 이상 사용되지 않으며, Adobe 솔루션 및 앱과 Campaign 아웃바운드 통합이 이제 OAuth 서버 간 자격 증명을 사용합니다. [자세히 알아보기](release-notes-2024.md#change-8-7-1)

### 일반 개선 사항 {#improvements-8-6-3}

* 애플리케이션 간 모든 통신에 대한 보안을 강화하기 위해 이제 외부 API 호출에도 mTLS를 지원합니다.

### 수정 사항 {#fixes-8-6-3}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-79328, NEO-78843, NEO-77795, NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-72504, NEO-70263, NEO-67620, NEO-63197, NEO-58596, NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->


## 2024년 5월 업데이트 {#may-updates}

다음 변경 사항은 5월에 릴리스되었으며 이제 Campaign v8 사용자가 사용할 수 있습니다.

* **새로운 향상된 보안 추가 기능**: 네트워크 연결을 더욱 안전하게 만들고 리소스에 대한 향상된 보안을 제공하기 위해 Adobe Campaign에서는 보안 CMK 통합 및 보안 VPN 터널링의 두 가지 기능이 포함된 향상된 새 보안 추가 기능을 제공합니다. [자세히 보기](../config/enhanced-security.md)

## 릴리스 8.6.2 {#release-8-6-2}

_2024년 2월 23일_

### 수정 사항 {#fixes-8-6-2}

이 릴리스에서는 다음 문제가 해결되었습니다.

* 중간 소싱 인스턴스에서 발생할 수 있는 성능 문제를 해결했습니다(NEO-72595).

## 릴리스 8.6.1 {#release-8-6-1}

_2024년 2월 14일_

### 새로운 기능 {#new-8-6-1}

* 이번 릴리스부터 중앙 Adobe Experience Cloud 환경을 통해 사용할 수 있는 새로운 **Campaign Web 사용자 인터페이스**&#x200B;에 액세스할 수 있습니다. Experience Cloud는 Adobe의 디지털 마케팅 애플리케이션, 제품 및 서비스 통합 제품군입니다. 직관적인 인터페이스에서 클라우드 애플리케이션, 제품 기능, 서비스에 빠르게 액세스할 수 있습니다. [이 페이지에서](campaign-ui.md#ac-web-ui) Adobe Experience Cloud에 연결하여 Adobe Campaign Web 인터페이스에 액세스하는 방법을 알아보십시오.

  >[!AVAILABILITY]
  >
  >Campaign 웹 사용자 인터페이스는 Adobe ID을 사용하여 Adobe Campaign에 연결하는 사용자만 사용할 수 있습니다. [Adobe IMS(Identity Management System)](https://helpx.adobe.com/kr/enterprise/using/identity.html){target="_blank"}에 대해 자세히 알아보세요.
  >

* Adobe Campaign v8은 이제 **Adobe Experience Manager as a Cloud Service**&#x200B;와 통합되어 Adobe Campaign Web 사용자 인터페이스를 통해서만 작성이 가능합니다. [자세히 알아보기](../connect/ac-aem.md)

* 이제 Adobe Campaign 인스턴스에 Adobe Experience Cloud 통합 패키지가 설치되어 있어도 Experience Cloud Assets과 함께 **Adobe Experience Manager Assets 라이브러리**&#x200B;를 사용할 수 있습니다. [자세히 알아보기](../connect/ac-aem.md#assets-library)

### 일반 개선 사항 {#improvements-8-6-1}

* Campaign v8.6은 **이메일 게재 추적 지표**&#x200B;에 대한 처리량이 향상되었습니다. 최적화된 프로세스로 추적 수집 및 컴퓨팅 시간이 단축되고 게재 주요 지표를 훨씬 빠르게 확인할 수 있습니다.


### 전달성 업데이트 {#deliverability-8-6-1}

* 2024년 2월까지 Google 또는 Yahoo!를 통해 5,000개가 넘는 이메일 메시지를 보내는 모든 회사는 도메인 기반 메시지 인증 보고 및 적합성(DMARC)이라는 인증 기술을 사용하기 시작해야 합니다. Adobe Campaign에서 사용하는 모든 하위 도메인에 대해 DMARC 레코드를 설정해야 합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=ko){target="_blank"}

* 2024년 6월 1일부터 Google 및 Yahoo!는 발신자에게 원클릭 목록-구독 취소를 준수하도록 요구할 것입니다. 이제 Adobe Campaign에서 이 옵션을 지원합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#list-unsubscribe){target="_blank"}


### 수정 사항 {#fixes-8-6-1}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059 58637 55197 52542 50488 47789



## 릴리스 8.5.3 {#release-8-5-3}

_2024년 5월 28일 수요일_

### OAuth 서버 간 자격 증명으로 마이그레이션 {#change-8-5-3}

이 버전부터 서비스 계정(JWT) 자격 증명이 Adobe에 의해 더 이상 사용되지 않으며, Adobe 솔루션 및 앱과 Campaign 아웃바운드 통합이 이제 OAuth 서버 간 자격 증명을 사용합니다. [자세히 알아보기](#change-8-7-1)

### 수정 사항 {#fixes-8-5-3}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-59544, NEO-52542