---
title: Campaign 및 CRM을 사용한 작업
description: Campaign 및 CRM으로 작업하는 방법을 알아봅니다
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin, User
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 20%

---

# CRM을 Campaign과 연결 {#gs-crm}

Adobe Campaign은 Adobe Campaign 플랫폼을 타사 시스템에 연결하는 다양한 CRM 커넥터를 제공합니다. 이러한 CRM 커넥터를 사용하면 연락처, 계정, 구매 등을 동기화할 수 있습니다. 또한 다양한 타사 및 비즈니스 애플리케이션과 사용자의 애플리케이션을 손쉽게 통합할 수 있습니다.

이러한 커넥터를 사용하면 빠르고 간편하게 데이터를 통합할 수 있습니다. Adobe Campaign에서는 CRM에서 사용할 수 있는 테이블을 수집하고 선택하는 전용 도우미를 제공합니다. 이렇게 하면 시스템 전체에서 항상 데이터가 최신 상태로 유지되도록 양방향 동기화를 보장합니다.

주요 이점은 다음과 같습니다.

* 영업 및 마케팅 간의 일관된 메시징: CRM과 Adobe Campaign의 통합을 통해 두 시스템에서 고객 인사이트 액세스 및 이메일 마케팅 기록을 제공하여 모든 메시지를 고객에게 동일한 일관된 메시지를 공유할 수 있습니다.

* 모든 잠재 고객 및 고객 데이터에 대한 전체적인 보기: Adobe Campaign을 CRM과 통합하여 CRM 시스템 내에서 각 연락처의 이메일 마케팅 내역을 공유하고 액세스할 수 있습니다.

* 모든 채널에서 CRM 데이터 활성화: Adobe Campaign에 동기화된 연락처 데이터를 사용하여 모바일 푸시, 인앱, 이메일 또는 DM을 포함하여 Campaign을 사용하는 모든 온라인 또는 오프라인 채널에서 커뮤니케이션을 보낼 수 있습니다.


>[!NOTE]
>
>이 기능은 **CRM 커넥터** 전용 패키지를 통해 Adobe Campaign에서 사용할 수 있습니다.

## 호환 시스템 {#compatible-crm-systems-and-limitations}

지원되는 CRM 및 버전은 Campaign [호환성 매트릭스](../start/compatibility-matrix.md)에 자세히 설명되어 있습니다.

>[!CAUTION]
>
> Campaign CRM 커넥터는 보안 URL(https)에서만 작동합니다.

## 구현 단계 {#crm-implementation-steps}

[이 페이지](ac-ms-dyn.md)에서 Campaign과 Microsoft Dynamics를 연결하는 단계별 절차에 대해 알아봅니다.

[이 페이지](ac-sfdc.md)에서 Campaign과 Salesforce.com을 연결하는 단계별 절차에 대해 알아봅니다.

Adobe Campaign과 CRM 간의 데이터 동기화는 전용 워크플로우 활동을 통해 수행됩니다. 워크플로우를 빌드하여 Campaign과 CRM 간의 동기화를 자동화합니다. Microsoft Dynamics를 통해 연락처를 가져와 기존 Adobe Campaign 데이터와 동기화하고 중복 연락처를 삭제한 다음 Adobe Campaign 데이터베이스를 업데이트하는 워크플로우를 만들 수 있습니다. [이 페이지](crm-data-sync.md)에서 자세히 알아보십시오.
