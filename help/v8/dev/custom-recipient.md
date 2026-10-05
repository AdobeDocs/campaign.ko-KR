---
title: 기본 수신자 테이블 변경
description: 사용자 지정 수신자 테이블을 사용하는 방법을 알아봅니다
feature: Custom Resources, Profiles, Configuration
role: User, Developer
level: Intermediate, Experienced
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
TQID: 'https://experienceleague.adobe.com/W67Z2xVEBDpju5xlL2WiE5ZTzvrFmhuByMvfPb4x6nM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: a2002dba-5e37-4dff-8e04-1cc3ec73558c
    internal-label: Custom resources
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
  - id: a14877cc-63b1-41d9-bf0b-5f97cadd0417
    internal-label: Configuration guidelines
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 3%
---
# 사용자 정의 수신자 테이블 사용{#gs-ac-custom-recipient}

Adobe Campaign에는 **nmsRecipient**&#x200B;라는 기본 제공 프로필 테이블이 있습니다. 이 테이블에는 쉽게 확장할 수 있는 사전 정의된 필드와 테이블이 여러 개 있습니다. [이 페이지](datamodel.md#ootb-profiles)에서 이 테이블에 대해 자세히 알아보세요.

기본 제공 테이블 확장은 유연성을 제공하지만 일부 사용하지 않는 필드 또는 링크를 제거할 수 없습니다. 따라서 데이터 모델이 Campaign의 기본 제공 수신자 테이블 구조와 크게 다르거나 프로필이 많은 경우 사용자 지정 수신자 테이블을 사용하는 것이 좋습니다.  그러나 이 방법은 구현 시 특정 예방 조치가 필요합니다.

[Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html){target="_blank"}에서 사용자 지정 수신자 테이블을 사용하도록 인스턴스를 구성하는 방법을 알아봅니다.