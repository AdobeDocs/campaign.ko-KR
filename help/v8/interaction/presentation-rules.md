---
product: campaign
title: 프레젠테이션 규칙
description: 프레젠테이션 규칙
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: f9dd9ad6-48da-4a80-9405-109a433a1ed5
TQID: 'https://experienceleague.adobe.com/s2QV1BGLtUfyWg1BfYuryciF9STRK3HpIXNc6oQ0ATY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%
---
# 프레젠테이션 규칙{#presentation-rules}



## 프레젠테이션 규칙 만들기 {#creating-a-presentation-rule}

저희 데이터베이스에 유럽, 아프리카, 미국, 캐나다에 대한 몇 가지 여행 제안이 있습니다. 캐나다 여행에 대한 오퍼를 보내고 싶지만, 수신자가 이 유형의 오퍼를 거부하는 경우, 다시 보내고 싶지 않습니다.

캐나다 여행은 수신자 당 한 번만 제공되고 거부되면 다시 제공되지 않도록 규칙을 구성할 예정입니다.

1. Adobe Campaign 트리에서 **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Typology management]** > **[!UICONTROL Typology rules]** 노드로 이동합니다.
1. 새 **[!UICONTROL Offer presentation]** 형식 규칙을 만듭니다.

   ![규칙 유형 목록이 열려 있고 오퍼 프레젠테이션이 선택된 유형화 규칙 만들기 양식](assets/offer_typology_example_001.png)

1. 필요한 경우 레이블 및 설명을 변경합니다.

   레이블, 오퍼 표시 유형, 전자 메일 채널 및 설명을 입력한 ![유형화 규칙 일반 탭](assets/offer_typology_example_002.png)

1. 규칙을 모든 채널로 확장하려면 **[!UICONTROL All channels]** 옵션을 선택하십시오.

   ![모든 채널이 선택된 유형화 규칙의 채널 목록](assets/offer_typology_example_003.png)

1. **[!UICONTROL Edit expression]** 링크를 클릭하고 **[!UICONTROL Category]** 노드를 식으로 선택합니다.

   ![식 선택 대화 상자를 열어 범주 필드를 선택할 수 있는 쿼리 창](assets/offer_typology_example_004.png)

1. 캐나다 여행 오퍼와 일치하는 범주를 선택하고 **[!UICONTROL OK]**&#x200B;을(를) 클릭하여 쿼리 창을 닫습니다.

   ![여행 오퍼 범주 트리에서 선택한 캐나다 폴더를 사용하여 캐나다와 같은 범주를 쿼리](assets/offer_typology_example_005.png)

1. **[!UICONTROL Offer presentation]** 탭에서 환경에 구성된 차원과 동일한 차원을 선택합니다.

   ![환경과 일치하는 타겟팅 차원 및 저장소 차원을 표시하는 오퍼 프레젠테이션 탭](assets/offer_typology_example_006.png)

1. 규칙을 적용할 기간을 지정합니다.

   ![슬라이딩 기간, 기간 고려 필드가 10d로 설정된 오퍼 프레젠테이션 탭](assets/offer_typology_example_007.png)

1. 이미 캐나다 여행을 거부한 수신자가 유사한 다른 오퍼를 받지 않도록 제안을 1개로 제한합니다.

   ![최대 제안 수 수량 필드가 1](assets/offer_typology_example_008.png)(으)로 설정된 오퍼 프레젠테이션 탭

1. **캐나다** 범주에서 모든 오퍼를 제외하려면 **[!UICONTROL Offers for the same category]** 필터를 선택하십시오.

   ![선택한 동일한 범주에 대한 오퍼와 함께 계산할 제안의 오퍼 드롭다운](assets/offer_typology_example_020.png)

1. 받는 사람이 거부한 제안만 고려하려면 **[!UICONTROL Rejected propositions]** 필터를 선택하세요.

   ![거부된 제안을 선택한 상태로 계산할 제안의 제안 상태 드롭다운](assets/offer_typology_example_021.png)

1. 이 규칙을 적용할 수신자를 선택합니다.

   이 예제에서는 **자주 방문하는 사람**&#x200B;명을 선택합니다.

   ![필터링 쿼리 편집 마법사: 자주 사용하는 여행자 받는 사람 폴더를 규칙 대상으로 선택](assets/offer_typology_example_009.png)

1. 오퍼 유형화에서 규칙을 참조합니다.

   선택한 오퍼 유형화를 나열하는 유형화 추가 대화 상자가 있는 규칙의 ![유형화 탭](assets/offer_typology_example_013.png)

1. 오퍼 환경(**환경 - 이 경우 수신자**)으로 이동한 다음 **[!UICONTROL Eligibility]** 탭의 드롭다운 목록을 사용하여 방금 만든 새 유형화를 참조합니다.

   ![오퍼를 표시하는 오퍼 표시 유형 목록이 있는 오퍼 환경의 자격 탭](assets/offer_typology_example_014.png)

## 프레젠테이션 규칙 적용 {#applying-the-presentation-rule}

다음은 이전에 만든 유형화 규칙의 적용 예입니다.

우리는 캐나다 카테고리에 속하는 첫 번째 오퍼 제안을 보내려고 합니다. 수신자가 오퍼를 한 번 거부하면 다시 오퍼가 제공되지 않습니다.

1. **자주 찾는 여행자** 받는 사람 폴더에서 프로필 중 하나를 선택하여 해당 프로필에 해당하는 오퍼를 확인합니다. **[!UICONTROL Propositions]** 탭을 클릭한 다음 **[!UICONTROL Preview]** 탭을 클릭합니다.

   이 예제에서 **Tim Ramsey**&#x200B;은(는) **Americas** 카테고리의 일부인 오퍼에 참가할 수 있습니다.

   ![수신자 제안 탭, 미리 보기 하위 탭, 미주 카테고리에 대한 적격 오퍼를 나열하는 중](assets/offer_typology_example_015.png)

1. 먼저 **자주 방문하는 사용자**&#x200B;명의 받는 사람을 대상으로 하는 전자 메일 게재를 만듭니다.
1. 오퍼 엔진 호출 매개 변수를 선택합니다.

   이 예제에서는 **캐나다** 및 **미국** 하위 범주를 포함하는 **미국 여행** 범주를 선택합니다.

   ![아메리카 범주와 메시지당 2개의 제안을 포함하는 전자 메일 게재의 오퍼 관리 대화 상자](assets/offer_typology_example_016.png)

1. 메시지 본문에 오퍼를 삽입하고 게재를 보냅니다. 자세한 내용은 [아웃바운드 채널 정보](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/offers/interaction-send-offers){target="_blank"}(Campaign v8 설명서)를 참조하세요.

   수신자가 적격한 오퍼를 수신했습니다.

1. 수용자는 제안 기록에 나타난 바와 같이 캐나다 제안을 거부하였다.

   ![거부됨 상태의 캐나다 snowmobile 오퍼가 있는 수신자 제안 내역](assets/offer_typology_example_018.png)

1. 이제 적격한 오퍼를 확인합니다.

   캐나다에 대한 오퍼가 선택되지 않았음을 알 수 있습니다.

   ![New-York과 Grand Canyon에 적합한 오퍼를 표시하는 수신자 미리 보기 탭, 캐나다 오퍼 없음](assets/offer_typology_example_019.png)
