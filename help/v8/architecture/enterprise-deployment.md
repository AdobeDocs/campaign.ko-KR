---
title: Campaign FDA 배포 시작
description: Campaign FDA 배포 시작
feature: Architecture, FFDA
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 0a6f6701-b137-4320-9732-31946509ee03
source-git-commit: 51bba0a2b4be03577f508d352fc7c2b514ba28e5
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 54%

---

# [!DNL Campaign] FFDA 배포{#gs-ac-ffda}

활용 [[!DNL Snowflake]](https://www.snowflake.com/)클라우드 데이터베이스 기술인 Adobe Campaign FDA(Enterprise Full Federated Access) 배포는 크기와 속도를 크게 향상시키며, 더 많은 수의 고객 프로필을 관리할 수 있을 뿐만 아니라 시간당 훨씬 더 높은 전송률 및 트랜잭션을 관리할 수 있습니다.

## 이점 {#ffda-benefits}

Campaign v8 Enterprise(FFDA)는 타깃팅에서 최종 보고에 이르기까지 프로세스의 모든 단계에서 종단 간 확장을 제공합니다.

* 처리할 수 있는 데이터 볼륨의 크기 조절(8TB까지)
* 세분화 및 타겟팅 외에도 데이터 수집 및 가져오기를 위한 쿼리 성능의 크기 조절
* 게재 준비 단위 조절(시간 ~ 분)

소프트웨어 아키텍처의 근본적인 변화입니다. 이제 데이터는 원격지에 있으며 Campaign은 프로필을 포함한 전체 데이터를 통합합니다. 이제 [!DNL Campaign] 프로세스가 타기팅에서 메시지 실행에 이르기까지 전체 프로세스를 확장합니다. 데이터 수집, 세분화, 타기팅, 쿼리, 게재는 이제 일반적으로 몇 분 내에 실행됩니다. 이 새로운 버전은 동일한 수준의 유연성과 확장성을 유지하면서 크기를 조절해야 하는 문제 전체를 해결합니다. 프로필 수는 거의 제한이 없으며 데이터 유지율을 확장할 수 있습니다.

클라우드 스토리지는 **[!DNL Snowflake]**&#x200B;에서 수행됩니다. Snowflake는 새로운 기본 제공 **외부 계정**&#x200B;으로 클라우드 데이터베이스와의 연결을 보장합니다. 이는 Adobe에서 구성하며 수정해서는 안 됩니다. [자세히 알아보기](../config/external-accounts.md)

클라우드 데이터베이스에서 이동하거나 복제해야 하는 내장 스키마/테이블은 **xxl** 네임스페이스 아래에 내장된 스키마 확장과 함께 제공됩니다. 이 확장에는 내장된 스키마를 [!DNL Campaign] 로컬 데이터베이스에서 [!DNL Snowflake] 클라우드 데이터베이스로 이동하고 그에 따라 새로운 UUID, 업데이트된 링크 등 해당 구조를 조정하는 데 필요한 수정 사항이 모두 포함됩니다.

>[!CAUTION]
>
> 고객 데이터는 [!DNL Campaign] 로컬 데이터베이스에 저장되지 않습니다. 따라서 모든 사용자 정의 테이블을 클라우드 데이터베이스에서 만들어야 합니다.

## Campaign Enterprise (FFDA) 아키텍처{#ffda-archi}

에서 [엔터프라이즈(FFDA) 배포](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] v8은 두 개의 데이터베이스에서 작동합니다. 지역 [!DNL Campaign] 사용자 인터페이스 실시간 메시징 및 단일 쿼리 및 API를 통한 쓰기 및 클라우드에 대한 데이터베이스 [!DNL Snowflake] 캠페인 실행, 배치 쿼리 및 워크플로우 실행을 위한 데이터베이스.

Campaign v8 Enterprise는 **FFDA(Full Federated Data Access)** 개념을 도입했습니다. 이제 모든 데이터는 클라우드 데이터베이스에서 원격으로 사용할 수 있습니다.

로컬 및 클라우드 데이터베이스 간에 데이터를 관리하는 데 특정 API를 사용할 수 있습니다. [이 페이지](new-apis.md)에서는 이 새로운 API의 작동 방식과 사용법을 알아봅니다.

서버와 프로세스 간의 일반 통신은 다음 스키마에 따라 수행됩니다.

![](assets/architecture.png)

* 인스턴스에서 실행 및 반송 관리 모듈을 사용할 수 없습니다.
* 이 애플리케이션은 SOAP 호출(HTTP 또는 HTTPS를 통해)을 사용하여 구동되는 원격 &quot;mid 소스&quot; 서버에서 메시지 실행을 수행하도록 구성됩니다.

다음 [!DNL Snowflake] 마케팅 측 데이터베이스는 다음과 같은 데 사용됩니다.

* 모든 고객 데이터 저장: 프로필, 트랜잭션, 제품, 위치 등의 사용자 지정 데이터.
* 게재 로그, 추적 로그, 푸시 등록 등과 같이 Campaign에서 생성 또는 수집한 모든 이벤트 및 동작 데이터를 저장합니다.
* 위의 모든 데이터 합계를 저장합니다.
* 참조 테이블(예: 게재, 열거형, 국가 등)의 사본(h+1)을 저장합니다. 워크플로우, 캠페인 및 보고서에 사용됩니다.
* 모든 일괄 처리 프로세스 및 워크로드 실행


마케팅 인스턴스의 PostgreSQL 데이터베이스를 사용하여 다음을 수행합니다.

* 낮은 볼륨 API와 같은 특정 워크로드를 실행합니다.
* 게재 및 캠페인 설정, 워크플로우 및 서비스 정의를 포함하여 모든 Campaign 데이터를 저장합니다.
* 기본 제공 참조 테이블(열거형, 국가 등)을 모두 저장합니다. 복제 대상 [!DNL Snowflake].

   그러나 다음을 수행할 수 없습니다.
   * 고객 데이터에 대한 사용자 지정 만들기(예: PostgreSQL에서 일반 테이블을 만들지 않고 Snowflake에서만)
   * 게재 로그, 추적 로그 등을 저장합니다. FFDA 타겟팅 차원에 있습니다.
   * 많은 양의 데이터를 저장합니다.


중간 소싱 인스턴스의 PostgreSQL 데이터베이스를 사용하여 다음을 수행할 수 있습니다.

* 배치 및 실시간(RT) 게재를 실행합니다.
* 게재 및 추적 로그 전송 - 게재 및 추적 로그 ID는 32비트 ID가 아니라 UUID입니다.
* 추적 데이터를 수집 및 저장합니다.


## 영향{#ffda-impacts}

### [!DNL Campaign] API 스테이징 메커니즘{#staging-api}

사용 [!DNL Campaign] 클라우드 데이터베이스인 경우 성능(지연 및 동시성)으로 인해 단일 호출을 권장하지 않습니다. 배치 작업이 항상 선호됩니다. API의 최적 성능을 보장하기 위해 Campaign은 로컬 데이터베이스 수준에서 API 호출을 계속 처리합니다.

![](../assets/do-not-localize/glass.png) [API 스테이징 메커니즘은 이 페이지에 자세히 설명되어 있습니다](staging.md)

### 새 API{#new-apis}

새 API는 두 API 간에 데이터 동기화를 관리하는 데 사용할 수 있습니다 [!DNL Campaign] 로컬 데이터베이스 및 클라우드 데이터베이스. 지연을 방지하고 전체 성능을 향상시키기 위해 로컬 데이터베이스 수준에서 API 호출을 처리하는 새로운 메커니즘이 도입되었습니다.

![](../assets/do-not-localize/glass.png) [새 API는 이 페이지에 자세히 설명되어 있습니다](new-apis.md)


### 데이터 복제{#data-replication}

특정 기술 워크플로우는 양쪽(Campaign 로컬 데이터베이스와 클라우드 데이터베이스)에 모두 표시되어야 하는 테이블 복제를 처리합니다. 이 워크플로우는 매 시간마다 트리거되며 새로운 내장 JavaScript 라이브러리를 사용합니다.

>[!NOTE]
>
> 테이블 크기(XS, XL 등)에 따라 여러 복제 정책이 생성되었습니다.
> 일부 테이블은 실시간으로 복제되고 다른 테이블은 시간별로 복제됩니다. 일부 테이블에는 증분 업데이트가 적용되고 다른 테이블에는 전체 업데이트가 적용됩니다.

[데이터 복제 자세히 알아보기](replication.md)

### ID 관리{#id-mgt-ffda}

이제 Campaign v8 개체에는 데이터를 식별하는 데 제한 없는 고유 값을 사용할 수 있는 **UUID(범용 고유 ID)**&#x200B;가 사용됩니다.

이 ID는 문자열 기반이며 순차적이 아님에 유의하세요. 기본 키는 Campaign v8에서 숫자 값이 아니므로 스키마에서 **autouid** 및 **autok** 속성을 사용해야 합니다.

Campaign Classic v7 및 이전 버전에서 스키마(즉 테이블) 내의 키 독자성은 데이터베이스 엔진 수준에서 처리됩니다. 일반적으로 PostgreSQL, Oracle 또는 SQL Server와 같은 클래식 데이터베이스 엔진에는 기본 키 및/또는 고유 인덱스를 통해 열 또는 열 세트를 기반으로 중복 행 삽입을 방지하는 기본 메커니즘이 포함되어 있습니다. 이 버전에서는 데이터베이스 수준에서 적절한 인덱스 및 기본 키를 설정한 경우 중복 ID가 존재하지 않습니다.

Adobe Campaign v8에는 핵심 데이터베이스로 Snowflake가 포함되어 있습니다. 쿼리 크기가 크게 증가함에 따라 Snowflake 데이터베이스의 분산 아키텍처는 이와 같이 테이블 내에서 키 독자성을 관리하는 메커니즘을 제공하지 않습니다. 따라서 Adobe Campaign v8에서는 테이블에서 중복 키를 수집하는 것을 방지하는 장치가 없습니다. 이제 Adobe Campaign 데이터베이스 내의 키 독자성을 유지할 책임은 최종 사용자에게 있습니다. [자세히 알아보기](keys.md)

### 기능 가용성 {#feature-availability}

일부 기능은 Campaign의 FFDA(Enterprise) 배포 컨텍스트에서 사용할 수 없습니다. 예를 들면 다음과 같습니다.

* 마케팅 리소스 관리
* 쿠폰
* 웹 추적
* 설문 조사


**관련 항목**

* [데이터 모델 모범 사례](../dev/datamodel-best-practices.md)
