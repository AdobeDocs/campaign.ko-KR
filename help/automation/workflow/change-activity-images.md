---
product: campaign
title: 활동 이미지 변경
description: 활동 이미지를 변경하는 방법 알아보기
feature: Workflows
role: Admin
version: Campaign v8, Campaign Classic v7
exl-id: f5580401-3305-4915-88a2-3400a32aa7aa
TQID: 'https://experienceleague.adobe.com/9i-2gtfWr0ghkIif2S-ORoXk-hTlSMHgkeRAmMW0msg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 3%
---
# 활동 이미지 변경{#change-activity-images}



다양한 워크플로우의 다이어그램에 사용된 이미지를 변경할 수 있습니다. 그러나 특정 제한 사항을 준수해야 합니다. 다음은 구현 단계입니다.

* 배경 이미지를 변경하려면 원하는 타겟팅 워크플로우를 선택한 다음 **[!UICONTROL Properties]** 탭을 클릭합니다.

  ![](assets/s_user_segmentation_properties_tab.png)

  사용할 이미지를 선택하려면 **[!UICONTROL Background image]** 필드 오른쪽에 있는 **[!UICONTROL Select link]** 아이콘을 클릭합니다.

  >[!NOTE]
  >
  >배경 이미지의 너비(픽셀 단위)는 4의 배수여야 합니다.

  ![](assets/s_user_segmentation_background_select.png)

  **[!UICONTROL Edit link]** 아이콘을 사용하면 선택한 이미지를 볼 수 있습니다.

* 활동과 연결된 이미지를 변경하려면 개체를 두 번 클릭한 다음 **[!UICONTROL Advanced]** 탭을 클릭합니다.

  사용할 이미지를 선택하려면 **[!UICONTROL Image]** 필드 오른쪽에 있는 **[!UICONTROL Select link]** 아이콘을 클릭합니다.

  ![](assets/s_user_segmentation_activity_image.png)

  **[!UICONTROL Edit link]** 아이콘을 사용하면 선택한 이미지를 볼 수 있습니다.

  ![](assets/s_user_segmentation_activity_image_select.png)

>[!NOTE]
>
>트리의 **[!UICONTROL Administration > Configuration > Images]** 노드에 저장된 이미지를 선택할 수 있습니다.
>  
>이미지는 48x48 픽셀, 1,600만 색상 및 투명 배경이 있는 PNG 형식이어야 합니다.
