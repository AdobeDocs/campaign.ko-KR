---
solution: Campaign Classic
product: campaign
title: 인스턴스 사용자 정의
description: 인스턴스를 사용자 정의하는 방법 학습
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
translation-type: tm+mt
source-git-commit: 805deadf994e2c4fdfb850ea5b1c3dedf565ef2d
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 6%

---

# 인스턴스 사용자 지정{#gs-ac-custom}

**캠페인 인스턴스 사용자 지정 방법**

>[!CAUTION]
>
>Adobe Campaign 맞춤화는 전문가 사용자에게만 제공됩니다.

## 새 데이터 필드 및 스키마 만들기

Adobe Campaign은 데이터 스키마를 사용하여 다음을 수행합니다.

* 애플리케이션 내의 데이터 개체가 기본 데이터베이스 테이블에 연결되어 있는 방식을 정의합니다
* Campaign 애플리케이션 내에서 서로 다른 데이터 개체 간의 링크를 정의합니다
* 각 개체에 포함된 개별 필드를 정의하고 설명합니다

받는 사람 테이블(nms:recipient)과 같은 필드를 기존 테이블에 추가할 수 있으므로 해당 스키마를 확장해야 합니다.

두 개의 표 확장 모드를 사용할 수 있습니다.

* 인터페이스를 통해 **새 필드** 도우미를 사용합니다.

   :arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic)에서 Campaign에서 새 필드를 빠르게 추가하는 방법을 알아봅니다.

* 프로그래밍 방식으로, 스키마 확장

   : 전구:[이 섹션](../dev/extend-schema.md)에서 기존 스키마를 확장하는 방법을 알아봅니다.


Campaign 데이터베이스에서 새 테이블을 만들고 내장 데이터 모델을 확장할 수 있습니다.

Adobe Campaign에 기본적으로 존재하지 않는 완전히 새로운 유형의 데이터(예: 계약서 표)를 추가하려면 사용자 정의 스키마를 직접 만들 수 있습니다. 자세한 내용은 [이 예제](../dev/create-schema.md#example--creating-a-contract-table)를 참조하십시오.

**관련 항목**

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic)의 스키마 에디션의 예

:arrow_upper_right:사용 사례:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link)의 기존 참조 테이블에 필드를 연결합니다.


## 입력 양식 수정

캠페인 입력 양식을 구현에 맞게 조정할 수 있습니다. XML 내용을 수정하여 필드를 추가하거나 제거할 수 있습니다.

: 전구:기존 입력 양식을 수정하거나 [이 섹션](../dev/forms.md)에서 새 양식을 만드는 방법에 대해 알아봅니다.

## 대시보드 사용자 지정{#gs-custom-dashboards}

Adobe Campaign 인터페이스는 많은 웹 애플리케이션을 사용하여 수신자, 전달, 캠페인, 주식 등에 액세스하고 이를 관리하고 상호 작용할 수 있도록 합니다. 인터페이스에서는 한 페이지만 있는 대시보드 형태로 표시됩니다.

즉시 사용 가능한 웹 응용 프로그램은 관리 > 구성 > 웹 응용 프로그램 노드에 저장됩니다.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application)에서 Campaign에서 개요 페이지를 만드는 방법을 알아봅니다.


## 목록을 사용자 정의하고 필터 {#gs-lists-and-filters} 만들기

### 대시보드에서 데이터 액세스

캠페인 목록에는 탐색 및 데이터 시각화를 용이하게 해주는 사전 정의된 필터가 포함되어 있습니다.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering)의 필터링 옵션에 대한 자세한 내용


### 탐색기에서 데이터에 액세스

Adobe Campaign 탐색기 트리에서 탐색할 때 데이터베이스에 포함된 데이터가 목록에 표시됩니다. 이러한 목록을 필터링하고, 검색을 실행하고, 정보를 추가하고, 데이터를 필터링하고 정렬할 수 있습니다.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started)에서 목록을 구성하고 목록 구성을 저장하는 방법을 알아봅니다.


이러한 목록에 필터를 적용하여 연산자가 필요한 데이터만 표시할 수 있습니다. 그런 다음 필터링된 데이터에 대해 작업을 실행할 수 있습니다. 필터 구성을 사용하면 목록에서 데이터를 동적으로 선택할 수 있습니다. 데이터가 수정되면 필터링된 데이터가 업데이트됩니다.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters)에서 데이터를 필터링하는 방법에 대해 알아봅니다.
