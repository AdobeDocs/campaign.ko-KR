---
product: campaign
title: 분할
description: 분할 워크플로우 활동에 대해 자세히 알아보기
feature: Workflows, Targeting Activity
exl-id: bf4935dd-87dc-4c5c-becf-8c4df61805fd
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '1796'
ht-degree: 0%

---

# 분할{#split}

A **분할**-type 활동을 사용하면 대상을 여러 하위 집합으로 분할할 수 있습니다. 타겟은 받은 모든 결과로 구성됩니다. 따라서 이 활동을 실행하려면 모든 이전 활동이 완료되어야 합니다.

이 활동은 인바운드 모집단의 결합을 트리거하지 않습니다. 여러 전환이 하나의 분할 활동으로 랜딩되는 경우 **[!UICONTROL Union]** 활동 을 참조하십시오.

사용 중인 분할 활동의 예는 를 참조하십시오. [이 섹션](targeting-workflows.md#create-subsets-using-the-split-activity).

분할 활동을 사용하여 필터링 조건을 사용하여 대상을 다른 모집단으로 분할하는 방법을 보여 주는 예제에 설명되어 있습니다 [이 섹션](cross-channel-delivery-workflow.md).

분할 활동에서 인스턴스 변수를 사용하는 방법을 보여주는 예는에서 사용할 수 있습니다. [이 섹션](javascript-scripts-and-templates.md).

이 활동을 구성하려면 하위 집합 콘텐츠와 레이블을 **[!UICONTROL Subsets]** 탭을 선택한 다음, **[!UICONTROL General]** 탭.

## 하위 집합 만들기 {#create-subsets}

하위 집합을 생성하려면 다음을 수행합니다.

1. 일치 필드에서 레이블을 클릭하고 적용할 필터를 선택합니다.
1. 인바운드 모집단을 필터링하려면 **[!UICONTROL Add a filtering condition]** 옵션을 클릭하고 **[!UICONTROL Edit...]** 링크를 클릭합니다.

   이 집합에 포함할 데이터에 적용할 필터 유형을 선택합니다.

   프로세스는 의 경우와 동일합니다. **쿼리**-type 활동.

   >[!NOTE]
   >
   >최대 2개의 외부 데이터베이스(FDA)에서 데이터를 필터링할 수 있습니다.

1. 대상에서 추출할 최대 레코드 수를 지정하여 하위 집합을 만들 수 있습니다. 이렇게 하려면 다음을 확인하십시오. **[!UICONTROL Limit the selected records]** 옵션을 클릭하고 **[!UICONTROL Edit...]** 링크를 클릭합니다.

   마법사를 사용하여 이 하위 집합의 레코드에 대한 선택 모드를 선택할 수 있습니다. [자세히 알아보기](#limit-the-number-of-subset-records)

   ![](assets/s_user_segmentation_partage4.png)

1. 원한다면 다음을 수행할 수 있습니다. **다른 하위 집합 추가** 사용 **[!UICONTROL Add]** 단추를 클릭합니다.

   ![](assets/s_user_segmentation_partage_add.png)

   >[!NOTE]
   >
   >다음과 같은 경우 **[!UICONTROL Enable overlapping of output populations]** 옵션을 선택하지 않으면 탭 순서대로 하위 집합이 만들어집니다. 이 창의 오른쪽 상단에 있는 화살표를 사용하여 이동합니다. 예를 들어 첫 번째 하위 집합이 초기 모집단의 70%를 복구하는 경우 다음 하위 집합은 나머지 30%에만 선택 기준을 적용합니다.

   생성된 각 하위 세트에 대해 아웃바운드 전환이 분할 활동에 추가됩니다.

   ![](assets/s_user_segmentation_partage_add2.png)

   단일 아웃바운드 전환을 생성하도록 선택하고(예: 세그먼트 코드를 사용하여 세트 식별) 이렇게 하려면 다음을 선택합니다. **[!UICONTROL Generate subsets in the same table]** 의 옵션 **[!UICONTROL General]** 탭.

   완료되면, 각 서브셋의 세그먼트 코드는 자동으로 추가 열에 저장된다. 이 열은 게재 수준의 개인화 필드에서 액세스할 수 있습니다.

## 하위 집합 레코드 수 제한 {#limit-the-number-of-subset-records}

하위 집합에 포함된 전체 모집단을 사용하지 않으려면 포함될 레코드 수를 제한할 수 있습니다.

1. 하위 집합 편집 창에서 다음을 확인합니다. **[!UICONTROL Limit the selected records]** 옵션을 클릭하고 **[!UICONTROL Edit...]** 링크를 클릭합니다.
1. 선택한 제한 유형을 선택합니다.

   * **[!UICONTROL Activate random sampling]**: 이 옵션은 레코드의 무작위 샘플을 가져옵니다. 적용되는 임의 샘플링 유형은 데이터베이스 엔진에 따라 다릅니다.
   * **[!UICONTROL Keep only the first records after sorting]**: 이 옵션을 사용하면 하나 이상의 정렬 명령을 기준으로 제한을 정의할 수 있습니다. 을(를) 선택하는 경우 **[!UICONTROL Age]** 필드를 정렬 기준으로 하고 100을 제한으로 설정하면 가장 어린 100명의 수신자만 유지됩니다.
   * **[!UICONTROL Keep the first ones after sorting (criteria, random)]**: 이 옵션은 앞의 두 옵션을 결합합니다. 하나 이상의 정렬 순서에 따라 제한을 정의한 다음, 일부 레코드가 정의된 기준과 동일한 값을 갖는 경우 첫 번째 레코드에 무작위 선택을 적용할 수 있습니다.

      예를 들어 **[!UICONTROL Age]** 필드를 정렬 기준으로 사용하고 제한을 100개로 정의하지만, 데이터베이스의 가장 최신 수신자 2000명은 모두 18개이므로 2000개 중 100명의 수신자가 임의로 선택됩니다.
   ![](assets/s_user_segmentation_partage_wz1.png)

1. 정렬 기준을 정의하려면 추가 단계를 통해 열과 정렬 순서를 정의할 수 있습니다.

   ![](assets/s_user_segmentation_partage_wz1.1.png)

1. 그런 다음 데이터 제한 방법을 선택합니다.

   ![](assets/s_user_segmentation_partage_wz2.png)

   다음과 같은 몇 가지 방법이 있습니다.

   * **[!UICONTROL Size (in %)]**: 레코드의 비율. 예를 들어 아래 구성은 전체 모집단의 10%를 추출합니다.

      백분율은 활동의 결과가 아닌 초기 모집단에 적용됩니다.

   * **[!UICONTROL Size (as a % of the segment)]**: 하위 집합에만 관련되고 초기 모집단과 관련되지 않은 레코드의 백분율입니다.
   * **[!UICONTROL Maximum size]**: 최대 레코드 수입니다.
   * **[!UICONTROL By data grouping]**: 인바운드 모집단의 지정된 필드에 있는 값에 따라 레코드 수에 대한 제한을 설정할 수 있습니다. [자세히 알아보기](#limit-the-number-of-subset-records-by-data-grouping)
   * **[!UICONTROL By data grouping (in %)]**: 백분율을 사용하여 인바운드 모집단의 지정된 필드에 있는 값에 따라 레코드 수에 대한 제한을 설정할 수 있습니다. [자세히 알아보기](#limit-the-number-of-subset-records-by-data-grouping)
   * **[!UICONTROL By data distribution]**: 그룹화 필드에 값이 너무 많거나 각 새 분할 활동에 대해 값을 다시 입력하지 않으려면 Adobe Campaign을 사용하여 다음을 구성할 수 있습니다. **[!UICONTROL By data distribution]** 제한 사항(선택적 분산 마케팅 모듈). [자세히 알아보기](#limit-the-number-of-subset-records-per-data-distribution)

1. 클릭 **[!UICONTROL Finish]** 레코드 선택 기준을 승인합니다. 그러면 정의된 구성이 편집기의 중간 창에 표시됩니다.

## 데이터 그룹별로 하위 집합 레코드 수 제한 {#limit-the-number-of-subset-records-by-data-grouping}

데이터 그룹화별로 레코드 수를 제한할 수 있습니다. 이 제한은 고정된 값 또는 백분율을 사용하여 수행할 수 있습니다.

예를 들어, **[!UICONTROL Language]** 필드는 그룹 필드로 각 언어에 대한 레코드 목록을 정의할 수 있습니다.

1. 데이터 제한 값을 선택한 후 다음을 선택합니다. **[!UICONTROL By data grouping]** 또는 **[!UICONTROL By data grouping (as a %)]** 및 클릭 **[!UICONTROL Next]**.

   ![](assets/s_user_segmentation_partage_wz3.png)

1. 그런 다음 그룹화 필드(을)를 선택합니다 **[!UICONTROL Language]** 인스턴스 필드)를 클릭하고 **[!UICONTROL Next]**.

   ![](assets/s_user_segmentation_partage_wz4.png)

1. 마지막으로 데이터 그룹화 임계값을 지정합니다(이전에 선택한 그룹화 방법에 따라 고정된 값 또는 백분율을 사용). 모든 값에 대해 동일한 임계값을 설정하려면(예: 각 언어에 대한 레코드 수를 10으로 설정하려면) 다음을 선택합니다 **[!UICONTROL All data groupings are the same size]** 옵션을 선택합니다. 모든 값에 대해 다른 제한을 설정하려면 **[!UICONTROL Limitations by grouping value]** 옵션을 선택합니다. 이렇게 하면 영어, 프랑스어 등에 대한 다른 제한을 선택할 수 있습니다.

   ![](assets/s_user_segmentation_partage_wz5.png)

1. 클릭 **[!UICONTROL Finish]** 을 눌러 제한을 승인하고 분할 활동 편집으로 돌아갑니다.

## 데이터 배포당 하위 집합 레코드 수 제한 {#limit-the-number-of-subset-records-per-data-distribution}

그룹화 필드에 너무 많은 값이 포함되어 있거나 모든 새 분할 활동에 대해 값을 재설정하지 않으려는 경우 Adobe Campaign을 사용하여 데이터 분포별로 제한을 만들 수 있습니다. 선택 시 [데이터 제한 값](#create-subsets) 섹션)에서 **[!UICONTROL By data distribution]** 옵션을 선택하고 드롭다운 메뉴에서 템플릿을 선택합니다. 데이터 배포 템플릿 만들기는 아래에 나와 있습니다.

예: **[!UICONTROL Local approval]** 배포 템플릿이 있는 활동은 다음을 참조하십시오. [이 페이지](local-approval-activity.md).

![](assets/s_user_segmentation_partage_wz6.png)

>[!CAUTION]
>
>이 함수는 [분산 마케팅 추가 기능](../distributed-marketing/about-distributed-marketing.md). 사용권 계약을 확인하십시오.

데이터 배포 템플릿을 사용하면 그룹화 값 목록을 사용하여 레코드 수를 제한할 수 있습니다. 데이터 배포 템플릿을 만들려면 다음 단계를 적용합니다.

1. 데이터 배포 템플릿을 만들려면 **[!UICONTROL Resources > Campaign management > Data distribution]** 노드 및 클릭 **[!UICONTROL New]**.

   ![](assets/local_validation_data_distribution_1.png)

1. 다음 **[!UICONTROL General]** 탭에서는 레이블과 배포의 실행 컨텍스트(타겟팅 차원, 배포 필드)를 입력할 수 있습니다.

   ![](assets/local_validation_data_distribution_2.png)

   다음 필드를 입력해야 합니다.

   * **[!UICONTROL Label]**: 배포 템플릿에 대한 레이블입니다.
   * **[!UICONTROL Targeting dimension]**: 데이터 배포를 적용할 타겟팅 차원을 입력합니다. **[!UICONTROL Recipient]** 예. 이 스키마는 항상 타겟팅 워크플로우에서 사용되는 데이터와 호환되어야 합니다.
   * **[!UICONTROL Distribution field]**: 타겟팅 차원을 통해 필드를 선택합니다. 예를 들어, **[!UICONTROL Email domain]** 필드, 받는 사람 목록은 도메인별로 분류됩니다.
   * **[!UICONTROL Distribution type]**: 대상에서 제한 값을 분류하는 방법을 선택합니다. **[!UICONTROL Distribution]** 탭: **[!UICONTROL Percentage]** 또는 **[!UICONTROL Set]**.
   * **[!UICONTROL Approval storage]**: 를 사용하는 경우 [로컬 승인](local-approval.md) 타겟팅 워크플로우에서 승인 결과가 저장될 스키마를 입력합니다. 타깃팅 스키마당 하나의 저장소 스키마를 지정해야 합니다. 를 사용하는 경우 **[!UICONTROL Recipients]** 타깃팅 스키마, 기본값 입력 **[!UICONTROL Local approval of recipients]** 스토리지 스키마.

      로컬 승인 없이 데이터 그룹화에 의해 간단하게 제한되는 경우 **[!UICONTROL Approvals storage]** 필드.

1. 를 사용하는 경우 [로컬 승인](local-approval.md) 활동, 다음을 입력합니다. **[!UICONTROL Advanced settings]** 배포 템플릿의 경우:

   ![](assets/local_validation_data_distribution_3.png)

   다음 필드를 입력해야 합니다.

   * **[!UICONTROL Approve targeted messages]**: 승인할 수신자 목록에서 모든 수신자를 미리 선택하려면 이 옵션을 선택합니다. 이 옵션을 선택 취소하면 수신자를 미리 선택하지 않습니다.

      >[!NOTE]
      >
      >이 옵션은 기본적으로 선택되어 있습니다.

      ![](assets/local_validation_notification.png)

   * **[!UICONTROL Delivery label]**: 반환 알림에 게재 레이블을 표시하는 표현식을 정의할 수 있습니다. 기본 표현식은 게재의 표준 레이블(계산 문자열)에 대한 정보를 제공합니다. 이 표현식은 수정할 수 있습니다.

      ![](assets/local_validation_notification_3.png)

   * **[!UICONTROL Grouping field]**: 이 필드에서는 수신자를 승인 및 반송 알림에 표시하는 데 사용되는 그룹화를 정의할 수 있습니다.

      ![](assets/local_validation_notification_4.png)

   * **[!UICONTROL Web Interface]**: 웹 애플리케이션을 수신자 목록에 연결할 수 있습니다. 승인 및 반환 알림에서 각 수신자는 클릭할 수 있고 선택한 웹 애플리케이션에 연결됩니다. 다음 **[!UICONTROL Parameters]** 필드(예 **[!UICONTROL recipientId]**)을 사용하면 URL 및 웹 애플리케이션에서 사용할 추가 매개 변수를 구성할 수 있습니다.

1. 다음 **[!UICONTROL Breakdown]** 탭에서는 배포 값 목록을 정의할 수 있습니다.

   ![](assets/local_validation_data_distribution_4.png)

   * **[!UICONTROL Value]**: 배포 값을 입력합니다.
   * **[!UICONTROL Percentage / Set]**: 각 값에 연결된 레코드 제한(고정 또는 백분율)을 입력합니다.

      이 열은 **[!UICONTROL Distribution type]** 필드 내 **[!UICONTROL General]** 탭.

   * **[!UICONTROL Label]**: 각 값에 연결된 레이블을 입력합니다.
   * **[!UICONTROL Group or operator]**: 를 사용하는 경우[로컬 승인](local-approval.md) 활동에서 각 분배 값에 지정된 연산자 또는 연산자 그룹을 선택합니다.

      로컬 승인 없이 데이터 그룹화에 의해 간단하게 제한되는 경우 **[!UICONTROL Group or operator]** 필드.

      >[!CAUTION]
      >
      >운영자에게 적절한 권한이 할당되었는지 확인합니다.

## 매개 변수 필터링 {#filtering-parameters}

다음을 클릭합니다. **[!UICONTROL General]** 탭으로 이동하여 활동 레이블을 입력합니다. 이 분할에 대한 대상 및 필터 차원을 선택합니다. 필요한 경우 주어진 하위 집합에 대해 이러한 차원을 변경할 수 있습니다.

![](assets/s_user_segmentation_partage_general.png)

다음 확인: **[!UICONTROL Generate complement]** 나머지 모집단을 활용하려면 옵션을 선택합니다. 보수는 인바운드 대상에서 하위 집합의 결합을 뺀 것입니다. 그러면 다음과 같이 추가 아웃바운드 전환이 활동에 추가됩니다.

![](assets/s_user_segmentation_partage_compl.png)

이 옵션이 제대로 작동하려면 인바운드 데이터에 기본 키가 있어야 합니다.

예를 들어 Netezza (색인의 개념을 지원하지 않음)과 같은 외부 데이터베이스에서 **[!UICONTROL Data loading (RDBMS)]** 활성, 다음으로 생성된 보체 **[!UICONTROL Split]** 활동이 올바르지 않습니다.

이 문제를 방지하기 위해 **[!UICONTROL Enrichment]** 활동 바로 앞 **[!UICONTROL Split]** 활동. 다음에서 **[!UICONTROL Enrichment]** 활동, 확인 **[!UICONTROL Keep all additional data from the main set]** 및 추가 데이터에서 의 필터를 구성하는 데 사용할 열을 지정합니다. **[!UICONTROL Split]** 활동. 의 인바운드 전환에서 가져온 데이터 **[!UICONTROL Split]** 그런 다음 활동은 Adobe Campaign 서버의 임시 테이블에 로컬로 저장되며 보조 활동을 올바르게 생성할 수 있습니다.

다음 **[!UICONTROL Enable overlapping of output populations]** 옵션을 사용하면 여러 하위 집합에 속하는 모집단을 관리할 수 있습니다.

* 상자를 선택하지 않으면 분할 활동은 수신자가 여러 하위 집합의 기준을 만족하더라도 여러 출력 전환에 있을 수 없도록 합니다. 첫 번째 탭의 타겟에서 기준이 일치합니다.
* 상자를 선택하면 수신자가 필터 기준을 충족하면 여러 하위 집합에서 찾을 수 있습니다. Adobe Campaign에서는 제외 기준을 사용하는 것이 좋습니다.

## 입력 매개 변수 {#input-parameters}

* tableName
* 스키마

각 인바운드 이벤트는 이러한 매개 변수로 정의된 대상을 지정해야 합니다.

## 출력 매개 변수 {#output-parameters}

* tableName
* 스키마
* recCount

이 세 값 세트는 제외로 인한 대상을 식별합니다. **[!UICONTROL tableName]** 는 대상 식별자를 기록하는 테이블의 이름입니다. **[!UICONTROL schema]** 모집단의 스키마(일반적으로 nms:recipient)이며, **[!UICONTROL recCount]** 는 테이블에 있는 요소의 수입니다.

보체와 관련된 전환은 동일한 매개 변수를 갖는다.
