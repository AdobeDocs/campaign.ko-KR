---
product: campaign
title: 아웃바운드 채널에 대한 오퍼
description: 아웃바운드 채널에 대한 오퍼
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: 77fee343-09d1-4d60-be43-efe02953a70c
TQID: 'https://experienceleague.adobe.com/WGoYaHNR13J47UVmKpHRSm9aw0T8ZrvHUl9zGXezQBU'
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
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 1%
---
# 아웃바운드 채널에 대한 오퍼{#offers-on-an-outbound-channel}



## 이메일 오퍼 게재 {#email-offer-delivery}

저희 데이터베이스에 아프리카 여행 상품 분류가 있습니다. 각 오퍼의 자격, 컨텍스트 및 표시가 구성되었습니다. 이제 이메일을 통해 오퍼를 제공하는 캠페인을 만들려고 합니다.

1. 마케팅 캠페인 및 타겟팅 워크플로우를 만듭니다.

   ![아프리카 여행 캠페인의 타기팅 워크플로우: 폴더, 게재, 중복 제거 및 두 개의 목록 업데이트 활동](assets/offer_delivery_example_001.png)

1. 전자 메일 게재를 편집하고 **[!UICONTROL Offers]** 아이콘을 클릭합니다.

   ![오퍼 아이콘으로 전자 메일 배달(오퍼 관리 창, 오퍼 선택 옵션 및 오퍼 공간 필드 열기](assets/offer_delivery_example_002.png))

1. 공휴일과 일치하는 오퍼 환경의 이메일 공간을 선택합니다.

   ![구독자 여정을 포함하여 사용 가능한 전자 메일 공간을 표시하는 오퍼 공간 목록이 있는 오퍼 관리 창](assets/offer_delivery_example_003.png)

1. 아프리카 여행 상품을 포함하는 범주를 선택하세요.

   ![오퍼 카탈로그 및 여정 아래에 범주 트리가 확장된 오퍼 관리 창, 아프리카 범주 강조 표시](assets/offer_delivery_example_004.png)

1. 게재에서 오퍼 수를 2로 설정합니다.

   ![아프리카 범주 및 메시지당 제안 수가 2](assets/offer_delivery_example_005.png)(으)로 설정된 오퍼 관리 창

1. 오퍼 관리 창을 닫고 게재 콘텐츠를 만듭니다.

   ![기본 포함 보기가 포함된 이메일 게재 HTML 콘텐츠 편집기, 오퍼 제안 준비 완료](assets/offer_delivery_example_006.png)

1. 메뉴를 사용하여 첫 번째 오퍼 제안을 삽입하고 HTML 렌더링 함수를 선택합니다.

   ![HTML 컨텐츠 도구 모음 메뉴: 제안, 제안 1, 렌더링 기능 및 HTML 렌더링](assets/offer_delivery_example_007.png)

1. 두 번째 오퍼 제안을 삽입합니다.

   ![두 제안 모두 포함된 전자 메일 HTML 콘텐츠에는 구독 취소 링크 앞에 렌더링/html 보기를 사용하는 줄이 포함됩니다](assets/offer_delivery_example_008.png)

1. **[!UICONTROL Preview]**&#x200B;을(를) 클릭하여 게재에서 오퍼를 미리 본 다음 오퍼를 받을 받는 사람을 선택하여 오퍼를 미리 봅니다.

   ![선택한 받는 사람에 대한 Sahara 오퍼 제목, 텍스트 및 이미지가 포함된 전자 메일을 표시하는 게재 미리 보기 탭](assets/offer_delivery_example_009.png)

1. 게재를 저장하고 타겟팅 워크플로우를 시작합니다.
1. 게재를 열고 게재의 **[!UICONTROL Audit]** 탭을 클릭합니다. 카탈로그의 다양한 오퍼에서 만들 제안을 오퍼 엔진에서 선택했음을 확인할 수 있습니다.

   ![Pyramids 및 Sahara 오퍼와 같이 오퍼별로 생성된 제안을 나열하는 게재 감사 탭 로그](assets/offer_delivery_example_010.png)

## 오퍼 시뮬레이션 수행 {#perform-an-offer-simulation}

1. **[!UICONTROL Profiles and Targets]** 탭에서 **[!UICONTROL Simulations]** 링크를 클릭한 다음 **[!UICONTROL Create]** 단추를 클릭합니다.

   템플릿, 레이블 및 폴더가 있는 새 오퍼 시뮬레이션 대화 상자를 여는 만들기 단추가 있는 ![시뮬레이션 목록](assets/offer_simulation_001.png)

