---
product: Adobe Campaign
title: Campaign v8 호환성 표
description: Campaign v8과 호환되는 시스템 및 버전 알아보기
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: f7e2581899d965975c129cac530a7edc6a2d55dd
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 75%

---

# Campaign v8 호환성 표

이 문서는 **Adobe Campaign v8**&#x200B;의 최신 빌드를 지원하는 모든 시스템 및 구성 요소를 나열합니다. 이 목록에 포함되지 않은 제품 및 버전은 Adobe Campaign과 호환되지 않습니다.

>[!CAUTION]
>
>* 별도로 언급되지 않는 한 모든 마이너 릴리스도 지원됩니다.
>* 이러한 타사 시스템 및 도구의 특정 버전이 EOL(End-of-Life)에 도달함에 따라 Adobe Campaign은 더 이상 해당 버전과 호환되지 않으며 이후 이 호환성 매트릭스에서 제거됩니다. 문제가 생기지 않도록 호환성 매트릭스에 나와 있는 모든 시스템의 지원 버전을 사용하고 있는지 확인하십시오.


## 호환 시스템

### 클라이언트 콘솔{#ClientConsoleoperatingsystems}

:경고:Campaign 클라이언트 콘솔을 사용하려면 다음 운영 체제와 브라우저가 필요합니다.

**운영 체제**

* **Microsoft Windows Server** 2016, 2012
* **Microsoft Windows** 8, 10(일본어 인스턴스에 권장))

**브라우저**

**Microsoft Internet Explorer** 11

### CRM 커넥터{#CRMconnectors}

* **Salesfore** connector API 버전 49
* **Microsoft Dynamics** connector, Web API: Dynamics 365 온프레미스 및 온라인

### FDA (Federated Data Access){#FederatedDataAccessFDA}

* **Amazon Redshift**
* **[!DNL Snowflake]**

### 모바일 SDK{#MobileSDK}

* **Android** 7.x, 8.x, 9.0(모바일 SDK 빌드 1.0.27).
* **Apple iOS** 9 – 14(모바일 SDK 빌드 1.0.26). 32비트 및 64비트 버전과 호환됩니다.

### 지원되는 브라우저 {#Browsers}

다음 브라우저는 웹 액세스에 대한 Campaign과 호환됩니다.

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari**(최신 버전)

* **Internet Explorer** 11

## Campaign 버전을 확인하는 방법 및 빌드

**도움말 > 정보..** 메뉴를 사용하여 버전을 확인하십시오.

![](assets/ac-version.png)

다음 정보에 액세스합니다.

* 클라이언트 콘솔 및 응용 프로그램 서버의 **버전** 번호입니다. 위의 샘플에서 버전은 클라이언트 콘솔과 애플리케이션 서버 모두에 대해 8.1.5입니다.
* 괄호 사이의 SHA 번호입니다.
* Adobe 고객 지원 센터에 문의하는 링크.
* Adobe 개인 정보 보호 정책, 사용 약관 및 쿠키 정책에 대한 링크입니다.
