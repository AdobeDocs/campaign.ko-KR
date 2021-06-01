---
product: Adobe Campaign
title: 대상자 시작
description: 대상자 시작
feature: 대상자
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 21%

---

# 대상 시작{#gs-ac-audiences}

## 프로필 작업{#gs-ac-profiles}

프로필은 고객, 구독자 및 잠재 고객을 포함하여 Campaign 데이터베이스에 저장된 연락처입니다. 프로필을 가져오고 이 데이터베이스를 빌드하는 데 사용할 수 있는 메커니즘은 웹 양식을 통한 온라인 수집, 텍스트 파일 수동 또는 자동 가져오기, 회사 데이터베이스 또는 기타 정보 시스템을 사용한 복제와 같이 다양합니다. Adobe Campaign을 사용하면 마케팅 기록, 구매 정보, 환경 설정, CRM 데이터 및 관련 API 데이터를 통합 뷰에 통합하여 분석하고 조치를 취할 수 있습니다. 프로필에는 타겟팅, 자격 부여 및 개인 추적에 필요한 모든 정보가 포함되어 있습니다.

프로필은 이름, 성, 이메일 주소, 쿠키 ID, 고객 ID, 모바일 식별자 또는 특정 채널과 관련된 기타 정보 등 모든 프로필 속성을 저장하는 **nmsRecipient** 테이블의 레코드입니다. 수신자 테이블에 연결된 다른 표에는 프로필 관련 데이터가 포함되어 있습니다. 예를 들어 수신자에게 전송된 모든 게재의 레코드를 포함하는 게재 로그 테이블입니다. [이 섹션](../dev/datamodel.md#ootb-profiles)에서 내장 프로필 및 수신자 표에 대해 자세히 알아보십시오.

Adobe Campaign에서 **수신자**&#x200B;는 게재(전자 메일, SMS 등)를 보낼 타겟팅된 기본 프로필입니다. 데이터베이스에 저장된 수신자 데이터를 사용하면 주어진 게재를 받을 대상을 필터링하고 게재 콘텐츠에 개인화 데이터를 추가할 수 있습니다. 데이터베이스에 다른 유형의 프로필이 있습니다. 다양한 용도로 디자인되어 있습니다. 예를 들어 최종 대상으로 전송되기 전에 시드 프로필을 테스트하여 게재를 테스트합니다.

프로필을 목록으로 그룹화하거나 데이터베이스를 쿼리하여 수집할 수 있습니다.


프로필 데이터로 Campaign을 채우려면 다음을 수행할 수 있습니다.

* [crm ](import.md) 시스템과 같은 외부 데이터 소스에서 데이터 파일 가져오기
* [고객이 자신의 ](../dev/webapps.md) 정보를 입력하고 자체 프로필을 만들 수 있도록 웹 양식 만들기
* [프로필을 ](../connect/fda.md) 저장하는 외부 데이터베이스에 매핑
* 다음과 같이 클라이언트 콘솔을 사용하여 수동으로 프로필을 입력합니다.

![](assets/create-profile.png)


[!DNL :arrow_upper_right:]  [Adobe Campaign Classic v7 설명서에서 프로필을 관리하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html).


## 개인 정보 보호 및 동의

Adobe Campaign은 개인 정보와 중요한 데이터를 포함한 많은 양의 데이터를 수집하고 처리할 수 있는 강력한 데이터 도구입니다. Adobe Campaign을 사용하면 개인 및 중요한 정보를 포함한 데이터를 수집할 수 있습니다. 따라서 수신자로부터 동의를 받고 모니터링하는 것이 중요합니다.

[!DNL :arrow_upper_right:]  [Adobe Campaign Classic v7 설명서에서 개인 정보 및 동의를 관리하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html).

## 목록 만들기

목록은 게재 작업에서 타겟팅되거나 가져오기 작업 또는 워크플로우 실행 중에 업데이트될 수 있는 정적 프로필 세트입니다. 예를 들어 쿼리를 통해 데이터베이스에서 추출한 모집단은 목록을 제공할 수 있습니다.

[!DNL :arrow_upper_right:]  [Adobe Campaign Classic v7 설명서에서 목록을 만들고 관리하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html).

## 데이터베이스를 쿼리합니다.

워크플로우에서 **쿼리** 활동을 사용하여 데이터베이스를 쿼리하고, 세그먼트 데이터를 쿼리하고, 복잡한 대상을 빌드하십시오.

[!DNL :arrow_upper_right:]  [Adobe Campaign Classic v7 설명서에서 Campaign 쿼리에 대해 자세히 알아보십시오](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html).

[!DNL :arrow_upper_right:] 모든 타깃팅 활동은  [Adobe Campaign Classic v7 설명서에 나열됩니다](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html)

## 워크플로우에서 대상자 만들기

워크플로우의 그래픽 시퀀스에서 쿼리 조합을 통해 타겟팅을 만들 수 있습니다. 요구 사항에 따라 타겟팅할 대상을 만들 수 있습니다. 워크플로우 편집기를 표시하려면 캠페인 대시보드에서 **[!UICONTROL Targeting and workflows]** 탭을 클릭합니다.

[!DNL :arrow_upper_right:]  [Adobe Campaign Classic v7 설명서에서 캠페인 워크플로우에서 대상을 만드는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)


## 활성 프로필{#active-profiles}

계약에 따라 각 캠페인 인스턴스에는 청구 용도로 계산되는 특정 양의 활성 프로필이 제공됩니다. 구입한 활성 프로필 수에 대한 자세한 내용은 최신 계약서를 참조하십시오.

**** 정보 레코드(예:최종 고객,  [잠재 고객 ](../dev/datamodel.md) 또는 리드를 나타내는 쿠키 ID, 고객 ID, 모바일 식별자 또는 특정 채널과 관련된 기타 정보가 포함된 외부 테이블 또는 수신자 테이블의 레코드. 지난 12개월 이내에 모든 채널을 통해 프로필을 타겟팅하거나 통신한 경우 프로필이 활성 상태로 간주됩니다.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

[!DNL :arrow_upper_right:] For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

**관련 항목**

[!DNL :arrow_upper_right:] [캠페인별 워크플로우 디자인 및 실행](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html)

[!DNL :arrow_upper_right:] [캠페인 대상자를 선택하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html)

[!DNL :arrow_upper_right:] [워크플로우 시작](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
