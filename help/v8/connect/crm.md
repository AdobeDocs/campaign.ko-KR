---
title: Campaign을 CRM과 함께 작업
description: Campaign 및 CRM으로 작업하는 방법 알아보기
feature: Overview
role: Data Engineer
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 25%

---

# Campaign과 CRM 연결 {#gs-crm}

Adobe Campaign은 Adobe Campaign 플랫폼을 타사 시스템에 연결하는 다양한 CRM 커넥터를 제공합니다. 이러한 CRM 커넥터를 사용하면 연락처, 계정, 구매 등을 동기화할 수 있습니다. 또한 다양한 타사 및 비즈니스 애플리케이션과 사용자의 애플리케이션을 손쉽게 통합할 수 있습니다.

이러한 커넥터를 사용하면 빠르고 손쉽게 데이터를 통합할 수 있습니다. Adobe Campaign은 CRM에서 사용할 수 있는 테이블을 수집하고 선택하는 전용 도우미를 제공합니다. 이렇게 하면 시스템 전체에서 항상 데이터가 최신 상태로 유지되도록 양방향 동기화를 보장합니다.

>[!NOTE]
>
>이 기능은 **CRM 커넥터** 전용 패키지

## 호환 시스템 {#compatible-crm-systems-and-limitations}

지원되는 CRM 및 버전은 Campaign에 자세히 설명되어 있습니다 [호환성 매트릭스](../start/compatibility-matrix.md).

![](../assets/do-not-localize/speech.png)  CRM 커넥터는 보안 URL(https)에서만 작동합니다.

## 구현 단계 {#crm-implementation-steps}

![](../assets/do-not-localize/book.png) 에서 Campaign과 Microsoft Dynamics를 연결하는 단계별 절차를 배웁니다. [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=en#microsoft-dynamics-implementation-steps)

![](../assets/do-not-localize/book.png) 에서 Campaign 및 Salesforce를 연결하는 단계별 절차를 배웁니다. [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=en#getting-started)


Adobe Campaign과 CRM 간의 데이터 동기화는 전용 워크플로우 활동을 통해 수행됩니다. 워크플로우를 빌드하여 Campaign과 CRM 간 동기화를 자동화합니다. Microsoft Dynamics를 통해 연락처를 가져오고, 기존 Adobe Campaign 데이터와 동기화하며, 중복 연락처를 삭제한 다음 Adobe Campaign 데이터베이스를 업데이트하는 워크플로우를 만들 수 있습니다.

![](../assets/do-not-localize/book.png) 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=en#getting-started)를 참조하세요
