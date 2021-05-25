---
solution: Campaign v8
product: Adobe Campaign
title: Campaign API 시작
description: Campaign API 시작
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 4%

---

# [!DNL Campaign] API{#gs-ac-api} 시작

[!DNL Adobe Campaign] 에는 사용할 수 있는 Javascript 함수 세트가 포함되어 있습니다.

* 스크립트에서 - [!DNL Adobe Campaign] 워크플로우에서
* API를 통해 - 외부 시스템

Javascript API를 사용하여 Campaign 클라우드 데이터베이스에 작성하거나 데이터베이스에서 읽을 수 있습니다.

* 각 객체에 대해 작업을 수행할 수 있는 비즈니스 특정 API:게재, 워크플로우, 구독 등 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html)를 참조하십시오.
* 일반 데이터는 데이터 모델 데이터를 쿼리하기 위해 API에 액세스합니다. 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html)를 참조하십시오.

Campaign v8은 두 개의 데이터베이스에서 작동합니다.API를 통해 실시간 메시징 및 단일 쿼리 및 쓰기를 위한 사용자 인터페이스의 로컬 데이터베이스, 캠페인 실행, 보고, 데이터 수집, 배치 쿼리 및 워크플로우 실행을 위한 클라우드 데이터베이스.

>[!CAUTION]
>
>[!DNL Adobe Campaign] v8에는 API 레이어의 처리량(TPS)에 대한 제한이 있습니다. 이 제한을 초과하면 표준 HTTP 오류(429)가 발생합니다. 관리 Cloud Services 사용자는 Adobe에 연락하여 각 API에 대한 전송률 조절 기능을 조정할 수 있습니다.


## 필수 구성 요소

[!DNL Adobe Campaign] API를 사용하기 전에 다음 주제를 알고 있어야 합니다.

* Javascript
* SOAP 프로토콜
* [!DNL Adobe Campaign] 데이터 모델

API를 사용하고 [!DNL Adobe Campaign]과 상호 작용하려면 데이터 모델에 대해서도 알고 있어야 합니다.

>[!NOTE]
>데이터 모델에 대한 전체 설명을 생성할 수 있습니다. 자세한 내용은 [이 페이지](datamodel.md)를 참조하십시오.

## [!DNL Campaign] API 스테이징 메커니즘

[!DNL Campaign] 클라우드 데이터베이스를 사용하면 성능(지연 및 동시성)으로 인해 단일 호출을 권장하지 않습니다. 배치 작업이 항상 선호됩니다. API의 최적 성능을 보장하기 위해 Campaign은 로컬 데이터베이스 수준에서 API 호출을 계속 처리합니다.

:[API 스테이징 메커니즘이 이 이 페이지에 자세히 설명되어 있습니다](staging.md)

## 새 API

새 API는 [!DNL Campaign] 로컬 데이터베이스와 클라우드 데이터베이스 간의 데이터 동기화를 관리하는 데 사용할 수 있습니다. 지연을 방지하고 전체 성능을 향상시키기 위해 로컬 데이터베이스 수준에서 API 호출을 처리하는 새로운 메커니즘이 도입되었습니다

:[새 API는 이 페이지에 자세히 설명되어 있습니다](new-apis.md)

**관련 항목**

* [데이터 모델 모범 사례](datamodel-best-practices.md)
