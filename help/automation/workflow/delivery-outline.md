---
product: campaign
title: 게재 개요
description: 게재 개요 워크플로우 활동에 대해 자세히 알아보기
feature: Workflows, Targeting Activity
exl-id: 3c06b329-b2d8-4ac8-ab9b-3ab3e525d109
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 1%

---

# 게재 개요{#delivery-outline}

다음 **게재 개요** 캠페인 워크플로우에서 아웃라인을 사용할 수 있습니다. 그 윤곽은 미리 캠페인에서 만들어졌을 것이다.

활동을 구성하려면 원하는 아웃라인과 계획된 연락 날짜를 선택하기만 하면 됩니다. 유형화 또는 유형화 규칙을 추가하여 필터링 규칙을 추가할 수 있습니다.

## 예: 게재 개요를 통해 오퍼 삽입 {#example--inserting-an-offer-via-a-delivery-outline}

다음 **게재 개요** 캠페인 워크플로우에서 사용할 수 있는 활동을 사용하면 현재 진행 중인 캠페인의 게재 개요에서 참조되는 오퍼를 제공할 수 있습니다.

>[!NOTE]
>
>다음 **상호 작용** 패키지를 설치해야 합니다.

1. 워크플로우에서 게재 활동을 추가하기 전에 게재 개요 활동을 추가합니다.
1. 게재 개요 활동에서 사용할 개요를 지정합니다.
1. 게재에 따라 사용 가능한 필드를 작성합니다.
1. 두 가지 가능한 경우가 있습니다.

   * 오퍼 엔진을 호출하려면 **[!UICONTROL Restrict the number of propositions selected]** 상자. 게재에 표시될 오퍼 공간 및 제안 수를 지정합니다.

      오퍼 가중치 및 자격 규칙은 오퍼 엔진에서 고려됩니다.

   * 확인란을 선택하지 않으면 오퍼 엔진을 호출하지 않고 게재 개요의 모든 오퍼가 표시됩니다.

   미리 보기는 게재에 지정된 오퍼 수를 고려합니다. 워크플로우를 실행할 때 고려되는 번호는 게재 개요에 지정된 번호입니다.

   ![](assets/int_compo_offre_wf1.png)
