---
product: campaign
title: 가설 만들기
description: Campaign Response Manager에서 가설을 만드는 방법을 알아봅니다
feature: Campaigns
version: Campaign v8, Campaign Classic v7
audience: campaign
content-type: reference
topic-tags: response-manager
exl-id: e0b3bc9f-5e81-463f-a59e-cd972a47109b
TQID: 'https://experienceleague.adobe.com/FggklU5pqlhjpHlUpd6C2G3Cb0A0dsooRZo9iEya858'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: d72afaa0-c842-48c8-9a3c-51b7911edc1b
    internal-label: Response Management
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8839c1717cb026a38987a745ffc080a79f344bce
workflow-type: tm+mt
source-wordcount: '1375'
ht-degree: 2%
---
# 가설 만들기{#creating-hypotheses}



가설을 생성/캠페인 오퍼 또는 게재에 연결하는 다양한 가능성이 있습니다.

* **[!UICONTROL Measurement hypotheses]** 폴더를 통해 기존 템플릿을 기반으로 새 가설을 만들어 기존 게재에 연결합니다.
* 캠페인의 **[!UICONTROL Edit]** > **[!UICONTROL Measurement]** 탭을 통해.
* 캠페인에서 만든 게재의 **[!UICONTROL Measurement]** 옵션을 통해.

