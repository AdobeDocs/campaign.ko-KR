---
title: 인스턴스 사용자 정의
description: 인스턴스를 사용자 지정하는 방법 알아보기
feature: Application Settings
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: c44fb2de4ed0e1661801313ae0430ba9d19542f0
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 7%

---

# 인스턴스 사용자 정의{#gs-ac-custom}

방법 알아보기 **Campaign 인스턴스 사용자 지정**.

>[!CAUTION]
>
>Adobe Campaign 사용자 지정은 전문가 사용자에게만 예약됩니다.

## 새 데이터 필드 및 스키마 만들기

Adobe Campaign에서는 데이터 스키마를 사용하여 다음을 수행합니다.

* 애플리케이션 내의 데이터 개체가 기본 데이터베이스 테이블에 연결되어 있는 방식을 정의합니다
* Campaign 애플리케이션 내에서 서로 다른 데이터 개체 간의 링크를 정의합니다
* 각 개체에 포함된 개별 필드를 정의하고 설명합니다

예를 들어 수신자 테이블(nms:recipient)과 같은 필드를 기존 테이블에 추가하려면 해당 스키마를 확장해야 합니다.

다음 두 가지 테이블 확장 모드를 사용할 수 있습니다.

* 인터페이스 사용, **새 필드** 보조

   ![](../assets/do-not-localize/book.png) Campaign에서 새 필드를 빠르게 추가하는 방법을 배웁니다 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic){target=&quot;_blank&quot;}

* 프로그래밍 방식으로, 스키마를 확장하여

   ![](../assets/do-not-localize/glass.png) 에서 기존 스키마를 확장하는 방법을 알아보십시오 [이 섹션](../dev/extend-schema.md).


Campaign 데이터베이스에서 새 테이블을 만들고 기본 제공 데이터 모델을 확장할 수도 있습니다.

Adobe Campaign(예: 계약 테이블)에 기본적으로 존재하지 않는 완전히 새로운 유형의 데이터를 추가하려면 사용자 지정 스키마를 직접 생성할 수 있습니다. 자세한 내용은 [이 예](../dev/create-schema.md#example--creating-a-contract-table).

**관련 항목**

![](../assets/do-not-localize/book.png) 의 스키마 에디션의 예 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic){target=&quot;_blank&quot;}

![](../assets/do-not-localize/book.png) 사용 사례: 필드를 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link){target=&quot;_blank&quot;}


## 입력 양식 수정

캠페인 입력 양식을 구현에 맞게 조정할 수 있습니다. XML 내용을 수정하여 양식 필드를 추가하거나 제거할 수 있습니다.

![](../assets/do-not-localize/glass.png) 기존 입력 양식을 수정하거나 새 양식을 만드는 방법을 알아봅니다. [이 섹션](../dev/forms.md).

## 대시보드 사용자 지정{#gs-custom-dashboards}

Adobe Campaign 인터페이스는 많은 웹 애플리케이션을 사용하여 수신자, 게재, 캠페인, 주식 등에 액세스하고, 관리하고, 상호 작용합니다. 인터페이스는 한 페이지만 있는 대시보드 형태로 표시됩니다.

기본 웹 응용 프로그램은 관리 > 구성 > 웹 응용 프로그램 노드에 저장됩니다.

![](../assets/do-not-localize/book.png) Campaign에서 개요 페이지를 만드는 방법을 알아봅니다 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application){target=&quot;_blank&quot;}


## 목록 사용자 지정 및 필터 만들기 {#gs-lists-and-filters}

### 대시보드에서 데이터 액세스

캠페인 목록에는 탐색 및 데이터 시각화를 용이하게 하기 위해 사전 정의된 필터가 포함되어 있습니다.

![](../assets/do-not-localize/book.png) 의 필터링 옵션에 대해 자세히 알아보십시오 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering){target=&quot;_blank&quot;}


### 탐색기에서 데이터에 액세스

Adobe Campaign 탐색기 트리에서 탐색하면 데이터베이스에 포함된 데이터가 목록에 표시됩니다. 이러한 목록을 필터링하고, 검색을 실행하고, 정보를 추가하고, 데이터를 필터링하고, 정렬할 수 있습니다.

![](../assets/do-not-localize/book.png) 목록 구성 및 목록 구성 저장 방법 알아보기 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started){target=&quot;_blank&quot;}


이러한 목록에 필터를 적용하여 연산자가 필요한 데이터만 표시할 수 있습니다. 그런 다음 필터링된 데이터에 대해 작업을 실행할 수 있습니다. 필터 구성을 사용하면 목록에서 데이터를 동적으로 선택할 수 있습니다. 데이터가 수정되면 필터링된 데이터가 업데이트됩니다.

![](../assets/do-not-localize/book.png) 에서 데이터를 필터링하는 방법 알아보기 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters){target=&quot;_blank&quot;}
