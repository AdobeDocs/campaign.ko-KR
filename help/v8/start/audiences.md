---
title: Campaign에서 대상자를 사용한 작업
description: Campaign에서 대상자를 사용한 작업
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 0a55d947a7646aab64ab2f9d0d09a6f930db576e
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 18%

---

# Campaign에서 대상자를 사용한 작업{#gs-ac-audiences}

프로필은 Campaign 데이터베이스에 저장된 연락처입니다.

Adobe Campaign에서, **수신자** 게재(이메일, SMS 등)를 보낼 타겟팅된 기본 프로필입니다. 데이터베이스에 저장된 수신자 데이터를 사용하면 주어진 게재를 받을 대상을 필터링하고 게재 콘텐츠에 개인화 데이터를 추가할 수 있습니다. 데이터베이스에 다른 유형의 프로필이 있습니다. 다양한 용도로 디자인되어 있습니다. 예를 들어 최종 대상으로 전송되기 전에 시드 프로필을 테스트하여 게재를 테스트합니다.

프로필 및 대상자를 가져오기, 업데이트 및 관리하는 방법을 알아봅니다 [이 섹션](../audiences/gs-audiences.md).

## 목록 만들기{#create-lists}

목록은 게재 작업에서 타겟팅되거나 가져오기 또는 다른 워크플로우 작업 중에 업데이트될 수 있는 정적 연락처 세트입니다. 예를 들어 쿼리를 통해 데이터베이스에서 추출한 모집단은 목록으로 저장할 수 있습니다.

![](../assets/do-not-localize/glass.png) 에서 목록을 만들고 관리하는 방법을 알아봅니다. [이 페이지](../audiences/create-audiences.md).

## 데이터베이스 필터링{#filter-the-database}

필터 구성을 사용하면 목록에서 데이터를 선택할 수 있습니다 **[!UICONTROL dynamically]**: 데이터가 수정되면 필터링된 데이터가 업데이트됩니다. 자신만의 필터를 만들거나 내장된 필터를 사용하여 타겟 대상을 정의할 수 있습니다.

![](../assets/do-not-localize/glass.png) 에서 필터를 만들고 관리하는 방법을 알아봅니다. [이 페이지](../audiences/create-filters.md).

## 워크플로우에서 대상자 만들기

워크플로우의 그래픽 시퀀스에서 쿼리 조합을 통해 타겟팅을 만들 수 있습니다. 요구 사항에 따라 타겟팅할 대상을 만들 수 있습니다. 워크플로우 편집기를 표시하려면 **[!UICONTROL Targeting and workflows]** campaign 대시보드의 탭입니다.

에서 캠페인 워크플로우에서 대상을 만드는 방법을 알아봅니다 [이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html)


## 활성 프로필{#active-profiles}

계약에 따라 각 캠페인 인스턴스에는 청구 용도로 계산되는 특정 수의 활성 프로필이 제공됩니다. 구입한 활성 프로필 수에 대한 자세한 내용은 최신 계약서를 참조하십시오.

**프로필** 는 정보의 기록(예: 그 곳의 기록 [수신자 테이블](../dev/datamodel.md) 또는 최종 고객, 잠재 고객 또는 리드를 나타내는 쿠키 ID, 고객 ID, 모바일 식별자 또는 특정 채널과 관련된 기타 정보가 포함된 외부 테이블. 지난 12개월 이내에 모든 채널을 통해 프로필을 타겟팅하거나 통신한 경우 프로필이 활성 상태로 간주됩니다.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

![](../assets/do-not-localize/book.png) For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

## 개인 정보 보호 및 동의{#privacy-and-consent}

Adobe Campaign은 개인 정보와 중요한 데이터를 포함한 많은 양의 데이터를 수집하고 처리할 수 있는 강력한 데이터 도구입니다. Adobe Campaign을 사용하면 개인 및 중요한 정보를 포함한 데이터를 수집할 수 있습니다. 따라서 수신자로부터 동의를 받고 모니터링하는 것이 중요합니다.

![](../assets/do-not-localize/book.png) 에서 개인 정보 및 동의를 관리하는 방법을 알아봅니다 [Adobe Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=ko){target=&quot;_blank&quot;}.

**관련 항목**

* [캠페인별 워크플로우 디자인 및 실행](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/campaign-workflows.html)

* [캠페인 대상자를 선택하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html)

* [워크플로우 시작](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html)
