---
solution: Campaign
product: Adobe Campaign
title: 대상 시작하기
description: 대상 시작하기
feature: 대상
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
translation-type: tm+mt
source-git-commit: 3870395ec74dd51ed42944981a3851d1052ee255
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 26%

---

# 대상 시작{#gs-ac-audiences}

프로파일을 목록으로 그룹화하거나 데이터베이스를 쿼리하여 수집할 수 있습니다.

## 프로필 작업{#gs-ac-profiles}

프로필은 클라우드 데이터베이스에 중앙에서 관리됩니다. 프로필을 가져오고 이 데이터베이스를 빌드하는 데 사용할 수 있는 메커니즘은 웹 양식을 통한 온라인 수집, 텍스트 파일 수동 또는 자동 가져오기, 회사 데이터베이스 또는 기타 정보 시스템을 사용한 복제와 같이 다양합니다. Adobe Campaign을 사용하면 마케팅 내역, 구매 정보, 환경 설정, CRM 데이터 및 관련 PI 데이터를 통합 뷰에 통합하여 분석하고 조치를 취할 수 있습니다.

&quot;**프로필**&quot;은 고객, 잠재 고객, 뉴스레터 가입자 등을 나타내는 정보 기록을 의미합니다.
**nmsRecipient** 표 또는 외부 테이블의 레코드에는 쿠키 ID, 고객 ID, 모바일 식별자 또는 특정 채널과 관련된 기타 정보가 포함됩니다. [이 섹션](../dev/datamodel.md#ootb-profiles)에서 내장 프로필 및 수신자 표에 대해 자세히 알아보십시오.

Adobe Campaign에서 수신자는 게재(전자 메일, SMS 등)를 보낼 타겟팅된 기본 프로필입니다. 데이터베이스에 저장된 수신자 데이터를 사용하면 주어진 배달을 받을 대상을 필터링하고 배달 내용에 개인화 데이터를 추가할 수 있습니다. 데이터베이스에 다른 유형의 프로필이 있습니다. 다양한 용도로 디자인되어 있습니다. 예를 들어 최종 대상으로 전송되기 전에 시드 프로필을 테스트하여 게재를 테스트합니다.

:arrow_forward:[비디오](https://video.tv.adobe.com/v/35611?quality=12)에 있는 프로필의 내용 이해

:arrow_upper_right:[이 안내서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html)에서 프로필을 관리하는 방법을 알아봅니다.

## 개인 정보 및 동의

Adobe Campaign은 개인 정보와 중요한 데이터를 포함한 많은 양의 데이터를 수집하고 처리할 수 있는 강력한 데이터 도구입니다. Adobe Campaign을 사용하면 개인 및 중요한 정보를 포함한 데이터를 수집할 수 있습니다. 따라서 수신자로부터 동의를 받고 모니터링하는 것이 중요합니다.

:arrow_upper_right:[이 안내서](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html)에서 개인 정보 및 동의를 관리하는 방법을 알아봅니다.


## 목록 만들기

목록은 가져오기 작업 또는 워크플로우 실행 중에 배달 작업에서 타깃팅하거나 업데이트할 수 있는 정적 프로필 집합입니다. 예를 들어 쿼리를 통해 데이터베이스에서 추출한 모집단은 목록을 제공할 수 있습니다.

:arrow_upper_right:[이 섹션](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html)에서 목록을 만들고 관리하는 방법을 알아봅니다.

## 데이터베이스 쿼리

워크플로우에서 **쿼리** 활동을 사용하여 데이터베이스를 쿼리하고 데이터를 세그먼트화하고 복잡한 대상을 빌드합니다.

:arrow_upper_right:[이 안내서](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html)에서 캠페인 쿼리에 대해 자세히 알아보십시오.

:arrow_upper_right:모든 타깃팅 활동은 [이 페이지](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html)에 나열됩니다.

## 워크플로우에서 대상자 만들기

타깃팅은 워크플로에서 그래픽 시퀀스의 쿼리 조합을 통해 만들 수 있습니다. 요구 사항에 따라 타깃팅할 대상을 만들 수 있습니다. 워크플로우 편집기를 표시하려면 캠페인 대시보드에서 **[!UICONTROL Targeting and workflows]** 탭을 클릭합니다.

:arrow_upper_right:[이 페이지]https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)에서 캠페인 워크플로우에서 대상을 빌드하는 방법을 알아봅니다.


## 활성 프로필{#active-profiles}

계약에 따라 각 캠페인 인스턴스에는 청구 용도로 계산되는 특정 양의 활성 프로필이 제공됩니다. 구입한 활성 프로필 수에 대한 자세한 내용은 최신 계약서를 참조하십시오.

&quot;프로파일&quot;은 정보 기록을 의미합니다(예:최종 고객, 잠재 고객 또는 리드를 나타내는 [수신자 테이블](../dev/datamodel.md)의 레코드 또는 특정 채널과 관련된 쿠키 ID, 고객 ID, 모바일 식별자 또는 기타 정보가 들어 있는 외부 테이블의 레코드입니다. 지난 12개월 이내에 모든 채널을 통해 프로파일을 타깃팅하거나 커뮤니케이션한 경우 프로파일이 활성 상태로 간주됩니다.

캠페인 Campaign 컨트롤 패널에서 직접 인스턴스에 사용된 활성 프로필 수를 모니터링할 수 있습니다.

:arrow_upper_right:자세한 내용은 [Campaign 컨트롤 패널 설명서](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html)를 참조하십시오.


**관련 항목**

:arrow_upper_right:[캠페인 특정 작업 과정 디자인 및 실행](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html)

:arrow_upper_right:[캠페인 대상자를 선택하는 방법 학습](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html)

:arrow_upper_right:[워크플로우 시작](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
