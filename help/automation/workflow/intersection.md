---
product: campaign
title: 교차
description: 교차
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 12777107-5ccc-4f19-9dcd-8f6cade3ee98
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 5%

---

# 교차{#intersection}



**교차** 유형 활동은 수신된 대상의 교차에서 대상을 만듭니다.

교차를 사용하면 모든 인바운드 활동 결과에 공통되는 모집단만 추출할 수 있습니다. 모든 결과가 수신된 타겟이 생성됩니다. 따라서 교차를 실행하려면 모든 이전 활동이 완료되어야 합니다. 이 활동을 구성하려면 활동에 대한 레이블과 결과에 대한 옵션을 입력해야 합니다.

![](assets/s_user_segmentation_inter.png)

교차 활동 구성 및 사용에 대한 자세한 내용은 [공동 데이터 추출(교차)](targeting-workflows.md#extracting-joint-data--intersection-)을 참조하세요.

나머지 모집단을 처리하려면 **[!UICONTROL Generate complement]** 옵션을 선택하십시오. 여집합에는 교차를 제외한 모든 인바운드 활동 결과의 합집합이 포함됩니다. 그러면 다음과 같이 추가 아웃바운드 전환이 활동에 추가됩니다.

![](assets/s_user_segmentation_inter_compl.png)

## 교차 예 {#intersection-example}

다음 예제에서는 목록을 만들기 위해 간단한 쿼리 3개에 공통되는 수신자를 계산하는 것이 교차 범위의 목적입니다.

1. 간단한 쿼리 3개 후 **[!UICONTROL Intersection]** -type 활동을 삽입합니다.

   이 예에서, 쿼리는 각각 남성, 파리에 거주하는 수신자 및 18세에서 30세 사이의 수신자를 타겟팅합니다.

1. 교차를 구성합니다. 이렇게 하려면 쿼리에서 얻은 모집단에 일관된 데이터가 포함되어 있으므로 **[!UICONTROL Keys only]** 조정 방법을 선택하십시오.
1. 쿼리에 대한 추가 데이터를 입력한 경우 관련 상자를 선택하여 수신자가 공유하는 데이터만 유지하도록 선택할 수 있습니다.
1. 쿼리와 관련된 나머지 데이터를 사용하려면 **[!UICONTROL Generate complement]** 상자를 선택합니다.
1. 교차 결과 뒤에 목록 업데이트 활동을 추가합니다. 목록 업데이트를 보조 목록에 추가할 수도 있습니다.
1. 워크플로우를 실행합니다. 여기서, 두 명의 수신자가 동시에 세 개의 입력 쿼리에 모두 적용된다. 보완은 세 개의 질의 중 한두 개에 대해서만 지원하는 5명의 수신자로 구성된다.

   교차 결과가 첫 번째 목록 업데이트로 전송됩니다. 보조 기능을 사용하도록 선택한 경우 보조 목록 업데이트로도 전송됩니다.

   ![](assets/intersection_example.png)

## 입력 매개 변수 {#input-parameters}

* tableName
* 스키마

각 인바운드 이벤트는 이러한 매개 변수로 정의된 대상을 지정해야 합니다.

## 출력 매개 변수 {#output-parameters}

* tableName
* 스키마
* recCount

이 세 값 세트는 교차로 인한 대상을 식별합니다. **[!UICONTROL tableName]**&#x200B;은(는) 대상 식별자를 기록하는 테이블의 이름이고, **[!UICONTROL schema]**&#x200B;은(는) 모집단의 스키마(일반적으로 **[!UICONTROL nms:recipient]**)이며, **[!UICONTROL recCount]**&#x200B;은(는) 테이블의 요소 수입니다.
