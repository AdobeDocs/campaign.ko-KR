---
title: Adobe Campaign 보고 도구 시작
description: 캠페인의 성공을 측정하고 사용자 행동을 분석합니다
feature: Reporting
role: Data Engineer
level: Beginner
exl-id: f931fc0d-12c1-4bff-a4f2-153e8d91c339
source-git-commit: 3ca0b96c9235008148067dc9a309f420bd9a92f8
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 12%

---

# 보고 시작{#gs-ac-reports}

Adobe Campaign은 이 페이지에 나와 있는 보고 도구 세트를 제공합니다.

* **동적 보고**

  Campaign 웹 UI에서 사용할 수 있는 동적 보고는 마케팅 활동의 영향을 측정하기 위한 사용자 지정 및 실시간 보고서를 제공합니다. 이 기능은 프로필 데이터에 대한 액세스를 추가하여 열기 및 클릭과 같은 기능적 이메일 캠페인 데이터 외에도 성별, 도시, 연령과 같은 프로필 차원별로 인구통계학적 분석을 지원합니다. [웹 UI v7 설명서](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html?lang=ko){target="_blank"}를 참조하세요.

* **큐브**

  Adobe Campaign에는 동적 보고서를 만들기 위한 직관적인 데이터 탐색 도구가 포함되어 있습니다.

  Marketing Analytics 기능을 사용하여 데이터를 분석 및 측정하고, 통계를 계산하며, 보고서 작성 및 계산을 간소화 및 최적화합니다. 보고서를 만들고 대상 모집단을 빌드하여 Adobe Campaign에서 타깃팅 또는 세분화 작업에 사용할 수 있는 목록에 저장할 수 있습니다.

  ![](assets/create-a-report.png)

  쿼리, 계산 및 볼륨의 복잡성에 따라, 이러한 보고서에서 분석된 데이터는 쿼리를 통해 수집되고 목록(데이터 관리 유형 워크플로우) 또는 큐브(Marketing Analytics 사용)에서 미리 집계될 수 있습니다. 피벗 테이블 또는 그룹 목록 형식으로 표시됩니다.

  이 작업에 대한 자세한 정보는 [이 섹션](gs-cubes.md)을 참조하십시오.

* **기본 제공 보고서**

  Adobe Campaign에는 게재, 캠페인, 플랫폼 활동, 선택적 기능 등에 대한 보고서가 함께 제공됩니다. 이러한 보고서는 관련 다양한 기능을 통해 사용할 수 있습니다. 특정 요구 사항에 맞게 조정할 수 있습니다.

  **보고서** 탭을 사용하여 이러한 보고서에 액세스합니다.

  ![](assets/built-in-reports.png)

  이 작업에 대한 자세한 정보는 [이 섹션](built-in-reports.md)을 참조하십시오.

* **설명 데이터 분석**

  Adobe Campaign은 데이터베이스의 데이터에 대한 통계를 생성하는 시각적 도구를 제공합니다. 전용 도우미를 사용하여 설명 분석 보고서를 만들고 필요에 따라 콘텐츠와 레이아웃을 조정할 수 있습니다.

  **[!UICONTROL Tools > Descriptive analysis...]** 메뉴를 사용하여 새 보고서를 만드십시오.

  ![](assets/desc-analysis-report.png)

  Campaign 설명 분석 보고는 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/analyzing-populations/about-descriptive-analysis.html?lang=ko){target="_blank"}에 나와 있습니다.

* **사용자 지정 보고서**

  Adobe Campaign을 사용하여 데이터베이스의 데이터에 대한 보고서를 만듭니다. 이러한 항목이 생성되면 적절한 컨텍스트에서 액세스할 수 있도록 합니다.

  보고서를 만드는 단계는 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/about-reports-creation-in-campaign.html?lang=ko){target="_blank"}에 자세히 설명되어 있습니다. 개인화된 보고서 생성은 고급 사용자에게 예약되어 있습니다.
