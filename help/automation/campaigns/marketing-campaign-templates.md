---
product: campaign
title: 마케팅 캠페인 템플릿
description: 마케팅 캠페인 템플릿
feature: Campaigns, Templates
exl-id: 1bd8d3e7-aaa9-4e00-96bb-0d30614ab380
source-git-commit: 1c879c7803c346d4b602089a22c2639eb83e82be
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 5%

---

# Campaign 템플릿 만들기 및 구성 {#campaign-templates}

모든 마케팅 캠페인은 주요 특성과 기능을 저장하는 템플릿을 기반으로 합니다. Campaign에는 캠페인을 만들기 위한 기본 제공 템플릿이 포함되어 있습니다. 이 템플릿에는 문서, 시드 주소, 승인, 게재 개요 등 모든 기능이 활성화되어 있습니다.

사용 가능한 기능은 사용 권한, 추가 기능 및 Adobe Campaign 플랫폼의 구성에 따라 다릅니다.


>[!NOTE]
>
>트리를 클릭하면 트리가 표시됩니다. **[!UICONTROL Explorer]** 홈 페이지의 아이콘입니다.

특정 구성이 정의되지 않은 캠페인을 만들기 위해 내장 템플릿이 제공됩니다. 캠페인 템플릿을 만들고 구성한 다음 그 템플릿에서 캠페인을 만들 수 있습니다.

## 캠페인 템플릿 만들기 {#create-a-campaign-template}

캠페인 템플릿을 만들려면 아래 단계를 수행하십시오.

1. 캠페인 열기 **탐색기**&#x200B;을 클릭하고 다음으로 이동 **리소스 > 템플릿 > Campaign 템플릿**.
1. 클릭 **신규** 템플릿 목록 위의 도구 모음에서 를 클릭합니다.

![](assets/campaign-template-node.png)

다음을 수행할 수도 있습니다. **복제** 기본 제공 템플릿을 사용하여 해당 구성을 다시 사용하고 조정할 수 있습니다. 이렇게 하려면 템플릿을 마우스 오른쪽 버튼으로 클릭하고 를 선택합니다. **복제**.

1. 새 캠페인 템플릿의 레이블을 입력합니다.
1. 클릭 **저장** 템플릿을 다시 여십시오.
1. 다음에서 **편집** 탭에서 템플릿 속성을 정의합니다.
1. 선택 **고급 캠페인 매개 변수...** 캠페인 템플릿에 워크플로우를 추가하는 링크입니다.

   ![](assets/campaign-template-parameters.png)

1. 변경 **타겟팅 및 워크플로우** 값: 까지 **예**&#x200B;을 누르고 확인합니다. 에서 기능을 추가하는 방법 알아보기 [이 섹션](#typology-of-enabled-modules).
1. 다음 **타겟팅 및 워크플로우** 탭이 템플릿에 추가됩니다. 클릭 **워크플로우 추가...**, 를 입력합니다. **레이블** 및 클릭 **확인**.
1. 필요에 따라 워크플로우를 만듭니다.

   ![](assets/campaign-template-create-wf.png)

1. **저장**&#x200B;을 클릭합니다. 이제 템플릿을 사용하여 새 캠페인을 만들 준비가 되었습니다.