가설은 마케팅 캠페인이 시작되고 수신자가 게재를 받은 후에만 계산할 수 있습니다. 가설이 오퍼 제안에 근거한다면, 후자는 적어도 제시될 필요가 있고 여전히 적극적일 필요가 있다. 오퍼 및 게재 가설은 **[!UICONTROL Measurement hypotheses]** 폴더를 통해 만들어지며 가설 템플릿을 기반으로 합니다. 그러나 캠페인이 시작되기 전에 게재 또는 캠페인에서 직접 가설을 참조할 수 있습니다. 이 경우, 가설은 마케팅 캠페인이 시작되면 실행 설정을 기반으로 자동으로 계산됩니다. [자세히 알아보기](hypothesis-templates.md#hypothesis-template-execution-settings)

## 게재 시 즉석으로 가설 만들기 {#creating-a-hypothesis-on-the-fly-on-a-delivery}

기존 게재에 대한 가설을 생성하려면 다음 프로세스를 적용합니다.

>[!NOTE]
>
>이 작업은 보류 중인 게재에만 가능합니다.

1. Adobe Campaign 트리에서 **[!UICONTROL Campaign management > Measurement hypotheses]**(으)로 이동합니다.
1. **[!UICONTROL New]** 단추를 클릭하거나 가설 목록을 마우스 오른쪽 단추로 클릭하고 드롭다운 목록에서 **[!UICONTROL New]**&#x200B;을(를) 선택합니다.

   ![템플릿 선택을 위한 [새로 만들기] 단추 및 [새 가설] 대화 상자가 있는 측정 가설 목록](assets/response_hypothesis_instance_creation_002.png)

1. 가설 창에서 이전에 만든 템플릿을 선택합니다. [자세히 알아보기](hypothesis-templates.md)

   ![사용 가능한 템플릿을 나열하는 가설 템플릿 드롭다운이 있는 새 가설 대화 상자](assets/response_hypothesis_instance_creation_003.png)

   선택한 모형에서 정의된 가설 문맥이 창에 표시된다.

   >[!NOTE]
   >
   >템플릿에 정의되어 있으며 이 단계에서 표시되지 않는 설정도 메모리에 유지되며 진행 중인 가설에 재할당됩니다.

   ![선택한 템플릿과 게재 필드에서 상속된 쿼리를 표시하는 새 가설 대화 상자](assets/response_hypothesis_instance_creation_004.png)

1. 가설을 생성할 게재를 선택합니다.

   ![선택할 게재를 나열하는 게재 드롭다운이 있는 새 가설 대화 상자](assets/response_hypothesis_instance_creation_005.png)

1. **[!UICONTROL General]**, **[!UICONTROL Transactions]** 및 **[!UICONTROL Scope]** 탭을 편집하여 가설을 개인화할 수 있습니다. [자세히 알아보기](hypothesis-templates.md#creating-a-hypothesis-model)
1. **[!UICONTROL Start]**&#x200B;을(를) 클릭하여 가설을 시작합니다.

   측정을 수행하기 위한 워크플로는 자동으로 만들어집니다. 가설 구성에 따라 이름이 자동으로 정의됩니다.

   >[!CAUTION]
   >
   >**[!UICONTROL Keep execution workflow]** 상자를 선택한 경우 이에 액세스할 수 있습니다.\
   >이 옵션은 가설을 실행하는 동안 오류가 발생한 경우에만 디버깅을 위해 활성화해야 합니다. 자동으로 생성된 워크플로는 Adobe Campaign 탐색기의 **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Objects created automatically]** > **[!UICONTROL Campaign workflows]** 폴더에 저장됩니다.
   > 
   >또한 자동으로 생성된 워크플로는 수정해서는 안 됩니다. 최종 수정 사항은 나중에 계산할 때 다른 곳에 고려되지 않습니다.
   >
   >이 옵션을 선택한 경우 워크플로우를 실행한 후 삭제합니다.

   ![가설을 시작하기 위한 측정 가설 목록과 확인 프롬프트의 시작 단추](assets/response_hypothesis_instance_creation_006.png)

   계산이 완료되면 측정 지표가 자동으로 업데이트됩니다.

   ![응답률 및 반응과 같이 가설로 계산된 지표가 있는 가설 일반 탭](assets/response_hypothesis_instance_creation_007.png)

1. 필요한 경우 설정을 변경하고 가설을 다시 시작합니다.

## 캠페인 게재에서 가설 참조 {#referencing-a-hypothesis-in-a-campaign-delivery}

시작하기 전에 마케팅 캠페인에서 가설을 참조할 수 있습니다. 이 경우, 게재가 전송되면 가설 템플릿에 정의된 실행 설정을 기반으로 가설이 자동으로 실행됩니다. 게재에서 가설을 생성하려면 다음 프로세스를 적용합니다.

1. 필요에 따라 [가설 모델 만들기](hypothesis-templates.md#creating-a-hypothesis-model)에 설명된 대로 **[!UICONTROL Delivery]** 형식 템플릿을 하나 이상 만들 수 있습니다.
1. 마케팅 캠페인 및 타기팅 워크플로우를 만듭니다.
1. 게재 창에서 **[!UICONTROL Delivery measurement]** 아이콘을 클릭합니다.
1. 가설 템플릿을 선택합니다(모델에 구성된 쿼리가 가설 창에 표시됨).

   가설은 캠페인이 완료되면 모델에 구성된 날짜를 기반으로 자동으로 계산됩니다. [자세히 알아보기](hypothesis-templates.md#hypothesis-template-execution-settings)

   ![게재에서 가설 템플릿을 참조하기 위한 추가 단추가 있는 게재 측정 창](assets/response_hypothesis_instance_creation_008.png)

## 캠페인 게재에 기본 가설 추가 {#adding-a-default-hypothesis-to-deliveries-for-a-campaign}

캠페인 수준에서 가설을 직접 참조할 수 있습니다. 이 경우 가설은 캠페인에서 생성된 모든 게재에 자동으로 연결됩니다. 방법은 다음과 같습니다.

1. 캠페인의 **[!UICONTROL Edit]** 탭으로 이동합니다.
1. 측정 섹션에서 **[!UICONTROL Default hypotheses]** 탭을 클릭합니다.

   ![기본 가설 탭이 강조 표시된 캠페인 편집 탭, 측정 섹션](assets/response_hypothesis_instance_creation_010.png)

1. **[!UICONTROL Add]**&#x200B;을(를) 클릭하고 가설 템플릿을 선택합니다.

   ![캠페인의 기본 가설 탭에서 템플릿 드롭다운으로 가설 대화 상자를 추가합니다](assets/response_hypothesis_instance_creation_011.png)

   이제 이 템플릿을 기반으로 하는 가설이 캠페인의 각 새 게재에서 기본적으로 참조됩니다.

   ![구매에 대한 가설을 나열하는 타기팅 워크플로우의 게재 측정 기간](assets/response_hypothesis_instance_creation_012.png)

가설의 **[!UICONTROL General]** 및 **[!UICONTROL Reactions]** 탭에서 가설 결과를 볼 수 있습니다. [자세히 알아보기](hypothesis-tracking.md)

자세한 정보는 [이 샘플](#example--creating-a-hypothesis-linked-to-a-delivery)을 참조하십시오.

## 오퍼에 대한 가설 만들기 {#creating-a-hypothesis-on-an-offer}

오퍼 제안에 대한 가설을 생성하는 것은 즉석 전달 가설을 생성하는 것과 유사하다. 오퍼가 활성화된 경우 가설을 실행할 수 있습니다. 계산 기간은 오퍼 제안 일자를 기반으로 합니다. 가설을 통해 수신자를 구매에 연결할 수 있는 경우 수락될 가능성이 있는 오퍼 제안의 상태는 자동으로 변경될 수 있습니다. [자세히 알아보기](hypothesis-templates.md#transactions)

1. [가설 모델 만들기](hypothesis-templates.md#creating-a-hypothesis-model)에 설명된 대로 **[!UICONTROL Offer]** 형식 모델을 하나 이상 만듭니다.
1. **[!UICONTROL Campaign management > Measurement hypotheses]** 노드로 이동합니다.
1. 이전에 만든 모델을 선택하여 **[!UICONTROL Offers]** 형식 가설을 만듭니다.

   ![새 오퍼 가설과 같은 오퍼 템플릿을 나열하는 템플릿 드롭다운이 있는 새 가설 대화 상자](assets/response_hypothesis_instance_offer_001.png)

   모델에서 생성된 질의가 창에 나타납니다.

   ![오퍼 가설 템플릿과 쿼리 형식이 Item과 같은 새 가설 대화 상자](assets/response_hypothesis_instance_offer_003.png)

1. 가설을 생성할 오퍼를 선택합니다.

   ![파리 여행과 같은 오퍼 드롭다운 목록이 있는 새 가설 대화 상자](assets/response_hypothesis_instance_offer_004.png)

1. 필요한 경우 쿼리를 세분화합니다.
1. 가설을 실행하려면 **[!UICONTROL Start]**&#x200B;을(를) 클릭합니다.
1. 가설 결과는 **[!UICONTROL General]** 및 **[!UICONTROL Reactions]** 탭에서 볼 수 있습니다. [자세히 알아보기](hypothesis-tracking.md)

   오퍼에 대한 가설은 **[!UICONTROL Measurement]** 탭에서 참조됩니다.

   ![유효 ROI 계산 중인 오퍼에 연결된 가설 목록이 있는 오퍼 측정값 탭](assets/response_hypothesis_instance_offer_007.png)

   가설 템플릿에서 **[!UICONTROL Update offer proposition status]** 옵션이 활성화된 경우 오퍼 제안 상태가 자동으로 변경되므로 캠페인의 영향에 대한 피드백을 제공합니다(자세한 내용은 [트랜잭션](hypothesis-templates.md#transactions) 참조).

## 예: 게재에 연결된 가설 만들기 {#example--creating-a-hypothesis-linked-to-a-delivery}

이 예제에서는 게재에 연결된 가설을 만들려고 합니다. 이 가설은 이전에 만들어진 모형을 기반으로 할 것이다. [자세히 알아보기](hypothesis-templates.md#example--creating-a-hypothesis-template-on-a-delivery)

그런 다음 모델에서 상속된 쿼리를 세분화하여 구매 테이블의 특정 기사에 대해 가설을 세웁니다.

1. 캠페인 및 게재를 만듭니다. [Campaign v8 설명서](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=ko){target=_blank}를 참조하세요.

   이 예제에서는 DM 유형 게재를 사용합니다.

1. 시드 주소 구성: 이전에 만든 가설 템플릿이 반응 결과에서 컨트롤 그룹을 고려하도록 구성되었습니다.

   ![컨트롤 그룹 구성이 활성화된 상태에서 Campaign 고급 설정, 컨트롤 채우기 탭](assets/response_hypothesis_delivery_example_007.png)

   >[!NOTE]
   >
   >자세한 내용은 관련 [Campaign v8 설명서](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=ko#add-a-control-group){target="_blank"}를 참조하십시오.

1. **[!UICONTROL Direct mail delivery]**&#x200B;을(를) 열고 **[!UICONTROL Delivery measurement]** 아이콘을 클릭한 다음 **[!UICONTROL Add]**&#x200B;을(를) 클릭합니다.

   ![가정에 대한 추가 단추가 있는 DM 게재의 게재 측정 창](assets/response_hypothesis_delivery_example_002.png)

1. 드롭다운 목록에서 이전에 만든 가설 템플릿을 선택합니다.

   ![구매 시 가설(HYP4)을 나열하는 템플릿 드롭다운이 있는 가설 대화 상자를 추가합니다](assets/response_hypothesis_delivery_example_004.png)

   모델에서 생성된 쿼리가 표시됩니다.

   ![티켓 라인별 가설 템플릿과 제품별 쿼리 필터를 사용한 새 가설 대화 상자](assets/response_hypothesis_delivery_example_005.png)

1. **[!UICONTROL Edit query...]**&#x200B;을(를) 클릭하고 가설이 관련된 제품을 입력하여 쿼리를 세분화합니다.

   ![의복과 같은 제품 이름에 대한 가설을 필터링하는 쿼리 창 편집](assets/response_hypothesis_delivery_example_006.png)

   캠페인의 **[!UICONTROL Edit]** > **[!UICONTROL Measurement]** 탭에서 가설이 게재에 연결되어 있는지 확인할 수 있습니다.

   ![캠페인 측정 섹션, 측정 가설 탭, 게재 구매 가설 나열](assets/response_hypothesis_delivery_example_008.png)

1. 타겟팅 워크플로우를 시작하고 캠페인이 완료될 때까지 필요한 검사를 실행합니다. [Campaign v8 설명서](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=ko#start-a-delivery){target=_blank}를 참조하세요.

   DM 게재가 진행 중이며 상태, 대상 모집단 및 증명이 포함된 ![Campaign 대시보드](assets/response_hypothesis_delivery_example_009.png)

1. Adobe Campaign 트리에서 **[!UICONTROL Campaign management > Measurement hypotheses]** 노드로 이동하여 가설로 계산된 지표를 확인합니다.

   ![연락한 응답률과 같이 계산된 지표가 있는 측정 가설 목록 및 일반 탭](assets/response_hypothesis_delivery_example_010.png)