1. 레이블을 선택하고 필요한 경우 실행 설정을 지정합니다.

   ![레이블 1년 구독자, 시뮬레이션 폴더 및 실행 설정이 있는 새 오퍼 시뮬레이션 대화 상자](assets/offer_simulation_example_002.png)

1. 시뮬레이션을 저장합니다. 그러면 새 탭에서 열립니다.

   ![편집 탭과 시뮬레이션 시작 단추가 있는 1년 구독자의 시뮬레이션 대시보드](assets/offer_simulation_example_003.png)

1. **[!UICONTROL Edit]** 탭을 클릭한 다음 **[!UICONTROL Scope]**&#x200B;을(를) 클릭합니다.

   ![환경 또는 범주, 오퍼 공간, 테마, 연락처 날짜 및 제안을 포함하는 시뮬레이션 편집 탭, 범위 섹션](assets/offer_simulation_example_004.png)

1. 오퍼를 시뮬레이션할 범주를 선택합니다.

   ![오퍼 - 디자인 및 오퍼 카탈로그에서 확장된 환경 또는 범주 목록(여행 범주 선택)](assets/offer_simulation_example_005.png)

1. 시뮬레이션에 사용할 오퍼 공간을 선택하십시오.

   ![DM 및 전자 메일을 제공하는 여행 범주 아래의 오퍼 공간 목록(환경 - 수신자)](assets/offer_simulation_example_006.png)

1. 유효 일자를 입력합니다. 시작 날짜 이상을 입력해야 합니다. 이렇게 하면 오퍼 엔진이 오퍼를 필터링하고 주어진 날짜에 유효한 오퍼를 선택할 수 있습니다.
1. 필요한 경우 하나 또는 여러 테마를 지정하여 설정에 이 키워드가 포함된 오퍼로 오퍼 수를 제한합니다.

   이 예제에서는 **여행** 카테고리에 두 개의 테마가 있는 두 개의 하위 카테고리가 포함되어 있습니다. **고객>1년** 테마를 사용하는 오퍼에 대한 시뮬레이션을 실행하려고 합니다.

   ![여행 카테고리의 테마 필드에 입력한 고객 > 1년 테마의 범위 섹션](assets/offer_simulation_example_007.png)

1. 타겟팅할 수신자를 선택합니다.

   ![대상 선택 필터 마법사에서 받는 사람 목록을 선택한 다음 빈번한 여행자 목록을 선택합니다](assets/offer_simulation_example_008.png)

1. 각 수신자에게 보낼 오퍼 수를 구성합니다.

   이 예에서 오퍼 엔진은 각 수신자에 대해 가중치가 가장 높은 3개의 오퍼를 선택합니다.

   ![제안 수가 3으로 설정된 범위 섹션 및 특별 오퍼 게재 목록의 대상 쿼리](assets/offer_simulation_example_009.png)

1. 설정을 저장한 다음 **[!UICONTROL Dashboard]** 탭에서 **[!UICONTROL Start]**&#x200B;을(를) 클릭하여 시뮬레이션을 실행하십시오.

   ![확인을 요청하는 대시보드 시작 시뮬레이션 대화 상자(확인 단추 강조 표시)에서](assets/offer_simulation_example_010.png)

1. 시뮬레이션이 완료되면 **[!UICONTROL Results]**&#x200B;에서 오퍼당 제안에 대한 자세한 분류를 참조하십시오.

   이 예에서 오퍼 엔진은 3개의 제안에 대한 오퍼 분류를 기반으로 합니다.

   ![오퍼별 제안 분류가 포함된 시뮬레이션 결과 탭: 모집단 크기 30, 제안 수 30](assets/offer_simulation_example_011.png)

1. 오퍼 엔진에서 선택한 오퍼 목록을 보려면 **[!UICONTROL Breakdown of offers by rank]**&#x200B;을(를) 표시하십시오.

   ![미국 여행 및 프랑스 검색에 대한 오퍼 순위표와 파이 차트가 포함된 순위별 오퍼 분석](assets/offer_simulation_example_012.png)

1. 필요한 경우 **[!UICONTROL Start simulation]**&#x200B;을(를) 클릭하여 범위 설정을 변경하고 시뮬레이션을 다시 실행할 수 있습니다.

   ![확인을 요청하는 대시보드 시작 시뮬레이션 대화 상자(확인 단추 강조 표시)에서](assets/offer_simulation_example_010.png)

1. 시뮬레이션 데이터를 저장하려면 보고서에서 사용할 수 있는 기록 또는 내보내기 기능을 사용합니다.

   ![내보내기 메뉴와 저장 아이콘이 강조 표시된 등급별 오퍼 분류 보고서](assets/offer_simulation_example_013.png)
