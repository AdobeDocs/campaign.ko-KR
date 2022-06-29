---
title: Campaign을 CRM과 함께 작업
description: Campaign 및 CRM으로 작업하는 방법 알아보기
feature: Salesforce Integration, Microsoft Integration
role: Data Engineer
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 20%

---

# Campaign과 CRM 연결 {#gs-crm}

Adobe Campaign은 Adobe Campaign 플랫폼을 타사 시스템에 연결하는 다양한 CRM 커넥터를 제공합니다. 이러한 CRM 커넥터를 사용하면 연락처, 계정, 구매 등을 동기화할 수 있습니다. 또한 다양한 타사 및 비즈니스 애플리케이션과 사용자의 애플리케이션을 손쉽게 통합할 수 있습니다.

이러한 커넥터를 사용하면 빠르고 손쉽게 데이터를 통합할 수 있습니다. Adobe Campaign은 CRM에서 사용할 수 있는 테이블을 수집하고 선택하는 전용 도우미를 제공합니다. 이렇게 하면 시스템 전체에서 항상 데이터가 최신 상태로 유지되도록 양방향 동기화를 보장합니다.

주요 이점은 다음과 같습니다.

* 영업 및 마케팅 간의 일관된 메시지: crm과 Adobe Campaign 통합을 통해 두 시스템 모두 고객 통찰력과 이메일 마케팅 기록에 액세스할 수 있으므로 모든 메시지는 고객에게 동일한 일관된 메시지를 공유할 수 있습니다.

* 모든 잠재 고객 및 고객 데이터의 전체적인 파악: Adobe Campaign을 CRM과 통합하여 CRM 시스템 내에서 각 연락처의 이메일 마케팅 기록을 공유 및 액세스할 수 있습니다.

* 채널에서 CRM 데이터를 활성화합니다. Adobe Campaign에 동기화된 연락처 데이터를 사용하면 모바일 푸시, 인앱, 이메일 또는 DM을 포함한 Campaign을 사용하여 모든 온라인 또는 오프라인 채널에서 커뮤니케이션을 전송할 수 있습니다.


>[!NOTE]
>
>이 기능은 **CRM 커넥터** 전용 패키지

## 호환 시스템 {#compatible-crm-systems-and-limitations}

지원되는 CRM 및 버전은 Campaign에 자세히 설명되어 있습니다 [호환성 매트릭스](../start/compatibility-matrix.md).

>[!CAUTION]
>
> Campaign CRM 커넥터는 보안 URL(https)에서만 작동합니다.

## 구현 단계 {#crm-implementation-steps}

에서 Campaign과 Microsoft Dynamics를 연결하는 단계별 절차를 배웁니다. [이 페이지](ac-ms-dyn.md).

에서 Campaign 및 Salesforce.com을 연결하는 단계별 절차를 배웁니다. [이 페이지](ac-sfdc.md).

Adobe Campaign과 CRM 간의 데이터 동기화는 전용 워크플로우 활동을 통해 수행됩니다. 워크플로우를 빌드하여 Campaign과 CRM 간 동기화를 자동화합니다. Microsoft Dynamics를 통해 연락처를 가져오고, 기존 Adobe Campaign 데이터와 동기화하며, 중복 연락처를 삭제한 다음 Adobe Campaign 데이터베이스를 업데이트하는 워크플로우를 만들 수 있습니다. [이 페이지](crm-data-sync.md)에서 자세히 알아보십시오.
