---
solution: Campaign Classic
product: campaign
title: 기술 워크플로우 및 데이터 복제
description: 기술 워크플로우 및 데이터 복제
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
translation-type: tm+mt
source-git-commit: 9efd6442336a62e627b0da4e17fa742f59f715f9
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 1%

---

# 기술 워크플로우 및 데이터 복제

## 기술 워크플로우

Adobe Campaign에는 내장된 기술 워크플로우가 포함되어 있습니다. 기술 워크플로우는 정기적으로 서버에서 예약된 프로세스 또는 작업을 실행합니다.

이러한 워크플로우는 데이터베이스에서 유지 관리 작업을 수행하고 배달 로그의 추적 정보를 활용하며 반복되는 캠페인을 만드는 등 다양한 작업을 수행합니다.

:arrow_upper_right:기술 워크플로우의 전체 목록은 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=en#overview)에 자세히 설명되어 있습니다.

이러한 기술 워크플로우 외에도 Campaign v8은 특정 기술 워크플로우를 사용하여 [데이터 복제](#data-replication)를 관리합니다.

* **[!UICONTROL Replicate Reference tables]**
이 워크플로에서는 Campaign 로컬 데이터베이스(Postgres) 및 클라우드 데이터베이스(Snowflake)에 있어야 하는 참조 테이블의 자동 복제를 수행합니다. 매일 매시간 실행되도록 예약되어 있습니다. If 
**lastModifiedfield가** 존재하면 복제가 점진적으로 수행되고, 그렇지 않으면 전체 테이블이 복제됩니다. 아래 배열에서 표의 순서는 복제 작업 과정에서 사용되는 순서입니다.
* **[!UICONTROL Replicate Staging data]**
이 작업 과정은 단일 호출을 위한 스테이징 데이터를 복제합니다. 매일 매시간 실행되도록 예약되어 있습니다.
* **[!UICONTROL Deploy FFDA immediately]**\
   이 워크플로우는 클라우드 데이터베이스에 즉시 배포합니다.
* **[!UICONTROL Replicate FFDA data immediately]**
이 워크플로우는 지정된 외부 계정에 대해 XS 데이터를 복제합니다.

이러한 기술 워크플로우는 캠페인 탐색기의 **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** 노드에서 사용할 수 있습니다.

## 데이터 복제{#data-replication}

테이블은 위에서 설명한 전용 워크플로우를 통해 Campaign 데이터베이스에서 Snowflake 클라우드 데이터베이스로 복제됩니다.

복제 정책은 테이블 크기를 기반으로 합니다. 일부 테이블이 복제됩니다. 일부 테이블은 실시간으로 복제되며, 다른 테이블은 시간별로 복제됩니다. 일부 탈목은 다른 항목을 교체할 때 증분 업데이트를 갖게 됩니다.

**모든 테이블을 나열해야 합니까?**

확인하려면

**관련 항목**

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)에서 워크플로우를 시작하는 방법을 알아봅니다.

: 전구:[이 섹션](../dev/datamodel-best-practices.md#data-retention)의 데이터 보존 기간에 액세스
