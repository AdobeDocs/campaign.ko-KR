---
title: Campaign API 시작
description: Campaign API 시작
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 94fc2739c538f3aa8b11e0ea69d08f1bfffb5d32
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 12%

---

# 시작하기 [!DNL Campaign] API{#gs-ac-api}

[!DNL Adobe Campaign] 에는 사용할 수 있는 Javascript 함수 세트가 포함되어 있습니다.

* 스크립트에서 - 위치 [!DNL Adobe Campaign] 워크플로우
* API를 통해 - 외부 시스템

JavaScript API를 사용하여 Campaign 클라우드 데이터베이스에 작성하거나 데이터베이스에서 읽을 수 있습니다.

* 각 객체에 대해 작업을 수행할 수 있는 비즈니스 특정 API: 게재, 워크플로우, 구독 등. 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html)를 참조하세요.
* 데이터 모델 데이터를 쿼리하기 위한 일반 데이터 액세스 API. 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html)를 참조하세요.

Campaign v8은 두 개의 데이터베이스에서 작동합니다. API를 통해 실시간 메시징 및 단일 쿼리 및 쓰기를 위한 사용자 인터페이스의 로컬 데이터베이스, 캠페인 실행, 보고, 데이터 수집, 배치 쿼리 및 워크플로우 실행을 위한 클라우드 데이터베이스.

>[!CAUTION]
>
>[!DNL Adobe Campaign] v8에는 API 레이어의 처리량(TPS)에 대한 제한이 있습니다. 이 제한을 초과하면 표준 HTTP 오류(429)가 발생합니다. 관리 Cloud Services 사용자는 Adobe에 연락하여 각 API에 대한 전송률 조절 기능을 조정할 수 있습니다.

## 전제 조건

사용하기 전 [!DNL Adobe Campaign] API를 사용하려면 다음 주제를 알고 있어야 합니다.

* JavaScript
* SOAP 프로토콜
* [!DNL Adobe Campaign] 데이터 모델

API를 사용하고 [!DNL Adobe Campaign]또한 데이터 모델에 익숙해야 합니다.

>[!NOTE]
>데이터 모델에 대한 전체 설명을 생성할 수 있습니다. [이 페이지](datamodel.md)에서 자세히 알아보십시오.

## [!DNL Campaign] API 스테이징 메커니즘

사용 [!DNL Campaign] 클라우드 데이터베이스인 경우 성능(지연 및 동시성)으로 인해 단일 호출을 권장하지 않습니다. 배치 작업이 항상 선호됩니다. API의 최적 성능을 보장하기 위해 Campaign은 로컬 데이터베이스 수준에서 API 호출을 계속 처리합니다.

![](../assets/do-not-localize/glass.png) [API 스테이징 메커니즘은 이 페이지에 자세히 설명되어 있습니다](staging.md)

## 새 API

새 API는 두 API 간에 데이터 동기화를 관리하는 데 사용할 수 있습니다 [!DNL Campaign] 로컬 데이터베이스 및 클라우드 데이터베이스. 지연을 방지하고 전체 성능을 향상시키기 위해 로컬 데이터베이스 수준에서 API 호출을 처리하는 새로운 메커니즘이 도입되었습니다.

![](../assets/do-not-localize/glass.png) [새 API는 이 페이지에 자세히 설명되어 있습니다](new-apis.md)

**관련 항목**

* [데이터 모델 모범 사례](datamodel-best-practices.md)
