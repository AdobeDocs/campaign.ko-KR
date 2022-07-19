---
product: campaign
title: 마케팅 캠페인 게재
description: 마케팅 캠페인 게재에 대해 자세히 알아보기
feature: Campaigns, Resource Management, Cross Channel Orchestration
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 1%

---

# 마케팅 캠페인 게재 {#marketing-campaign-deliveries}

캠페인에서 크로스 채널 게재 오케스트레이션: 개인화된 이메일, SMS, 푸시 알림 및 인앱 메시지를 통해 Adobe Campaign와의 커뮤니케이션을 간소화합니다. 비디오, 이모지 또는 GIF과 같은 리치 미디어를 사용하여 직접 통합할 수 있습니다.

캠페인 대시보드, 캠페인 워크플로우를 통해 또는 게재 개요를 통해 직접 게재를 만들 수 있습니다. 캠페인에서 만든 게재는 이 캠페인에 연결되고 캠페인 수준에서 통합됩니다.

## 게재 만들기 {#create-deliveries}

마케팅 캠페인에 게재를 추가하는 방법은 두 가지가 있습니다.

* 에서 **[!UICONTROL Add a delivery]** campaign 대시보드에 연결합니다.

![](assets/campaign_op_add_delivery.png)

게재가 저장되면 캠페인 대시보드에 추가됩니다.

* 캠페인 워크플로우에서 **[!UICONTROL Targeting and workflows]** 탭합니다.

   ![](assets/campaign-wf-delivery.png)

   워크플로우가 시작되면 게재가 캠페인 대시보드에 추가됩니다.

게재 승인 흐름을 설정하고 실행하는 방법을 알아봅니다 [이 페이지에서](marketing-campaign-approval.md).

## 게재 시작 {#start-a-delivery}

모든 승인이 부여되면 게재를 보낼 수 있습니다. 게재 실행 프로세스는 채널에 따라 다릅니다.

* 이메일 또는 모바일 채널 게재에 대해서는 다음을 참조하십시오. [이 섹션](#start-an-online-delivery)

* DM 게재의 경우 다음을 참조하십시오 [이 섹션](#start-an-offline-delivery)

### 이메일 또는 모바일 게재 시작 {#start-an-online-delivery}

모든 승인 요청이 부여되면 게재 상태는 **[!UICONTROL Pending confirmation]** 을 시작할 수 있습니다. 게재를 시작할 수 있는 검토자는 게재를 시작할 준비가 되었다는 알림을 받습니다.

![](assets/confirm-delivery.png)

정보가 캠페인 대시보드에 나타납니다. 다음 **[!UICONTROL Confirm delivery]** 링크를 통해 게재를 시작할 수 있습니다.

![](assets/confirm-delivery-from-dashboard.png)

게재 확인은 관리자, 게재 또는 캠페인 속성에서 명시적으로 언급한 연산자 또는 연산자 그룹으로 제한됩니다. 연산자가 디자인되지 않은 경우 관리자 및 캠페인 소유자가 승인할 수 있습니다.

![](assets/select-delivery-reviewers.png)

그러나 게재 또는 캠페인 속성에서 특정 검토자가 정의된 경우에도 캠페인 소유자가 전송을 확인하도록 허용할 수도 있습니다. 이렇게 하려면 관리자는 **NmsCampaign_Activate_OwnerConfirmation** 옵션을 설정하고 **1**. 옵션은 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]** 노드 아래에 있어야 합니다.


### DM 게재 시작 {#start-an-offline-delivery}

모든 승인이 부여되면 게재 상태가 **[!UICONTROL Pending extraction]**. 추출 파일은 전용 [기술 워크플로우](../workflow/technical-workflows.md) 기본 구성에서 dm 게재가 추출 보류 중일 때 자동으로 시작됩니다. 프로세스가 진행 중이면 대시보드에 표시되고 링크를 통해 편집할 수 있습니다.

추출 워크플로우가 성공적으로 실행되면 추출 파일을 승인해야 합니다(게재 설정에서 추출 파일 승인을 선택한 경우). [자세히 알아보기](marketing-campaign-approval.md#approving-an-extraction-file)

컨텐츠의 유효성을 확인하고 파일을 공급자에게 보내려면 아래 절차를 따르십시오.

1. 추출 파일이 승인되면 라우터 알림 전자 메일의 증명을 생성할 수 있습니다. 이 이메일 메시지는 게재 템플릿을 기반으로 만들어집니다. 승인을 받아야 합니다.

   이 단계는 **[!UICONTROL Enable the sending and validation of proofs (Direct mail)]** 옵션이에서 활성화됨 **[!UICONTROL Approvals]** 고급 캠페인 매개 변수의 탭입니다.

   ![](assets/enable-proof-validation.png)

1. 을(를) 클릭합니다. **[!UICONTROL Send a proof]** 버튼을 클릭하여 증명을 만듭니다.

   증명 타겟을 미리 정의해야 합니다.

   필요한 만큼 증명을 만들 수 있습니다. 액세스 권한은 **[!UICONTROL Direct mail...]** 게재 세부 사항의 링크입니다.

1. 게재 상태가 **[!UICONTROL To submit]**. 을(를) 클릭합니다. **[!UICONTROL Submit proofs]** 버튼을 클릭하여 승인 프로세스를 시작합니다.

1. 게재 상태가 **[!UICONTROL Proof to validate]** 및 버튼을 사용하면 승인을 수락하거나 거부할 수 있습니다.

   이 승인을 수락하거나 거부하거나 추출 단계로 돌아갈 수 있습니다.

1. 증명을 승인하면 추출 파일이 라우터로 전송되고 게재가 완료됩니다.

### 예산 및 비용 계산 {#compute-costs-and-stocks}

파일 추출은 다음 두 가지 프로세스를 시작합니다. 예산 계산 및 주식 계산. 예산 항목이 갱신됩니다.

* 다음 **[!UICONTROL Budget]** 탭에서는 캠페인에 대한 예산을 관리할 수 있습니다. 원가 항목의 합계는 **[!UICONTROL Calculated cost]** 캠페인의 기본 탭 및 캠페인에 속하는 프로그램의 필드입니다. 그 액수도 캠페인 예산에 반영된다.

   ![](assets/campaign-budget-tab.png)

   결국 실제 비용은 라우터에서 제공한 정보를 통해 계산됩니다. 실제로 전송된 메시지만 송장 발행됩니다.

* 주식은 **[!UICONTROL Administration > Campaign management > Stocks]** 노드 아래에 있어야 합니다.

   ![](assets/campaign-stocks.png)

   의 비용 구조 **[!UICONTROL Administration > Campaign management > Service providers]** 노드 아래에 있어야 합니다.

   ![](assets/campaign-service-providers.png)

   재고 라인은 재고 섹션에 표시됩니다. 초기 재고를 정의하려면 스톡 라인을 엽니다. 주식은 배달이 일어날 때마다 감소한다. 경고 수준 및 알림을 정의할 수 있습니다.


   >[!NOTE]
   >
   >예산에 대해 자세히 알아보기 [이 섹션](providers--stocks-and-budgets.md).
