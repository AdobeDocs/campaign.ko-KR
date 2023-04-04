---
product: campaign
title: 마케팅 캠페인 자산, 문서 및 게재 개요
description: 마케팅 캠페인 문서 및 게재 개요에 대해 자세히 알아보십시오
feature: Campaigns
exl-id: 352f6cd5-777d-413d-af79-6f53444b336f
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 0%

---

# 자산 및 문서 관리 {#manage-assets-documents}

다양한 문서를 캠페인과 연결할 수 있습니다. 보고서, 사진, 웹 페이지, 다이어그램 등 이러한 문서는 어떤 형식으로든 사용할 수 있습니다.

캠페인에서 프로모션 쿠폰, 특정 브랜드 또는 스토어와 관련된 특별 오퍼 등과 같은 다른 항목을 참조할 수도 있습니다. 이러한 요소가 아웃라인에 포함되면 DM 게재와 연결될 수 있습니다. [자세히 알아보기](#associating-and-structuring-resources-linked-via-a-delivery-outline)


>[!CAUTION]
>
>이 기능은 작은 자산과 문서를 위해 설계되었습니다.

<!--
>[!NOTE]
>
>If you are using Campaign Marketing Resource Management module, you can also manage a library of marketing resources that are available for several users for collaborative work. [Learn more](../../mrm/using/managing-marketing-resources.md).
-->

## 문서 추가 {#add-documents}

문서는 캠페인 수준(상황별 문서) 또는 프로그램 수준(일반 문서)에서 연결할 수 있습니다.

캠페인의 경우, **[!UICONTROL Documents]** 에는 다음이 포함되어 있습니다.

* 컨텐츠에 필요한 모든 문서 목록(템플릿, 이미지 등) 적절한 권한이 있는 Adobe Campaign 운영자가 로컬로 다운로드할 수 있습니다.
* 라우터에 대한 정보가 들어 있는 문서(있는 경우)

문서는 **[!UICONTROL Edit > Documents]** 탭.

![](assets/op_add_document.png)

대시보드의 전용 링크에서 캠페인에 문서를 추가할 수도 있습니다.

![](assets/add_a_document_in_op.png)

을(를) 클릭합니다. **[!UICONTROL Detail...]** 아이콘 을 클릭하여 파일의 컨텐츠를 보고 정보를 추가합니다.

![](assets/add_document_details.png)

대시보드에서 캠페인과 연관된 문서는 **[!UICONTROL Document(s)]** 섹션을 참조하십시오.

![](assets/edit_documents.png)

이 보기에서 편집하고 수정할 수도 있습니다.

## 게재 개요 사용 {#delivery-outlines}

게재 아웃라인은 구성 요소 세트(문서, 스토어, 프로모션 쿠폰 등)입니다. 회사 및 특정 캠페인에 의해 만들어집니다. DM 게재 컨텍스트에서 사용됩니다.

이러한 요소는 게재 아웃라인에서 그룹화되며, 각 게재 아웃라인은 게재와 연결됩니다. 로 보낸 추출 파일에서 참조됩니다. **서비스 공급자** 배달물에 첨부하기 위해. 예를 들어 단위 및 해당 장치에서 사용하는 마케팅 브로셔를 참조하는 게재 아웃라인을 만들 수 있습니다.

캠페인의 경우, 게재 개요를 사용하면 특정 기준에 따라 게재와 연결할 외부 요소를 구성할 수 있습니다. 관련 단위, 프로모션 오퍼 부여됨, 로컬 이벤트 초대 등

>[!CAUTION]
>
>게재 아웃라인은 DM 캠페인으로 제한됩니다.

### 게재 개요 만들기 {#create-an-outline}

게재 개요를 만들려면 **[!UICONTROL Delivery outlines]** 의 하위 탭 **[!UICONTROL Edit > Documents]** 관련 캠페인의 탭.

![](assets/add-a-delivery-outline.png)


>[!NOTE]
>
>이 탭이 표시되지 않으면 이 캠페인에 이 기능을 사용할 수 없거나 인스턴스에서 DM 전달이 활성화되지 않습니다. 자세한 내용은 [캠페인 템플릿 구성](marketing-campaign-templates.md#campaign-templates) 또는 라이센스 계약에 따라 다릅니다.

다음을 클릭합니다. **[!UICONTROL Add a delivery outline]** 캠페인에 대한 아웃라인 계층 구조를 만듭니다.

1. 트리의 루트를 마우스 오른쪽 단추로 클릭하고 를 선택합니다 **[!UICONTROL New > Delivery outlines]**.
1. 방금 만든 아웃라인을 마우스 오른쪽 버튼으로 클릭하고 를 선택합니다 **[!UICONTROL New > Item]** 또는 **[!UICONTROL New > Personalization fields]**.

![](assets/del-outline-add-new-item.png)

아웃라인에는 항목, 개인화 필드 및 오퍼가 포함될 수 있습니다.

* 항목은 여기에서 참조하고 설명되는 물리적 문서 등 게재에 첨부할 수 있습니다.
* 개인화 필드를 사용하면 수신자가 아닌 게재와 관련된 개인화 요소를 만들 수 있습니다. 따라서 특정 타겟(환영 오퍼, 할인 등)에 대한 게재 시 사용할 값을 만들 수 있습니다. Adobe Campaign에서 작성하여 를 통해 아웃라인으로 가져옵니다 **[!UICONTROL Import personalization fields...]** 링크를 클릭합니다.

   ![](assets/del-outline-perso-field.png)

   를 클릭하여 아웃라인에서 직접 만들 수도 있습니다 **[!UICONTROL Add]** 목록 영역의 오른쪽에 있는 아이콘을 클릭합니다.

   ![](assets/add-del-outline-button.png)


### 아웃라인 선택 {#select-an-outline}

각 게재에 대해 다음 예와 같이 추출 아웃라인에 예약된 섹션에서 연결할 아웃라인을 선택할 수 있습니다.

![](assets/select-delivery-outline.png)

선택한 아웃라인이 창의 아래 섹션에 표시됩니다. 필드 오른쪽의 아이콘을 사용하여 편집하거나 드롭다운 목록을 사용하여 변경할 수 있습니다.

![](assets/delivery-outline-selected.png)

다음 **[!UICONTROL Summary]** 게재 탭에는 다음 정보도 표시됩니다.

![](assets/delivery-outline-in-dashboard.png)

### 추출 결과 {#extraction-result}

추출하여 서비스 제공업체에 보내는 파일에서 아웃라인의 이름과 적절한 경우 해당 특성(비용, 설명 등)은 은 서비스 공급자와 연관된 내보내기 템플릿의 정보에 따라 컨텐츠에 추가됩니다.

다음 예에서는 게재와 연관된 아웃라인의 레이블, 예상 비용 및 설명이 추출 파일에 추가됩니다.

![](assets/campaign-export-template.png)

내보내기 모델은 해당 게재에 대해 선택한 서비스 공급자와 연결되어 있어야 합니다. [이 섹션](providers--stocks-and-budgets.md#creating-service-providers-and-their-cost-structures)을 참조하십시오.
