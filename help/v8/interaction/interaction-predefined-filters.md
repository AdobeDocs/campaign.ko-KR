---
title: 캠페인 상호 작용 오퍼 사전 정의 필터
description: 사전 정의된 필터를 만드는 방법 알아보기
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 092262c7-768c-4e86-9b2b-c52516f6a030
TQID: 'https://experienceleague.adobe.com/XWkWbgrMASz-9FfrXC23tTwiw54oQH5U4iWM9fa2FDQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 4%
---
# 사전 정의 필터 만들기{#creating-pre-defined-filters}

사전 정의된 필터를 만들어 오퍼 생성 중 쉽게 다시 사용할 수 있는 대상 모집단의 자격 규칙을 정의합니다. 각 환경에 따라 다르며 오퍼 매개 변수를 고려합니다.

>[!NOTE]
>
>Adobe Campaign Web UI는 특정 요구 사항에 맞게 사전 정의된 필터를 손쉽게 관리하고 사용자 정의할 수 있는 사용자 친화적인 인터페이스를 제공합니다. 한 번 만들고 나중에 사용할 수 있도록 저장하십시오. 웹 UI용 사전 정의된 필터에 대한 자세한 내용은 [Adobe Campaign 웹 UI 설명서](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/predefined-filters){target=_blank}를 참조하세요.


사전 정의된 필터를 만들려면 다음 프로세스를 적용합니다.

1. **[!UICONTROL Administration]** 폴더를 찾은 다음 **[!UICONTROL Pre-defined offer filters]**&#x200B;을(를) 선택합니다.

   ![오퍼 - 관리에서 미리 정의된 오퍼 필터 노드가 선택된 트리 디자인](assets/offer_filter_create_005.png)

1. **[!UICONTROL New]**&#x200B;을(를) 클릭합니다.

   ![새 단추가 강조 표시되고 연령 필터가 나열된 사전 정의된 오퍼 필터 목록](assets/offer_filter_create_001.png)

1. 나중에 필터를 식별할 수 있도록 레이블을 변경합니다.

   레이블 필드가 전자 메일 채널로 설정된 ![응용 프로그램 필터 대화 상자](assets/offer_filter_create_002.png)

1. 필터링 조건과 관련된 필드를 선택합니다.

   ![받는 사람 필드에서 선택한 전자 메일 필드가 있는 식 대화 상자 선택](assets/offer_filter_create_003.png)

1. 필요한 경우 연산자 및 값을 선택한 다음 쿼리를 저장합니다.

   ![연산자가 로 설정된 전자 메일 식의 필터 조건이 비어 있지 않습니다](assets/offer_filter_create_004.png)

1. 필터 결과를 보려면 **[!UICONTROL Preview]**&#x200B;을(를) 클릭하십시오.

   ![필터와 일치하는 수신자를 나열하는 전자 메일 채널 필터의 미리 보기 탭](assets/offer_filter_create_006.png)
