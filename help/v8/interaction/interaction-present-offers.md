---
product: campaign
title: 오퍼(인바운드 상호 작용) 제공
description: Campaign 상호 작용 모듈을 사용하여 최상의 오퍼를 제공하는 방법 알아보기
feature: Interaction, Offers
role: User, Admin
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 4%

---

# 최상의 오퍼 제공{#interaction-present-offers}

[인바운드 또는 아웃바운드 채널](interaction-architecture.md#interaction-types)을 사용하여 다양한 오퍼 공간에서 오퍼를 표시할 수 있습니다. 이 장에서는 인바운드 채널에 대한 몇 가지 특정 기능을 자세히 설명합니다.

![](assets/inbound-interactions.png)

오퍼 엔진에서 오퍼를 선택하려면 오퍼를 승인하고 라이브 환경에서 사용할 수 있어야 합니다.

자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html#approving-offer-content){target="_blank"}를 참조하세요.

인바운드 연락처의 컨텍스트에서 페이지를 탐색하는 사용자를 웹 사이트로 식별하거나 식별하지 못할 수 있습니다. 오퍼 엔진은 식별된 프로필과 익명 프로필에 대해 서로 다른 오퍼를 제공합니다.

인바운드 채널에 오퍼를 제공하기 전에 오퍼를 제공할 오퍼 엔진 호출을 구성해야 합니다. 대부분의 경우 인바운드 상호 작용의 경우 웹 페이지입니다.

>[!NOTE]
>
>인바운드 상호 작용의 경우 하나 이상의 오퍼를 제시하고 업데이트하도록 오퍼 엔진을 구체적으로 구성해야 합니다.
>
>또한 오퍼 공간에서 단일 모드를 활성화해야 합니다. 자세한 정보는 이 [페이지](interaction-offer-spaces.md)를 참조하십시오.
