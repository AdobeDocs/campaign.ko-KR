---
solution: Campaign Classic
product: campaign
title: Campaign Classic v7 - 캠페인 v8 기능 매트릭스
description: Campaign Classic v7과 Campaign v8 간의 차이점 이해
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
translation-type: tm+mt
source-git-commit: 04859274593f507a0b07f46cf6a65434b6a4bc60
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 2%

---

# Campaign Classic v7 - Campaign v8 기능{#gs-matrix}


기존 Campaign Classic v7 사용자는 일반적으로 Adobe Campaign을 &quot;재생&quot;하는 방식으로 큰 중단을 예상할 수 있습니다. UI와 구성 단계에 나타나는 작은 변경을 제외하고는 대부분의 변경 사항이 표시되지 않습니다.

주요 변경 사항:

* 최대 200배 더 빠르게 세그먼트 만들기

* 전달 속도 향상

* 실시간 보고

Campaign Classic 사용자는 Campaign Classic v7 기능 중 대부분은 [이 섹션](#gs-removed)에 나열된 작은 기능을 제외한 Campaign v8에서 사용할 수 있습니다. 다른 제품은 향후 릴리스에 제공될 예정입니다. [자세히 알아보기](#gs-unavailable-features)


## 제품 구성 변경 사항

### 캠페인 및 Snowflake {#ac-gs-snowflake}

클라우드 스토리지는 Snowflake에서 수행됩니다.새 외부 계정은 클라우드 데이터베이스와 연결을 보장합니다. [자세히 알아보기](#ac-gs-snowflake)

소프트웨어 아키텍처의 근본적인 변화입니다. 이제 데이터가 원격입니다.캠페인은 프로필을 포함한 전체 데이터를 통합합니다. 이제 캠페인 프로세스가 타깃팅에서 게재 실행까지 포괄적으로 조정됩니다.이제 데이터 통합, 세그멘테이션, 타깃팅, 쿼리, 배달 실행이 몇 분 후에 실행됩니다.

이 새로운 버전은 동일한 수준의 유연성과 확장성을 유지하면서 Scaling의 모든 문제를 해결합니다. 프로파일 수는 거의 제한이 없으며 데이터 유지율을 확장할 수 있습니다.

새로운 내장 **외부 계정**&#x200B;은(는) 정식 FDA를 위한 것입니다. 클라우드 데이터베이스 연결의 중심입니다. 지금 바로 출발하는 것이 좋습니다

클라우드 데이터베이스에서 이동 또는 복제해야 하는 내장 스키마/테이블은 네임스페이스 **xxl**&#x200B;에 내장된 스키마 확장명과 함께 제공됩니다. 스키마 확장의 경우 새 XXL 네임스페이스는 JavaScript, JSSP 등과 같은 새로운 OOTB 구성에 사용됩니다.

이러한 익스텐션은 내장된 스키마를 Campaign 로컬 데이터베이스에서 Snowflake Cloud 데이터베이스로 이동하고 그에 따라 해당 구조를 조정하는 데 필요한 모든 수정에 컨텐츠를 제공합니다.새로운 UUID, 업데이트된 링크 등

>[!CAUTION]
>
> 고객 데이터는 로컬 Campaign 데이터베이스에 저장되지 않습니다. 그 결과, 모든 사용자 정의 테이블을 클라우드 데이터베이스에서 만들어야 합니다.


### 데이터 복제

특정 기술 워크플로우는 양쪽에 모두 표시되어야 하는 테이블(Campaign 로컬 데이터베이스 및 클라우드 데이터베이스) 복제를 처리합니다. 이 워크플로우는 매 시간마다 트리거되며 새로운 내장 JavaScript 라이브러리를 사용합니다.

>[!NOTE]
>
> 테이블 크기(XS, XL 등)에 따라 여러 복제 정책이 생성되었습니다.
> 일부 테이블은 시간별로 복제되므로 실시간으로 복제됩니다. 일부 표에는 전체 업데이트이므로 증분 업데이트가 적용됩니다.


[데이터 복제에 대한 자세한 내용](../config/replication.md)

### ID 관리

이제 Campaign v8 개체에는 데이터를 식별하기 위한 무제한 고유 값을 의미하는 **UUID(Universal Unique ID)**&#x200B;가 사용됩니다

이 ID가 문자열 기반이고 순차적 내용이 아닙니다.

### 유지 관리 간소화

캠페인 사용자는 데이터베이스 전문가가 될 필요가 없습니다.더 이상 데이터베이스 유지 관리 긴 작업 과정이나 복잡한 테이블 인덱싱을 수행할 필요가 없습니다.

## 일시적으로 사용할 수 없는 기능{#gs-unavailable-features}

일부 기능은 이 첫 번째 버전에서는 사용할 수 없지만 다음과 같이 곧 릴리스될 예정입니다.

* 마케팅 리소스 관리
* 분산 마케팅
* 오퍼 관리 인바운드 메시지(상호 작용 모듈)
* 캠페인 최적화
* 반응 관리자
* twitter을 통한 소셜 마케팅
* 하이브리드/온-프레미스 배포 모델

## 제거된 기능{#gs-removed}

Campaign v8의 새로운 아키텍처 및 배포 모델에 맞춰 일부 이전 Campaign Classic v7 기능은 Campaign v8에서 사용할 수 없습니다.

* 쿠폰
* 웹 추적
* 설문 조사
* facebook을 사용한 소셜 마케팅
* ACS 커넥터(기본 제공)
* Microsoft SQL 데이터베이스
* Oracle 데이터베이스
