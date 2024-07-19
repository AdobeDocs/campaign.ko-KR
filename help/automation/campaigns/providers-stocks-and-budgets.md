---
product: campaign
title: 공급자, 재고 및 예산
description: 공급자, 재고 및 예산
feature: Budget Management, Campaigns
role: User
exl-id: 1d4a98e6-af11-4645-864e-29aa5766d9d8
source-git-commit: 7f6c394f56d517c0a675e0fd2341bb6ef98044f0
workflow-type: tm+mt
source-wordcount: '1830'
ht-degree: 1%

---

# 공급자, 재고 및 예산{#providers-stocks-and-budgets}

Adobe Campaign을 사용하면 캠페인 내에서 수행되는 작업에 참여할 서비스 공급자를 정의할 수 있습니다. 서비스 제공자 및 관련 비용 구조에 대한 정보는 기본 보기에서 Adobe Campaign 관리자에 의해 정의됩니다. 서비스 제공자는 게재에서 참조되며, 해당 비용 구조를 통해 해당 게재와 관련된 비용 계산은 물론 해당 주식의 관리를 수행할 수 있습니다.

## 서비스 공급자 및 해당 비용 구조 만들기 {#create-service-providers-and-their-cost-structures}

각 서비스 공급자는 연락처 세부 정보, 서비스 템플릿 및 관련 작업이 포함된 파일에 저장됩니다.

서비스 공급자가 Campaign 탐색기의 **[!UICONTROL Administration > Campaign management]** 폴더에 구성되어 있습니다.

게재 중에 수행되는 작업은 서비스 공급자(특히 DM 및 모바일 채널)가 수행합니다. 이러한 서비스 제공자는 예를 들어 메시지를 인쇄하거나 배포하는 데 관여할 수 있습니다. 이러한 작업에는 각 서비스 공급업체별 구성과 비용이 포함됩니다. 서비스 공급자 구성은 다음 네 가지 단계로 구성됩니다.

