---
title: 기본 수신자 테이블 변경
description: 사용자 지정 수신자 테이블을 사용하는 방법을 알아봅니다
feature: Custom Resources, Profiles, Configuration
role: User, Developer
level: Intermediate, Experienced
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 3%

---

# 사용자 정의 수신자 테이블 사용{#gs-ac-custom-recipient}

Adobe Campaign에는 **nmsRecipient**&#x200B;라는 기본 제공 프로필 테이블이 있습니다. 이 테이블에는 쉽게 확장할 수 있는 사전 정의된 필드와 테이블이 여러 개 있습니다. [이 페이지](datamodel.md#ootb-profiles)에서 이 테이블에 대해 자세히 알아보세요.

기본 제공 테이블 확장은 유연성을 제공하지만 일부 사용하지 않는 필드 또는 링크를 제거할 수 없습니다. 따라서 데이터 모델이 Campaign의 기본 제공 수신자 테이블 구조와 크게 다르거나 프로필이 많은 경우 사용자 지정 수신자 테이블을 사용하는 것이 좋습니다.  그러나 이 방법은 구현 시 특정 예방 조치가 필요합니다.

[Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html){target="_blank"}에서 사용자 지정 수신자 테이블을 사용하도록 인스턴스를 구성하는 방법을 알아봅니다.