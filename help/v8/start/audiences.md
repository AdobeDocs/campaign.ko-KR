---
title: Campaign에서 대상자를 사용하여 작업
description: Campaign에서 대상자를 사용하여 작업
feature: Audiences
role: User
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 59d33983db930b3a7dc022693d72704bda99e3a1
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 16%

---

# Campaign에서 대상자를 사용하여 작업{#gs-ac-audiences}

프로필은 Campaign 데이터베이스에 저장된 연락처입니다.

Adobe Campaign, **수신자** 게재(이메일, SMS 등)를 보낼 타겟팅된 기본 프로필입니다. 데이터베이스에 저장된 수신자 데이터를 사용하면 지정된 게재를 받을 대상을 필터링하고 게재 콘텐츠에 개인화 데이터를 추가할 수 있습니다. 데이터베이스에 다른 유형의 프로필이 있습니다. 다양한 용도로 디자인되어 있습니다. 예를 들어 최종 대상으로 전송되기 전에 시드 프로필을 테스트하여 게재를 테스트합니다.

프로필 및 대상자 가져오기, 업데이트 및 관리 방법 알아보기 [이 섹션에서](../audiences/gs-audiences.md).

## 목록 만들기{#create-lists}

목록은 게재 작업에서 타겟팅되거나 가져오기 또는 다른 워크플로우 작업 중에 업데이트될 수 있는 정적 연락처 집합입니다. 예를 들어 쿼리를 통해 데이터베이스에서 추출한 모집단을 목록으로 저장할 수 있습니다.

![](../assets/do-not-localize/glass.png) 에서 목록을 만들고 관리하는 방법 알아보기 [이 페이지](../audiences/create-audiences.md).

## 데이터베이스 필터링{#filter-the-database}

필터 구성을 통해 목록에서 데이터를 선택할 수 있습니다. **[!UICONTROL dynamically]**: 데이터가 수정되면 필터링된 데이터가 업데이트됩니다. 필터를 직접 만들거나 기본 제공 필터를 사용하여 타겟 대상자를 정의할 수 있습니다.

![](../assets/do-not-localize/glass.png) 에서 필터를 만들고 관리하는 방법 알아보기 [이 페이지](../audiences/create-filters.md).

## 워크플로우에서 대상자 만들기

워크플로우의 그래픽 시퀀스에서 쿼리의 조합을 통해 타깃팅을 만들 수 있습니다. 요구 사항에 따라 타겟팅할 대상을 만들 수 있습니다. 워크플로우 편집기를 표시하려면 **[!UICONTROL Targeting and workflows]** 캠페인 대시보드의 탭입니다.

캠페인 워크플로우에서 대상자를 만드는 방법 알아보기 [이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=ko)


## 활성 프로필 {#active-profiles}

활성 프로필은 고객이 지난 12개월 동안 모든 채널을 통해 통신하려고 시도한 프로필입니다. 라이선스 지표는 활성 프로필을 기반으로 합니다. 다음에서 자세히 알아보기 [Adobe Campaign 제품 설명](https://helpx.adobe.com/kr/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Campaign Campaign 컨트롤 패널에서 직접 인스턴스의 활성 프로필 수를 모니터링할 수 있습니다. 자세한 내용은 [Campaign 컨트롤 패널 설명서](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}.

>[!CAUTION]
>
>* 여러 게재에서 타겟팅한 프로필은 한 번만 카운트됩니다.
>
>* X의 소셜 마케팅(Twitter) 컨텍스트에서 타깃팅된 프로필은 활성 프로필로 간주되지 않습니다.

## 개인 정보 보호 및 동의{#privacy-and-consent}

Adobe Campaign은 개인 정보와 중요한 데이터를 포함한 많은 양의 데이터를 수집하고 처리할 수 있는 강력한 데이터 도구입니다. Adobe Campaign을 사용하면 개인 및 중요한 정보를 포함한 데이터를 수집할 수 있습니다. 따라서 수신자로부터 동의를 받고 모니터링하는 것이 중요합니다.

![](../assets/do-not-localize/book.png) 에서 개인 정보 및 동의를 관리하는 방법 알아보기 [Adobe Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=ko){target="_blank"}.

**관련 항목**

* [캠페인별 워크플로우 디자인 및 실행](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/campaign-workflows.html)

* [캠페인 대상자 선택 방법 알아보기](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=ko)

* [워크플로우 시작](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=ko)
