---
title: Campaign Classic v7 - Campaign v8 기능 매트릭스
description: Campaign Classic v7과 Campaign v8 간의 차이점 이해
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 0c01b0a597e54ae93dd581ccba6f19b2ff13f956
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 40%

---

# [!DNL Campaign Classic] v7 - [!DNL Campaign] v8 기능{#gs-matrix}

이전 [!DNL Campaign Classic] v7 사용자는 일반적으로 상호 작용하는 방식으로 큰 중단을 기대하지 마십시오 [!DNL Adobe Campaign]. v8의 변경 사항 대부분은 UI 및 구성 단계에 나타나는 작은 변경 사항을 제외하고는 사용자에게 표시되지 않습니다.

Adobe Campaign v8은 **관리 Cloud Service**. 이 새로운 오퍼링에서는 업계 최고의 서비스를 사전 예방적 관리와 시기 적절한 경고 기능을 결합하여 세 가지 영역에 초점을 맞추고 있습니다.

* **클라우드 민첩성** — Adobe에 의한 자동화, 보다 예측 가능한 성능, 뛰어난 민첩성 및 향상된 셀프 서비스 생산성을 위해 최적화된 표준화된 클라우드 배포를 제공합니다.
* **서비스 경험** — 사전 예방적 가용성, 용량, 성능 모니터링 및 응답으로 중단 방지, 장애 해결 속도 향상, 지속적인 개선을 위해 정기적으로 서비스 검토
* **Deep Campaign 전문 지식** — 전문 고객 엔지니어링 팀의 높은 친화성 서비스로 기능, 기술 또는 게재 능력 요구 사항을 충족하고 배포 위험을 줄이고 변경 관리를 개선합니다.

이전 [!DNL Campaign Classic] 사용자는 대부분의 [!DNL Campaign Classic] v7 기능은 [!DNL Campaign] v8, 여기에 나열된 작은 세트를 제외하고 [이 섹션](#gs-removed). 다른 기능은 향후 릴리스에서 제공될 예정입니다. [이 섹션에서 자세히 알아보기](#gs-unavailable-features)

>[!NOTE]
>
> Campaign v8은 하이브리드 아키텍처를 사용합니다. Campaign Classic v7에서 전환하는 경우 모든 게재는 중간 소싱 서버를 통과합니다. [자세히 알아보기](../architecture/architecture.md)
>
> 따라서 내부 라우팅은 **가능하지 않음** campaign v8에서 외부 계정이 그에 따라 비활성화되었습니다.


## [!DNL Campaign] 및 [!DNL Snowflake] {#ac-gs-snowflake}

Campaign v8은 [!DNL Snowflake]. 두 가지 배포 모델을 사용할 수 있습니다.

![](../assets/do-not-localize/glass.png) [!DNL Campaign] v8 아키텍처에 대한 자세한 내용은 [이 페이지](../architecture/architecture.md)를 참조하세요.


## Adobe ID을 사용하여 Campaign에 연결{#adobe-id}

Campaign 사용자는 Adobe ID을 통해 연결합니다. 동일한 Adobe ID을 사용하여 모든 Adobe Experience Cloud 솔루션에 대해 단일 계정과 연결된 모든 Adobe 계획 및 제품을 유지합니다.

![](../assets/do-not-localize/glass.png) [!DNL Campaign]에 연결하는 방법은 [이 페이지](connect.md)를 참조하세요.

## 큐브로 데이터 분석{#adobe-reporting}

Marketing Analytics 모듈을 사용하여 데이터를 분석 및 측정하고, 통계를 계산하며, 보고서 작성 및 계산을 간소화 및 최적화합니다. 또한 보고서를 만들고 대상 모집단을 빌드합니다. 식별되면 Adobe Campaign에서 사용할 수 있는 목록(타깃팅, 세그멘테이션 등)에 저장됩니다.

Adobe Campaign 큐브 보고서는 Campaign Classic v7보다 최적화되고 더 나은 확장 기능을 제공합니다. 큐브에 대한 이전 제한 사항은 Campaign v8에서 적용되지 않습니다.

## 데이터 소스 변경 {#change-data-source}

Campaign v8에서는 추가적인 타겟팅 워크플로우 활동으로 **[!UICONTROL Change data source]**&#x200B;를 제공합니다.

**[!UICONTROL Change data source]** 활동을 사용하면 워크플로우의 데이터 소스 **[!UICONTROL Working table]**&#x200B;을 변경하여 FDA, FFDA 및 로컬 데이터베이스와 같은 다양한 데이터 소스에 걸쳐 데이터를 관리할 수 있습니다.

![](../assets/do-not-localize/glass.png) **[!UICONTROL Change data source]** 활동에 대한 자세한 내용은 [이 페이지](../config/workflows.md#change-data-source-activity)를 참조하세요.

## 사용할 수 없는 기능{#gs-unavailable-features}

다음과 같은 일부 기능은 이 버전에서 아직 사용할 수 없습니다.

* 마케팅 리소스 관리
* 하이브리드/온-프레미스 배포 모델

>[!CAUTION]
>
>* 현재 Campaign v8은 관리 클라우드 서비스로&#x200B;**만** 사용할 수 있으며, 온-프레미스 또는 하이브리드 환경에 배포할 수 없습니다.
>
>* 기존 Campaign Classic v7 환경에서의 마이그레이션은 아직 불가능합니다.
>
>* 배포 모델을 잘 모르거나 질문이 있는 경우 Adobe 계정 담당자에게 문의하십시오.


## 지원되지 않는 기능{#gs-removed}

Campaign v8의 새로운 아키텍처 및 배포 모델에 맞게 이전 Campaign Classic v7의 일부 기능은 Campaign v8에서 더 이상 사용할 수 없습니다:

* 쿠폰
* 웹 추적
* 설문 조사
* 소셜 마케팅
* ACS 커넥터(프라임 제공)
* LDAP와 통합
* 사용자/암호 로그인

>[!NOTE]
>
>사용 가능하지 않거나 지원되지 않는 일부 기능이 사용자 인터페이스에 계속 표시될 수 있습니다.
