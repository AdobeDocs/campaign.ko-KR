---
title: Campaign v8 호환성 표
description: Campaign v8과 호환되는 시스템 및 버전 알아보기
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: f89bc8baeb4b934bdde6b6fd33ee494195ab61b3
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 88%

---

# Campaign v8 호환성 표

이 문서는 **Adobe Campaign v8**&#x200B;의 최신 빌드를 지원하는 모든 시스템 및 구성 요소를 나열합니다. 별도로 언급되지 않는 한 모든 마이너 릴리스도 지원됩니다. 이 목록에 포함되지 않은 제품 및 버전은 Adobe Campaign과 호환되지 않습니다.

이러한 타사 시스템 및 도구의 특정 버전이 EOL(End-of-Life)에 도달함에 따라 Adobe Campaign은 더 이상 해당 버전과 호환되지 않으며 이후 이 호환성 매트릭스에서 제거됩니다. 문제가 생기지 않도록 호환성 매트릭스에 나와 있는 모든 시스템의 지원 버전을 사용하고 있는지 확인하십시오.

>[!NOTE]
>
>Adobe Campaign 서버와 클라이언트 콘솔의 버전은 동일해야 합니다. [버전을 확인하는 방법을 알아보세요](#version).

## 클라이언트 콘솔{#ClientConsoleoperatingsystems}

Campaign 클라이언트 콘솔을 사용하려면 다음 운영 체제와 브라우저가 필요합니다. [자세히 알아보기](connect.md)

### 운영 체제

* **Microsoft Windows Server** 2019년, 2016년, 2012년
* **Microsoft Windows** 11(Campaign v8.3 시작), 10, 8,

>[!NOTE]
>
>일본어 인스턴스에 대해 Microsoft Windows 10이 권장됩니다.

### 브라우저

**Microsoft Internet Explorer** 11

## CRM 커넥터{#CRMconnectors}

Adobe Campaign과 호환되는 CRM(고객 관계 관리) 시스템 목록은 다음과 같습니다. [자세히 알아보기](../connect/crm.md)

* **Salesfore** connector API 버전 49
* **Microsoft Dynamics** connector, Web API: Dynamics 365 온프레미스 및 온라인

## FDA(Federated Data Access){#FederatedDataAccessFDA}

Adobe Campaign FDA(Federated Data Access) 모듈과 호환되는 외부 데이터베이스 목록은 다음과 같습니다. [자세히 알아보기](../connect/fda.md)

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## 모바일 SDK{#MobileSDK}

다음 목록에 있는 운영 체제에서는 Campaign에서 연결된 모바일 SDK를 사용하여 [푸시 알림](../send/push.md)을 보낼 수 있습니다.

* **Android** 12(Campaign v8.3 시작), 9.0, 8.x, 7.x(Campaign Android SDK 빌드 1.1.1 사용)
* **Apple iOS** 9 - 15(Campaign iOS SDK 빌드 1.0.26 포함)는 32비트 및 64비트 버전과 호환됩니다. iOS 15는 Campaign v8부터 지원됩니다.

## 웹 액세스

다음 브라우저는 [웹 액세스](connect.md#web-access)용 Campaign과 호환됩니다.

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari**(최신 버전)

## Campaign 버전을 확인하고 빌드하는 방법{#version}

**도움말 및 정보…** 메뉴에 액세스하여 버전을 확인하세요.

![](assets/ac-version.png)

확인할 수 있는 정보:

* Campaign 클라이언트 콘솔 및 애플리케이션 서버의 **버전**. 위의 샘플에서는 클라이언트 콘솔과 애플리케이션 서버 모두 다 버전 8.1.5입니다.
* 괄호 사이에 있는 SHA 번호.
* Adobe 고객 지원 센터 연락을 위한 링크.
* Adobe 개인 정보 보호 정책, 사용 약관 및 쿠키 정책에 대한 링크.
