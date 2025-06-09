---
title: Campaign v8 호환성 표
description: Campaign v8과 호환되는 시스템 및 버전 살펴보기
feature: Release Notes
role: Admin
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
source-git-commit: fb2cf4407750f8cff65ca53f0e87c32e9702de92
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 92%

---

# Campaign v8 호환성 표 {#compat-matrix}

이 문서는 **Adobe Campaign v8** 클라이언트 콘솔의 최신 빌드를 지원하는 모든 시스템 및 구성 요소 목록을 제공합니다. 별도로 언급되지 않는 한 모든 마이너 릴리스도 지원됩니다. 이 목록에 포함되지 않은 제품 및 버전은 Adobe Campaign과 호환되지 않습니다.

이러한 타사 시스템 및 도구의 특정 버전이 EOL(End-of-Life)에 도달함에 따라 Adobe Campaign은 더 이상 해당 버전과 호환되지 않으며 이후 이 호환성 매트릭스에서 제거됩니다. 문제가 생기지 않도록 호환성 매트릭스에 나와 있는 모든 시스템의 지원 버전을 사용하고 있는지 확인하십시오.

>[!NOTE]
>
>Adobe Campaign 서버와 Campaign 클라이언트 콘솔의 버전은 동일해야 합니다. [버전을 확인하는 방법을 알아보십시오](upgrades.md#version).

## 클라이언트 콘솔 {#ClientConsoleoperatingsystems}

Campaign 클라이언트 콘솔을 사용하려면 다음 운영 체제와 브라우저가 필요합니다. [자세히 알아보기](connect.md)

### 운영 체제 {#op-systems}

* **Microsoft Windows Server** 2019, 2016
* **Microsoft Windows** 11, 10

>[!NOTE]
>클라이언트 콘솔의 32비트 버전은 8.5 릴리스 이후 더 이상 사용되지 않습니다. 8.6 릴리스부터 클라이언트 콘솔은 64비트로만 사용할 수 있습니다. 시스템을 업그레이드하는 자세한 방법은 [기술 정보](../../technotes/upgrades/console.md)를 참조하십시오.

### 웹 브라우저 {#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**, 최신 버전. [Microsoft 개발자 사이트](http://www.adobe.com/go/acc-ms-webview2-runtime-download_kr){target="_blank"}에서 다운로드합니다.

## CRM 커넥터 {#CRMconnectors}

Adobe Campaign과 호환되는 CRM(고객 관계 관리) 시스템 목록은 다음과 같습니다. [이 페이지에서](../connect/crm.md) CRM 커넥터에 대해 자세히 알아봅니다.

* **Salesfore** connector API 버전 49
* **Microsoft Dynamics** 커넥터, Web API: Dynamics 365 온프레미스 및 온라인

## FDA(Federated Data Access){#FederatedDataAccessFDA}

Adobe Campaign FDA(Federated Data Access) 모듈과 호환되는 외부 데이터베이스 목록은 다음과 같습니다. [이 페이지에서](../connect/fda.md) FDA에 대해 자세히 알아봅니다.

* **[!DNL Amazon Redshift]** ODBC 커넥터, Campaign v8.6.4 / v8.7.1부터
* **[!DNL Amazon Redshift]** 레거시 커넥터
* **[!DNL Azure Synapse]**, Campaign v8.5부터
* **[!DNL Databricks]**, Campaign v8.6.4/v8.7부터
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**


>[!AVAILABILITY]
>또한 [향상된 보안 추가 기능](../config/enhanced-security.md#secure-vpn-tunneling)을 사용하면 보안 VPN 터널링을 통해 On-Premise 데이터베이스에 액세스할 수 있습니다. [자세히 알아보기](../config/enhanced-security.md#vpn-callouts)

## 모바일 SDK {#MobileSDK}

Campaign으로 [푸시 알림](../send/push.md)을 보내려면 데이터 수집 UI에서 Adobe Campaign Classic을 구성하여 Adobe Experience Platform Mobile SDK를 사용합니다.

iOS 및 Android의 호환 버전은 [Adobe Developer 설명서](https://developer.adobe.com/client-sdks/home/){target="_blank"}에 자세히 설명되어 있습니다.

## Web 사용자 인터페이스 {#web-ui}

다음 브라우저는 Campaign Web 사용자 인터페이스와 호환됩니다. [이 페이지에서](campaign-ui.md#ac-web-ui) Campaign Web UI에 대해 자세히 알아봅니다.

* **Microsoft Edge**, **Google Chrome**, **Safari**(최신 버전)

## 웹 액세스 {#web-access}

다음 브라우저는 웹 액세스용 Campaign과 호환됩니다. [이 페이지에서](connect.md#web-access) Campaign Web 액세스에 대해 자세히 알아봅니다.

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari**(최신 버전)

## 추가 리소스 {#support}

* [Campaign 릴리스 업데이트](upgrades.md)
* [Campaign 버전 확인](upgrades.md#version)
* [Campaign 클라이언트 콘솔 설치](connect.md)
* [컨트롤 패널 릴리스](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=ko){target="_blank"}

새로운 Experience Cloud 솔루션 릴리스에 대한 정보를 받으려면 [Adobe 주요 제품 업데이트](https://www.adobe.com/kr/subscription/priority-product-update.html){target="_blank"}를 구독하세요.