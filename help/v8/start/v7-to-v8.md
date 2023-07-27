---
title: Campaign Classic v7에서 Campaign v8로 전환
description: Campaign Classic v7과 Campaign v8 간의 차이점에 대해 알아봅니다.
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 2d0c82df052c9b8c9f264c2ad15ac6050025f770
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 92%

---

# [!DNL Campaign Classic] v7에서 [!DNL Campaign] v8로 전환{#gs-matrix}

기존 [!DNL Campaign Classic] v7 사용자라면 [!DNL Adobe Campaign]과(와)의 상호 작용 방식을 크게 바꿀 필요가 없습니다. v8의 변경 사항 대부분은 UI 및 구성 단계에 나타나는 작은 변경 사항을 제외하고는 사용자에게 표시되지 않습니다.

>[!AVAILABILITY]
>
>* 현재 Campaign v8은 관리 클라우드 서비스로&#x200B;**만** 사용할 수 있으며, 온-프레미스 또는 하이브리드 환경에 배포할 수 없습니다. [자세히 알아보기](#cloud-services)
>
>* 기존 Campaign Classic v7 환경에서의 자동 마이그레이션은 아직 불가능합니다.


## 관리 클라우드 서비스{#cloud-services}

Adobe Campaign v8은 **관리 클라우드 서비스**&#x200B;로 사용 가능합니다.

Adobe Campaign 관리 클라우드 서비스는 크로스 채널 고객 경험을 설계하기 위한 관리 클라우드 서비스 플랫폼과 함께 시각적 캠페인 오케스트레이션, 실시간 상호 작용 관리, 크로스 채널 실행 환경을 제공합니다. 에서 Campaign 관리 Cloud Services에 대해 자세히 알아보십시오. [제품 설명 페이지](https://helpx.adobe.com/kr/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

이 새로운 버전에서는 업계 최고의 서비스를 사전 예방적 관리와 시기 적절한 경고 기능을 결합했으며 세 가지 영역에 초점을 맞춥니다.

* **클라우드 민첩성** — Adobe에 의해 자동화되었고, 최적화되었고 표준화된 클라우드 배포로 더욱 예측 가능한 성능, 우수한 민첩성, 향상된 셀프 서비스 생산성을 제공합니다.
* **서비스 경험** — 사전 예방적 가용성, 용량, 성능 모니터링 및 응답으로 중단을 방지하고, 장애 해결 속도를 높이고, 정기적으로 서비스를 검토하여 지속적으로 개선됩니다.
* **심층적인 Campaign 전문 지식** — 전문 고객 엔지니어링 팀의 높은 친화성 서비스로 기능, 기술 또는 게재 능력 요구 사항을 충족하고 배포 위험을 줄이고 변경 관리를 개선합니다.

이전 [!DNL Campaign Classic] 사용자는 대부분의 [!DNL Campaign Classic] v7 기능을 [!DNL Campaign] v8에서도 사용할 수 있습니다(일부 예외 사항: [이 섹션](#gs-removed) 참조).

Campaign v8은 **하이브리드 아키텍처**. Campaign Classic v7에서 전환하는 경우 모든 게재는 중간 소싱 서버를 거칩니다. 따라서 내부 라우팅은 Campaign v8에서 **불가능**&#x200B;하며, 외부 계정이 이에 따라 비활성화되었습니다. [자세히 알아보기](../architecture/architecture.md)

>[!NOTE]
>
>새로운 클라우드 아키텍처를 통해 Campaign은 프로세스를 간소화하고, 비용을 절감하고, 위험을 관리하고, 데이터 보안을 개선할 수 있습니다. Campaign v8 환경에는 사전 구성된 전용 Virtual Private Cloud(VPC)가 포함되어 있습니다.

## [!DNL Campaign] 및 [!DNL Snowflake] {#ac-gs-snowflake}

Campaign v8은 [!DNL Snowflake]과(와) 함께 사용 가능합니다.

[엔터프라이즈(FFDA) 배포](../architecture/enterprise-deployment.md)에서 [!DNL Adobe Campaign] v8은 두 개의 데이터베이스를 사용합니다. 하나는 사용자 인터페이스 실시간 메시지 보내기와 API를 통한 단일 쿼리 및 쓰기를 위한 로컬 [!DNL Campaign] 데이터베이스이고, 다른 하나는 캠페인 실행, 쿼리 일괄 처리 및 워크플로우 실행을 위한 클라우드[!DNL Snowflake] 데이터베이스입니다.

Campaign v8 Enterprise는 **FFDA(Full Federated Data Access)** 개념을 도입했습니다. 이제 모든 데이터는 클라우드 데이터베이스에서 원격으로 사용할 수 있습니다. Campaign v8 엔터프라이즈(FFDA) 배포는 이 새로운 아키텍처를 통해 데이터 관리를 간소화하므로 클라우드 데이터베이스에 인덱스를 작성할 필요가 없습니다. 표를 만들고 데이터를 복사하기만 하면 바로 시작할 수 있습니다. 클라우드 데이터베이스 기술은 성능 수준을 보장하기 위해 특정한 유지 관리가 필요 없습니다.

![](../assets/do-not-localize/glass.png) [!DNL Campaign] v8 아키텍처에 대한 자세한 내용은 [이 페이지](../architecture/architecture.md)를 참조하세요.


## Adobe ID를 사용하여 Campaign에 연결{#adobe-id}

Campaign 사용자는 Adobe ID를 통해서만 연결합니다. 동일한 Adobe ID를 사용하여 모든 Adobe Experience Cloud 솔루션에 대해 하나의 계정과 연결된 모든 Adobe 플랜 및 제품을 유지합니다.

![](../assets/do-not-localize/glass.png) [!DNL Campaign]에 연결하는 방법은 [이 페이지](connect.md)를 참조하세요.

## 큐브로 데이터 분석{#adobe-reporting}

Marketing Analytics 모듈을 사용하여 데이터를 분석 및 측정하고, 통계를 계산하며, 보고서 작성 및 계산을 간소화 및 최적화합니다. 또한 보고서를 만들고 대상 모집단을 빌드합니다. 식별되면 Adobe Campaign에서 사용할 수 있는 목록(타겟팅, 세그멘테이션 등)에 저장됩니다.

Adobe Campaign v8에서 큐브 보고서는 최적화되어 있으며 Campaign Classic v7보다 더 나은 확장 기능을 제공합니다. 해당 특정 배포 모델에서는 큐브에 대한 이전 제한 사항이 Campaign v8에 적용되지 않습니다. 큐브에 대한 자세한 내용은[이 섹션](../../v8/reporting/gs-cubes.md)을 참조하십시오.

## 사용할 수 없는 기능{#gs-unavailable-features}

Campaign의 [엔터프라이즈(FFDA) 배포](../architecture/enterprise-deployment.md) 컨텍스터에서는 일부 기능이 제공되지 않습니다. 예:

* 마케팅 리소스 관리
* 쿠폰
* 웹 추적
* 설문 조사

## 지원되지 않는 기능{#gs-removed}

일부 이전 Campaign Classic v7 기능은 다음과 같은 Campaign v8에서 더 이상 지원되지 않습니다:

* Facebook을 사용한 소셜 마케팅
* ACS 커넥터(프라임 제공)
* LDAP와 통합
* 사용자/암호 로그인
* 하이브리드/온-프레미스 배포 모델


>[!NOTE]
>
>사용할 수 없거나 지원되지 않는 기능 중 일부는 계속 사용자 인터페이스에 표시될 수 있습니다.
