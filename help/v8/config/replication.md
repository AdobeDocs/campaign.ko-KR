---
title: 기술 워크플로우 및 데이터 복제
description: 기술 워크플로우 및 데이터 복제
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: e55a60ae1628e534e32e86d347457b6c208db75b
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 2%

---

# 기술 워크플로우 및 데이터 복제

## 기술 워크플로우{#tech-wf}

Adobe Campaign에는 내장된 기술 워크플로우가 포함되어 있습니다. 기술 워크플로우는 서버에서 정기적으로 예약된 프로세스 또는 작업을 실행합니다.

이러한 워크플로우는 데이터베이스에서 유지 관리 작업을 수행하고, 게재 로그에서 추적 정보를 활용하고, 반복 캠페인을 만드는 등의 작업을 수행합니다.

![](../assets/do-not-localize/book.png) 기술 워크플로우의 전체 목록은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html){target=&quot;_blank&quot;}


Campaign v8은 이러한 기술 워크플로우 외에도 특정 기술 워크플로우를 활용하여 관리합니다 [데이터 복제](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
이 워크플로우에서는 Campaign 로컬 데이터베이스(Postgres) 및 클라우드 데이터베이스( )에 있어야 하는 기본 제공 테이블을 자동으로 복제합니다[!DNL Snowflake]). 매시간 매일 실행되도록 예약되어 있습니다. If **lastModified** 필드가 존재하면 복제가 점진적으로 수행되며, 그렇지 않으면 전체 테이블이 복제됩니다. 아래 배열에 있는 표의 순서는 복제 워크플로우에서 사용하는 순서입니다.
* **[!UICONTROL Replicate Staging data]**
이 워크플로우는 단일 호출에 대한 스테이징 데이터를 복제합니다. 매시간 매일 실행되도록 예약되어 있습니다.
* **[!UICONTROL Deploy FFDA immediately]**\
   이 워크플로우는 클라우드 데이터베이스에 즉시 배포를 수행합니다.
* **[!UICONTROL Replicate FFDA data immediately]**
이 워크플로우는 지정된 외부 계정에 대해 XS 데이터를 복제합니다.

이러한 기술 워크플로우는 **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** campaign Explorer 노드 아래에 있습니다. **이를 수정해서는 안 됩니다.**

필요한 경우 데이터 동기화를 수동으로 시작할 수 있습니다. 이렇게 하려면 **스케줄러** 활동 및 선택 **지금 보류 중인 작업 실행**.

## 데이터 복제{#data-replication}

기본 제공 테이블 중 일부는 Campaign 로컬 데이터베이스에서 로 복제됩니다 [!DNL Snowflake] 위에 설명된 전용 워크플로우를 통해 클라우드 데이터베이스

Adobe Campaign v8에서 사용하는 데이터베이스, 데이터가 복제되는 이유, 복제되는 데이터 및 복제 프로세스 작동 방식을 이해합니다.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### 데이터 복제 정책

복제 정책은 테이블 크기를 기반으로 합니다. 일부 테이블은 실시간으로 복제되고, 다른 테이블은 시간별로 복제됩니다. 일부 테이블은 다른 테이블을 교체하면 증분 업데이트가 있습니다.

기본 제공 외에 **참조 테이블 복제** 기술 워크플로우에서는 워크플로우에서 데이터 복제를 강제 수행할 수 있습니다.

다음을 수행할 수 있습니다.

* 특정 **Javascript 코드** 활동은 다음 코드를 가지고 있습니다.

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* 특정 **nlmodule** 다음 명령을 사용하여 활동을 수행합니다.

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)



**관련 항목**

![](../assets/do-not-localize/book.png) 에서 워크플로우를 시작하는 방법을 알아봅니다 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows){target=&quot;_blank&quot;}

![](../assets/do-not-localize/glass.png) 에서 데이터 보존 기간에 액세스 [이 섹션](../dev/datamodel-best-practices.md#data-retention)