1. Adobe Campaign에서 서비스 공급자 생성. [자세히 알아보기](#add-a-service-provider)

1. 비용 범주 및 관련 서비스 템플릿의 구조를 정의합니다. [자세히 알아보기](#define-cost-categories)

1. 프로세스 구성 [자세히 알아보기](#configure-processes-associated-with-a-service).

1. 캠페인 수준에서 서비스 공급자 참조. [자세히 알아보기](#associate-a-service-with-a-campaign).

### 서비스 공급자 및 해당 비용 범주 만들기 {#create-a-service-provider-and-its-cost-categories}

#### 서비스 공급자 추가 {#add-a-service-provider}

게재에 필요한 수만큼 서비스 공급자를 만들 수 있습니다. 서비스 제공자를 추가하는 절차는 다음과 같습니다.

1. 서비스 공급자 목록 위에 있는 **[!UICONTROL New]** 단추를 클릭합니다.
1. 창의 아래 섹션에서 서비스 공급자의 이름과 연락처 세부 정보를 지정합니다.

   ![](assets/add-a-supplier.png)

1. 서비스 공급자를 목록에 추가하려면 **[!UICONTROL Save]** 단추를 클릭하십시오.

#### 비용 범주 정의 {#define-cost-categories}

이제 서비스 템플릿을 각 서비스 공급자와 연결할 수 있습니다. 이러한 템플릿에서 먼저 비용 범주와 필요한 경우 관련 재고를 식별해야 합니다. 그런 다음 원가 구조를 통해 각 범주에 대한 원가 계산 규칙을 생성할 수 있습니다. [자세히 알아보기](#define-the-cost-structure).

비용 카테고리는 게재 유형(이메일, DM, SMS 등)에 적합한 비용 세트가 포함된 엔티티입니다. 비용 범주는 서비스 제공자와 연관된 서비스 템플릿으로 그룹화됩니다. 각 서비스 제공자는 하나 이상의 서비스 템플릿을 참조할 수 있습니다.

서비스 템플릿을 만들고 콘텐츠를 정의하려면 아래 단계를 수행합니다.

1. 서비스 공급자의 **[!UICONTROL Services]** 탭에서 **[!UICONTROL Add]** 단추를 클릭하고 서비스 템플릿의 이름을 입력합니다.

   ![](assets/supplier-new-template.png)

1. 각 프로세스 유형(DM/이메일 등을 통한 게재)에 대한 비용 범주를 만듭니다. 또는 작업)을 참조하십시오. 이렇게 하려면 **[!UICONTROL Cost categories]** 탭을 클릭한 다음 **[!UICONTROL Add]** 단추를 클릭하고 각 비용 범주의 매개 변수를 입력합니다.

   ![](assets/add-cost-categories.png)

   * 이 비용 범주의 레이블을 입력하고 관련 프로세스 유형을 선택하십시오. **[!UICONTROL Direct mail]**, **[!UICONTROL Email]**, **[!UICONTROL Mobile]** 등
   * **[!UICONTROL Add]** 단추를 클릭하여 이 범주와 관련된 비용 유형을 정의합니다.
   * 필요한 경우, 사용된 수량이 자동으로 기존 주식에 관련되도록 각 원가 유형과 재고 라인을 연관시킵니다.

     >[!NOTE]
     >
     >재고 라인이 **[!UICONTROL Stock management]** 노드에 정의되어 있습니다. [자세히 알아보기](#stock-and-order-management).

1. 이 비용 범주의 값을 미리 선택할 수 있습니다. 이 값은 서비스 공급자 비용 범주의 기본값입니다(빈 값 대신). 이렇게 하려면 관련 범주 유형에 대해 **[!UICONTROL Selected]** 열에서 **예** 옵션을 활성화하십시오.

   ![](assets/default-cost-type.png)

   게재 수준에서 기본적으로 값이 선택됩니다.

### 비용 구조 정의 {#define-the-cost-structure}

각 원가 유형에 대해 원가 구조는 적용할 계산 규칙을 지정합니다.

각 비용 범주 및 유형에 대한 비용 계산을 구성하려면 **[!UICONTROL Cost structure]** 탭을 클릭하십시오. **[!UICONTROL Add]**&#x200B;을(를) 클릭하고 비용 구조를 입력합니다.

![](assets/add-cost-structure.png)

* 비용 구조를 생성하려면 계산 규칙이 적용될 비용 유형뿐만 아니라 드롭다운 목록에서 메시지 유형 및 관련 비용 범주를 선택합니다. 이러한 드롭다운 목록의 콘텐츠는 **[!UICONTROL Cost categories]** 탭을 통해 입력한 정보에서 가져옵니다.

  원가 구조에 레이블을 지정해야 합니다. 기본적으로 **비용 범주 - 비용 유형**&#x200B;의 게재 개요가 있습니다.

  그러나 이름을 바꿀 수 있습니다. **[!UICONTROL Label]** 필드에 원하는 값을 직접 입력하십시오.

* 원가 계산 공식은 창의 아래 섹션에 정의되어 있습니다.

  이 수식은 고정(메시지 수에 상관없이)하거나 메시지 수에 따라 계산할 수 있습니다.

  메시지 수에 따라 달라지는 경우 비용 계산 구조는 **[!UICONTROL Linear]**, **[!UICONTROL Linear by threshold]** 또는 **[!UICONTROL Constant by threshold]**&#x200B;일 수 있습니다.

#### 선형 구조 {#linear-structure}

메시지(또는 메시지 묶음)의 금액이 총 메시지 수와 관계없이 항상 동일하면 **[!UICONTROL Linear]**&#x200B;을(를) 선택하고 각 메시지의 비용을 입력합니다.

이 금액이 메시지 배치에 적용되는 경우 **[!UICONTROL for]** 필드에 관련된 메시지 수를 지정하십시오.

![](assets/supplier_cost_structure_calc.png)


#### 임계값에 따른 선형 구조 {#linear-structure-by-threshold}

각 메시지에 임계값별로 금액이 적용되는 경우 **[!UICONTROL Linear by threshold]** 계산 구조를 정의해야 합니다. 이러한 유형의 비용 구조에서, 예를 들어 총 메시지 수가 1과 100 사이인 경우 각 메시지의 비용은 0.13이 되며, 전송된 메시지 100개에서 1000개까지 또는 메시지 1000개를 초과하는 경우 0.12가 듭니다.

구성은 다음과 같습니다.

![](assets/supplier-cost-structure-linear.png)

임계값을 추가하려면 목록 오른쪽에 있는 **[!UICONTROL Add]** 단추를 클릭하십시오.

#### 임계값에 의한 상수 구조 {#constant-structure-by-threshold}

마지막으로, 총 메시지 수에 따라 비용 계산을 구성할 수 있습니다. 이렇게 하려면 **[!UICONTROL Constant by threshold]** 계산 구조를 선택하십시오. 예를 들어 비용은 메시지 1개부터 100개까지 고정된 12.00, 메시지 101개부터 1000개까지 전달된 경우 100.00, 메시지 1000개를 초과하는 전달된 경우 500.00개로 설정됩니다(전체 메시지 수에 상관없이).

![](assets/supplier-cost-structure-constant.png)

### 서비스와 연결된 작업 구성 {#configure-processes-associated-with-a-service}

**[!UICONTROL Jobs]** 탭을 통해 서비스 공급자와 연결된 프로세스에 대한 정보를 연결할 수 있습니다. 이 섹션에서는 라우터로 정보를 전송하도록 구성할 수 있습니다.

![](assets/cost-supplier-jobs.png)

* **[!UICONTROL File extraction]** 섹션은 이 서비스를 선택할 때 게재에 사용되는 내보내기 템플릿을 나타냅니다. **[!UICONTROL Extraction file]** 필드에 출력 파일의 이름을 나타낼 수 있습니다. 필드 오른쪽에 있는 버튼을 사용하여 변수를 삽입할 수 있습니다.

* **[!UICONTROL Notification email]** 섹션을 사용하면 파일을 보낸 후 서비스 공급자에게 알릴 템플릿을 지정할 수 있습니다. 경고 메시지를 만드는 데 사용되는 템플릿과 수신자 그룹을 선택합니다.

  기본적으로 알림 메시지의 게재 템플릿은 일반 보기에서 액세스할 수 있는 **[!UICONTROL Administration > Campaign management > Technical delivery templates]** 폴더에 저장됩니다.

* **[!UICONTROL Post-processing]** 섹션을 사용하면 게재가 승인된 후 실행할 워크플로우를 선택할 수 있습니다. 워크플로 템플릿을 입력하면 승인이 적용되는 즉시 워크플로 인스턴스가 자동으로 만들어지고 시작됩니다. 예를 들어 이 워크플로우는 외부 서비스 공급자에게 추출 파일을 보내어 처리할 수 있습니다.

### 서비스를 캠페인에 연결 {#associate-a-service-with-a-campaign}

서비스 공급자는 캠페인 게재와 연결됩니다. 게재 템플릿에서 참조되어 이 템플릿을 통해 만든 게재에서 서비스를 제공합니다.

서비스를 선택하면 게재 유형(DM, 이메일 등)에 해당하는 비용 범주 정의된 처리 옵션과 함께 중앙 테이블에 자동으로 표시됩니다.

>[!NOTE]
>
>서비스를 선택할 때 비용 범주가 표시되지 않으면 이 유형의 프로세스에 대해 정의된 비용 범주가 없음을 의미합니다. 예를 들어 전자 메일 게재의 경우 **[!UICONTROL Email]** 유형 비용 범주가 정의되지 않은 경우 범주가 표시되지 않으며 서비스를 선택해도 효과가 없습니다.

* DM 게재의 경우 구성 창에서 서비스를 선택할 수 있습니다.

  ![](assets/supplier-mail-delivery-select.png)

* 모바일 채널에서 전송하는 경우에도 동일한 선택 모드가 적용됩니다.
* 전자 메일 게재의 경우 다음 예제와 같이 게재 속성의 **[!UICONTROL Advanced]** 탭에서 서비스를 선택합니다.

  ![](assets/supplier-email-delivery-select.png)

**[!UICONTROL Amount to surcharge]** 열을 사용하면 해당 게재 또는 작업의 컨텍스트에서 이 범주에 대한 비용을 추가할 수 있습니다.

게재에 대한 비용 범주를 정의하는 동안 비용 유형의 필수 선택을 정의할 수 있습니다. 이렇게 하려면 **[!UICONTROL A cost type must be selected]**&#x200B;을(를) 선택합니다.

![](assets/cost-type-must-be-selected.png)

## 재고 및 주문 관리 {#stock-and-order-management}

경고를 처리하고, 공급을 추적하고, 주문을 실행하기 위해 원가 유형을 재고 라인과 연관시킬 수 있습니다.

Adobe Campaign에서 재고 및 주문 관리를 설정하고, 납품할 물량이 부족할 경우 운영자에게 경고하는 절차는 다음과 같습니다.

1. 관련 서비스 공급자에 대한 스톡 생성 및 참조. [자세히 알아보기](#create-a-stock).

1. 재고 라인 추가 [자세히 알아보기](#add-stock-lines).

1. 경고 발생 시 운영자에게 알림. [자세히 알아보기](#alert-operators).

1. 주문 및 공급 [자세히 알아보기](#orders).

### 재고 관리 {#stock-management}

Adobe Campaign은 재고가 소진되거나 최소 임계값에 도달한 경우 운영자 그룹에 경고할 수 있습니다. 재고 수준은 탐색 영역의 **[!UICONTROL Other choices]** 링크를 통해 **[!UICONTROL Campaigns]** 탭의 **[!UICONTROL Stocks]** 링크를 통해 액세스할 수 있습니다.

![](assets/stock-dashboard.png)

#### 스톡 만들기 {#creating-a-stock}

새 재고를 생성하려면 다음 단계를 적용합니다.

1. 재고 목록 위에 있는 **[!UICONTROL Create]** 단추를 클릭합니다.
1. 재고의 레이블을 입력하고 드롭다운 목록에서 해당 재고와 연관된 서비스 공급자를 선택합니다. [자세히 알아보기](#create-service-providers-and-their-cost-structures).

#### 재고 라인 추가 {#add-stock-lines}

스톡은 다양한 스톡 라인으로 구성됩니다. 재고 라인에는 게재에서 사용할 초기 자원 수량이 포함됩니다. 각 재고 라인은 소비된 수량, 재고 수량 및 주문 수량을 나타냅니다.

주식을 만들 때 **[!UICONTROL Stock lines]** 탭을 클릭하여 새 줄을 추가합니다.

![](assets/stock-new-lines.png)

스톡이 생성되면 대시보드를 사용하여 스톡 라인을 생성하고 모니터링합니다.

새 재고 라인을 추가하려면 **[!UICONTROL Create]** 단추를 클릭하십시오.

![](assets/add-stock-lines.png)

* **[!UICONTROL Initial stock]** 필드에 초기 재고 수량을 나타냅니다. **[!UICONTROL Consumed]** 및 **[!UICONTROL In stock]** 필드는 캠페인 진행에 따라 자동으로 계산되고 업데이트됩니다.

  ![](assets/create-new-stock-line.png)

* 운영자가 주문 재고에 대한 알림을 받아야 하는 임계값을 **[!UICONTROL Alert level]** 필드에 지정합니다. 경고 수준에 도달하면 이 재고를 사용하는 게재의 승인 창에 경고 메시지가 표시됩니다.

#### 원가분류와 재고 연결 {#associate-a-stock-with-cost-categories}

특정 서비스 공급자의 경우 서비스에서 다음과 같이 비용 범주 중 하나에 의해 재고 라인을 참조할 수 있습니다.

![](assets/select-stock-line-supplier.png)

### Stock 추적 {#stock-tracking}

#### 경고 연산자 {#alert-operators}

게재에서 참조한 스톡이 부족하면 경고가 표시됩니다. 예를 들어 추출 파일이 승인되면 다음 경고가 표시됩니다.

![](assets/stock-alert.png)

#### 주문 {#orders}

**[!UICONTROL Orders]** 하위 탭을 사용하여 현재 주문을 보고 새 주문을 저장할 수 있습니다.

주문을 저장하려면 대상 재고 라인을 편집하고 **[!UICONTROL Add]** 버튼을 클릭한 다음 배달 날짜와 주문 수량을 지정하십시오.

![](assets/order-stocks.png)

>[!NOTE]
>
>배달 날짜에 도달하면 주문된 재고 라인이 자동으로 사라지고 **[!UICONTROL Volume on order]** 필드에 입력한 수량이 **[!UICONTROL Tracking]** 탭에 추가됩니다. 이 수량은 자동으로 재고 수량에 추가됩니다.

**[!UICONTROL Consumptions]** 탭에는 캠페인당 소비된 볼륨이 포함되어 있습니다. 이 탭의 정보는 수행된 게재에 따라 자동으로 입력됩니다. 관련 캠페인을 열려면 **[!UICONTROL Edit]** 단추를 클릭하십시오.

## 예산 계산 {#calculate-budgets}

### 원칙 {#principle}

게재 및 캠페인에 대한 비용을 관리합니다. 진행 상황에 따라 이러한 비용은 예산에 할당됩니다.

캠페인에 대한 게재 비용은 캠페인 수준에서 통합되며, 프로그램의 모든 캠페인 비용은 해당 캠페인과 관련된 프로그램으로 전달됩니다. 전용 보고서를 사용하면 전체 플랫폼 또는 각 플랜과 각 프로그램에 대한 예산을 추적할 수 있습니다.

### 구현 {#implementation}

캠페인에서 예산을 선택할 때는 초기 금액을 입력해야 합니다. 계산된 원가는 입력된 금액(수행된 비용, 예상 비용, 예약된 비용, 약정된 비용)의 약정 수준에 따라 자동으로 업데이트됩니다.


<!--
See [Calculating amounts](../../mrm/using/controlling-costs.md#calculating-amounts).

>[!NOTE]
>
>The procedure for creating budgets is presented in [Creating a budget](../../mrm/using/controlling-costs.md#creating-a-budget).
-->