캠페인 템플릿의 다양한 탭과 하위 탭을 사용하면에 설명된 설정에 액세스할 수 있습니다. [일반 구성](#general-configuration).

## 모듈 선택 {#select-modules}

다음 **[!UICONTROL Advanced campaign parameters...]** 링크를 사용하면 이 템플릿을 기반으로 캠페인에 대한 작업을 활성화 및 비활성화할 수 있습니다. 이 템플릿을 기반으로 만든 캠페인에서 활성화할 기능을 선택합니다.

![](assets/campaign-template-select-modules.png)

기능을 선택하지 않으면 프로세스와 관련된 요소(메뉴, 아이콘, 옵션, 탭, 하위 탭 등)가 템플릿의 인터페이스 또는 이 템플릿을 기반으로 하는 캠페인에 나타나지 마십시오. 캠페인 세부 정보의 왼쪽에 있는 탭과 사용 가능한 탭은 템플릿에서 선택한 기능과 일치합니다. 예를 들어 **경비 및 목표** 기능이 활성화되지 않았으므로 해당 **[!UICONTROL Budget]** 이 템플릿을 기반으로 하는 캠페인에는 탭이 표시되지 않습니다.

또한 구성 창에 대한 단축키가 캠페인 대시보드에 추가됩니다. 기능을 활성화하면 직접 링크를 통해 캠페인 대시보드에서 액세스할 수 있습니다.

### 구성 샘플

* 예를 들어 다음 설정을 사용합니다.

   ![](assets/campaign-template-select-functionalities.png)

   캠페인 대시보드에는 다음이 표시됩니다.

   ![](assets/campaign-template-dashboard-sample-1.png)

   다음 사항에 주의하십시오. **[!UICONTROL Targeting and workflows]** 탭이 누락되었습니다.

   다음 기능을 사용할 수 있습니다.

   ![](assets/campaign-template-edit-sample-1.png)

   다음 사항에 주의하십시오. **[!UICONTROL Budget]** 탭이 누락되었습니다.

   캠페인 고급 설정도 이 구성을 반영합니다.

   ![](assets/campaign-template-parameters-sample-1.png)

   다음 사항에 주의하십시오. **[!UICONTROL Approvals]** 탭을 사용할 수 없습니다.

* 이 구성:
   ![](assets/campaign-template-dashboard-sample-2.png)

   캠페인 대시보드에는 다음이 표시됩니다.

   ![](assets/campaign-template-select-functionalities-2.png)

   다음 사항에 주의하십시오. **[!UICONTROL Targeting and workflows]** 탭은 사용할 수 있지만 **문서 추가** 링크가 누락되었습니다.

   다음 기능을 사용할 수 있습니다.

   ![](assets/campaign-template-edit-sample-2.png)

   다음 사항에 주의하십시오. **[!UICONTROL Budget]** 탭을 사용할 수 있습니다.

   캠페인 고급 설정도 이 구성을 반영합니다.

   ![](assets/campaign-template-parameters-sample-2.png)

   다음 사항에 주의하십시오. **[!UICONTROL Approvals]** 탭은 사용할 수 있지만 **[!UICONTROL Control population]** 및 **[!UICONTROL Seed addresses]** 탭이 활성화되어 있지 않습니다.


## 모듈 유형화 {#typology-of-enabled-modules}

* **컨트롤 그룹**

   이 모듈을 선택하면 템플릿 및 이 템플릿을 기반으로 하는 캠페인의 고급 설정에 추가 탭이 추가됩니다. 템플릿을 통해 또는 각 캠페인에 대해 개별적으로 구성을 정의할 수 있습니다. 에서 컨트롤 그룹에 대해 자세히 알아보기 [이 섹션](marketing-campaign-deliveries.md#defining-a-control-group).

   ![](assets/template-activate-1.png)


* **시드 주소**

   이 모듈을 선택하면 템플릿 및 이 템플릿을 기반으로 하는 캠페인의 고급 설정에 추가 탭이 추가됩니다. 템플릿을 통해 또는 각 캠페인에 대해 개별적으로 구성을 정의할 수 있습니다.

   ![](assets/template-activate-2.png)

* **문서**

   이 모듈을 선택하면 추가 탭이 **[!UICONTROL Edit]** 템플릿 및 이 템플릿을 기반으로 하는 캠페인의 탭입니다. 첨부된 문서는 템플릿에서 또는 각 캠페인에 대해 개별적으로 추가할 수 있습니다. 의 문서에 대해 자세히 알아보기 [이 섹션](marketing-campaign-deliveries.md#manage-associated-documents).

   ![](assets/template-activate-3.png)

* **게재 개요**

   이 모듈을 선택하면 **[!UICONTROL Delivery outlines]** 하위 탭이 **[!UICONTROL Documents]** 탭으로 이동하여 캠페인에 대한 게재 개요를 정의합니다. 에서 게재 개요에 대해 자세히 알아보기 [이 섹션](marketing-campaign-assets.md#delivery-outlines).

   ![](assets/template-activate-4.png)

* **타겟팅 및 워크플로**

   다음을 선택하면 **[!UICONTROL Targeting and workflows]** 모듈에서는 이 템플릿을 기반으로 캠페인용 워크플로우를 하나 이상 만들 수 있는 탭이 추가됩니다. 이 템플릿을 기반으로 각 캠페인에 대해 개별적으로 워크플로우를 구성할 수도 있습니다.에서 캠페인 워크플로우에 대해 자세히 알아보세요. [이 섹션](marketing-campaign-deliveries.md#build-the-main-target-in-a-workflow).

   ![](assets/template-activate-5.png)

   이 모듈이 활성화되면 **[!UICONTROL Jobs]** campaign의 고급 설정에 탭이 추가되어 프로세스 실행 시퀀스를 정의합니다.

* **승인**

   을(를) 활성화하면 **[!UICONTROL Approvals]**&#x200B;를 통해 승인할 프로세스 및 승인 담당 연산자를 선택할 수 있습니다. 에서 승인에 대해 자세히 알아보기 [이 섹션](marketing-campaign-approval.md#select-reviewers).

   ![](assets/template-activate-6.png)

   다음을 통해 프로세스 승인을 사용할지 여부를 선택할 수 있습니다. **[!UICONTROL Approvals]** 템플릿 고급 설정 섹션의 탭입니다.

* **경비 및 목표**

   이 모듈을 선택하면 **[!UICONTROL Budget]** 관련 예산을 선택할 수 있도록 이 템플릿을 기반으로 하는 캠페인 및 템플릿의 세부 정보에 탭이 추가됩니다.

   ![](assets/template-activate-7.png)


## 템플릿 속성 {#template-properties}

![](assets/template-op-type.png)

캠페인 템플릿을 만들 때 다음 정보를 입력해야 합니다.

* 다음을 입력합니다. **레이블** 템플릿 중: 레이블은 필수이며, 이 템플릿을 기반으로 하는 모든 캠페인에 대한 기본 레이블입니다.
* 캠페인 선택 **특성** 을 클릭합니다. 이 목록에서 사용할 수 있는 값은 **[!UICONTROL natureOp]** 열거형입니다.

에서 열거형에 액세스하고 구성하는 방법에 대해 알아봅니다. [이 페이지](../../v8/config/ui-settings.md#enumerations).


* 다음 항목 선택 **캠페인 유형**: 고유, 반복 또는 주기적입니다. 기본적으로 캠페인 템플릿은 고유한 캠페인에 적용됩니다. 반복 및 정기 캠페인에 대해서는 다음에서 자세히 설명합니다. [이 섹션](recurring-periodic-campaigns.md).
* 캠페인 기간, 즉 캠페인이 진행될 일 수를 지정합니다. 이 템플릿을 기반으로 캠페인을 만들 때 캠페인 시작 및 종료 날짜가 자동으로 채워집니다.

   캠페인이 반복되면 템플릿에서 직접 캠페인 시작 및 종료 날짜를 지정해야 합니다.

* 다음을 지정합니다. **관련 프로그램** 템플릿 중: 이 템플릿을 기반으로 하는 캠페인이 선택한 프로그램에 연결됩니다.

<!--
## Track campaign execution{#campaign-reverse-scheduling}

You can create a schedule for a campaign and track accomplishments, for instance to prepare an event schedule for a specific date. Campaign templates now let you calculate the start date of a task based on the end date of a campaign.


In the task configuration box, go to the **[!UICONTROL Implementation schedule]** area and check the **[!UICONTROL The start date is calculated based on the campaign end date]** box. (Here, "start date" is the task start date). Go to the **[!UICONTROL Start]** field and enter an interval: the task will start this long before the campaign end date. If you enter a period which is longer than the campaign is set to last, the task will begin before the campaign.

![](assets/mrm_task_in_template_start_date.png)

When you create a campaign using this template, the task start date will be calculated automatically. However, you can always change it later.-->
