---
title: 인스턴스 사용자 정의
description: 인스턴스 사용자 지정 방법 알아보기
feature: Configuration, Application Settings
role: Developer
level: Intermediate, Experienced
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 1%

---

# 인스턴스 사용자 정의 {#gs-ac-custom}

방법 알아보기 **Campaign 인스턴스 사용자 정의**.

>[!CAUTION]
>
>Adobe Campaign 사용자 지정은 전문가 사용자에게만 예약되어 있습니다.

## 새 데이터 필드 및 스키마 만들기

Adobe Campaign은 데이터 스키마를 사용하여 다음을 수행합니다.

* 응용 프로그램 내의 데이터 개체가 기본 데이터베이스 테이블에 연결되는 방식을 정의합니다.
* Campaign 애플리케이션 내에서 서로 다른 데이터 개체 간의 링크를 정의합니다.
* 각 개체에 포함된 개별 필드 정의 및 설명

예를 들어 수신자 테이블(nms:recipient)과 같은 기존 테이블에 필드를 추가하려면 해당 스키마를 확장해야 합니다.

두 가지 테이블 확장 모드를 사용할 수 있습니다.

* 인터페이스를 통해 **새 필드** 어시스턴트

  Campaign에서 새 필드를 빠르게 추가하는 방법 알아보기 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html#configuring-campaign-classic){target="_blank"}

* 프로그래밍 방식으로 스키마를 확장하여 에서 기존 스키마를 확장하는 방법 알아보기 [이 섹션](../dev/extend-schema.md).

Campaign 데이터베이스에서 새 테이블을 만들고 기본 제공 데이터 모델을 확장할 수도 있습니다.

Adobe Campaign에 즉시 존재하지 않는 완전히 새로운 유형의 데이터(예: 계약 테이블)를 추가하려면 사용자 지정 스키마를 직접 만들 수 있습니다. 자세한 내용은 다음을 참조하십시오. [이 예](../dev/create-schema.md#example--creating-a-contract-table).

**관련 항목**

의 스키마 에디션 예 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#configuring-campaign-classic){target="_blank"}

사용 사례:에서 기존 참조 테이블에 필드 연결 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#uc-link){target="_blank"}


## 입력 양식 수정

캠페인 입력 양식을 구현에 맞게 조정할 수 있습니다. XML 내용을 수정하여 양식 필드를 추가하거나 제거할 수 있습니다.

에서 기존 입력 양식을 수정하거나 새 양식을 만드는 방법을 알아봅니다. [이 섹션](../dev/forms.md).

## 대시보드 맞춤화{#gs-custom-dashboards}

Adobe Campaign 인터페이스는 많은 웹 애플리케이션을 사용하여 수신자, 게재, 캠페인, 주식 등에 액세스하고 관리하며 상호 작용합니다. 이러한 화면은 페이지가 한 개만 있는 대시보드 형태로 인터페이스에 표시됩니다.

기본 제공 웹 응용 프로그램은 **관리 > 구성 > 웹 애플리케이션** 탐색기의 폴더입니다.

의 Campaign에서 개요 페이지를 만드는 방법을 알아봅니다. [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html#creating-a-single-page-web-application){target="_blank"}


## 목록 사용자 지정 및 필터 만들기 {#gs-lists-and-filters}

캠페인 목록에는 탐색 및 데이터 시각화를 용이하게 하는 사전 정의된 필터가 제공됩니다.

Adobe Campaign 탐색기 트리에서 탐색하면 데이터베이스에 포함된 데이터가 목록에 표시됩니다. 이러한 목록을 필터링하고, 검색을 실행하고, 정보를 추가하고, 데이터를 필터링하고 정렬할 수 있습니다.

에서 목록을 구성하고 목록 구성을 저장하는 방법을 알아봅니다. [이 페이지](../start/campaign-ui.md).

이러한 목록에 필터를 적용하여 연산자에 필요한 데이터만 표시할 수 있습니다. 그런 다음 필터링된 데이터에 대해 작업을 실행할 수 있습니다. 필터 구성을 사용하면 목록에서 데이터를 동적으로 선택할 수 있습니다. 데이터가 수정되면 필터링된 데이터가 업데이트됩니다.

에서 필터링 옵션에 대해 자세히 알아봅니다. [이 페이지](../audiences/create-filters.md).
