---
product: Adobe Campaign
title: 기술 워크플로우 및 데이터 복제
description: 기술 워크플로우 및 데이터 복제
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 2%

---

# 기술 워크플로우 및 데이터 복제

## 기술 워크플로우{#tech-wf}

Adobe Campaign에는 내장된 기술 워크플로우가 포함되어 있습니다. 기술 워크플로우는 서버에서 정기적으로 예약된 프로세스 또는 작업을 실행합니다.

이러한 워크플로우는 데이터베이스에서 유지 관리 작업을 수행하고, 게재 로그에서 추적 정보를 활용하고, 반복 캠페인을 만드는 등의 작업을 수행합니다.

[!DNL :arrow_upper_right:] 기술 워크플로우의 전체 목록은  [Campaign Classic v7 설명서에 자세히 설명되어 있습니다](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)


이러한 기술 워크플로우 외에도 Campaign v8은 [데이터 복제](#data-replication)를 관리하는 특정 기술 워크플로우를 사용합니다.

* **[!UICONTROL Replicate Reference tables]**
이 워크플로우에서는 Campaign 로컬 데이터베이스(Postgres) 및 클라우드 데이터베이스([!DNL Snowflake])에 있어야 하는 기본 제공 테이블을 자동으로 복제합니다. 매시간 매일 실행되도록 예약되어 있습니다. **lastModified** 필드가 있으면 복제가 증분 발생하며, 그렇지 않으면 전체 테이블이 복제됩니다. 아래 배열에 있는 표의 순서는 복제 워크플로우에서 사용하는 순서입니다.
* **[!UICONTROL Replicate Staging data]**
이 워크플로우는 단일 호출에 대한 스테이징 데이터를 복제합니다. 매시간 매일 실행되도록 예약되어 있습니다.
* **[!UICONTROL Deploy FFDA immediately]**\
   이 워크플로우는 클라우드 데이터베이스에 즉시 배포를 수행합니다.
* **[!UICONTROL Replicate FFDA data immediately]**
이 워크플로우는 지정된 외부 계정에 대해 XS 데이터를 복제합니다.

이러한 기술 워크플로우는 Campaign Explorer의 **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** 노드에서 사용할 수 있습니다. **이를 수정해서는 안 됩니다.**

필요한 경우 데이터 동기화를 수동으로 시작할 수 있습니다. 이렇게 하려면 **스케줄러** 활동을 마우스 오른쪽 단추로 클릭하고 **지금 보류 중인 작업 실행**&#x200B;을 선택합니다.

## 데이터 복제{#data-replication}

기본 제공 테이블 중 일부는 위에 설명된 전용 워크플로우를 통해 Campaign 로컬 데이터베이스에서 [!DNL Snowflake] 클라우드 데이터베이스로 복제됩니다.

복제 정책은 테이블 크기를 기반으로 합니다. 일부 테이블은 실시간으로 복제되고 다른 테이블은 시간별로 복제됩니다. 일부 테이블은 다른 테이블을 교체하면 증분 업데이트가 있습니다.

기본 제공 **참조 테이블 복제** 기술 워크플로우 외에도 워크플로우에서 데이터 복제를 강제 수행할 수 있습니다.

다음을 수행할 수 있습니다.

* 다음 코드와 함께 특정 **Javascript 코드** 활동을 추가합니다.

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* 다음 명령을 사용하여 특정 **nlmodule** 활동을 추가합니다.

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)

**관련 항목**

[!DNL :arrow_upper_right:]  [Campaign Classic v7 설명서에서 워크플로우를 시작하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)

[!DNL :bulb:] 이 섹션에서 데이터 보존 기간 [에 액세스합니다](../dev/datamodel-best-practices.md#data-retention)
