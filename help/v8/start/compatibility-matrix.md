---
solution: Campaign Classic
product: campaign
title: 캠페인 v8 호환성 표
description: Campaign v8과 호환되는 시스템 및 버전 학습
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
translation-type: tm+mt
source-git-commit: 29c13e6c1b08a5b0f6ba8bb433f7165e3e452942
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 27%

---

# 캠페인 v8 호환성 표

이 문서에서는 **Adobe Campaign v8**&#x200B;의 최신 빌드에 대해 지원되는 모든 시스템 및 구성 요소를 나열합니다. 이 목록에 포함되지 않은 제품 및 버전은 Adobe Campaign과 호환되지 않습니다.

>[!CAUTION]
>
>* 별도로 언급되지 않는 한 모든 부 릴리스가 지원됩니다.
>* 이러한 제3자 시스템 및 도구의 특정 버전이 EOL(End-of-Life)에 도달함에 따라 Adobe Campaign은 더 이상 해당 버전과 호환하지 않으며, 이 호환성 매트릭스에서 제거됩니다. 호환성 매트릭스에 나와 있는 모든 시스템의 지원 버전을 사용하고 있는지 확인하십시오.


## 호환 시스템

### CRM 커넥터{#CRMconnectors}

* **** Salesforeconnector API 버전 49
* **Microsoft** Dynamicssconnector, 웹 API:Dynamics 365 온프레미스 및 온라인

### FDA (FEDERATED DATA ACCESS){#FederatedDataAccessFDA}

* **Microsoft Azure Synapse Analytics**
* **Amazon Redshift**
* **[!DNL Snowflake]**
* **Oracle** 19c, 18c, 12c, 11G
* **PostgreSQL** 12.x, 11.x, 10.x, 9.6.x, 9.5.x, 9.4.x
* **Microsoft SQL Server** 2019, 2017, 2016, 2014, 2012 SP1 및 SP2
* **MySQL** 5.7
* **Teradata** 16.20, 16, 15.10, 15.0
* **Netezza** 7.2
* **sybase IQ** 16, ASE 15.7
* **SAP** HANAversion 1 SPS 12
* **Hadoop via HiveSQL**
   * HortonWorks HDP 2.4.X, 2.5.x, 2.6.x
   * HDInsight 3.4(HDP 2.4), 3.5(HDP 2.5), 3.6(HDP 2.6
   * Cloudera CDH6.x

### 클라이언트 콘솔 운영 체제{#ClientConsoleoperatingsystems}

* **Microsoft Windows Server** 2016, 2012
* **Microsoft Windows** 8, 10(일본어 인스턴스 권장)

### 모바일 SDK{#MobileSDK}

* **Android** 7.x, 8.x, 9.0(모바일 SDK 빌드 1.0.27).
* **Apple iOS** 9 - 모바일 SDK 빌드 1.0.26 14는 32비트 및 64비트 버전과 호환됩니다.

## 지원되는 브라우저 {#Browsers}

* **Microsoft Edge**,  **Mozilla Firefox**,  **Google Chrome**,  **Safari** (최신 버전)

* **Internet Explorer** 11

## 캠페인 버전을 확인하는 방법

**도움말 > 정보...** 메뉴를 사용하여 다음 정보에 액세스할 수 있습니다.

* 캠페인 클라이언트 콘솔 및 애플리케이션 서버의 버전 번호
* 캠페인 클라이언트 콘솔 및 애플리케이션 서버에 대한 빌드 번호
* Adobe 고객 지원 센터에 연락하는 링크
* Adobe 개인정보 보호정책, 사용 약관 및 쿠키 정책에 대한 링크
