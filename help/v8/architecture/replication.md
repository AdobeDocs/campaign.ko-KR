---
title: 기술 워크플로우 및 데이터 복제
description: 기술 워크플로우 및 데이터 복제
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 2%

---

# 기술 워크플로우 및 데이터 복제 {#wf-data-replication}

## 기술 워크플로 {#tech-wf}

[엔터프라이즈(FFDA) 배포](enterprise-deployment.md)의 컨텍스트에서 Adobe Campaign에는 기본 제공 기술 워크플로우 집합이 포함되어 있습니다. 기술 워크플로우는 서버에서 정기적으로 예약된 프로세스 또는 작업을 실행합니다.

이러한 워크플로우는 데이터베이스에서 유지 관리 작업을 수행하고, 게재 로그의 추적 정보를 활용하고, 반복 캠페인을 만드는 등의 작업을 수행합니다.

기술 워크플로우의 전체 목록은 [이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}에 자세히 설명되어 있습니다.

이러한 기술 워크플로우 외에도 Campaign v8은 [데이터 복제](#data-replication)를 관리하기 위해 특정 기술 워크플로우를 사용합니다.

* **[!UICONTROL Replicate Reference tables]**
이 워크플로는 Campaign 로컬 데이터베이스(Postgres) 및 클라우드 데이터베이스([!DNL Snowflake])에 있어야 하는 기본 제공 테이블의 자동 복제를 수행합니다. 매시간, 매일 실행되도록 예약되어 있습니다. **lastModified** 필드가 있으면 복제가 점진적으로 발생하고 그렇지 않으면 전체 테이블이 복제됩니다. 아래 배열에 있는 표의 순서는 복제 워크플로우에서 사용하는 순서입니다.
* **[!UICONTROL Replicate Staging data]**
이 워크플로우는 단일 호출에 대한 스테이징 데이터를 복제합니다. 매시간, 매일 실행되도록 예약되어 있습니다.
* **[!UICONTROL Deploy FFDA immediately]**\
  이 워크플로우는 클라우드 데이터베이스에 대한 즉각적인 배포를 수행합니다.
* **[!UICONTROL Replicate FFDA data immediately]**
이 워크플로우는 지정된 외부 계정에 대한 XS 데이터를 복제합니다.

이러한 기술 워크플로우는 Campaign 탐색기의 **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]** 노드에서 사용할 수 있습니다. **수정해서는 안 됩니다.**

필요한 경우 데이터 동기화를 수동으로 시작할 수 있습니다. 이 작업을 수행하려면 **스케줄러** 활동을 마우스 오른쪽 단추로 클릭하고 **지금 보류 중인 작업 실행**&#x200B;을 선택하십시오.

## 데이터 복제 {#data-replication}

일부 기본 제공 테이블은 위에서 설명한 전용 워크플로우를 통해 Campaign 로컬 데이터베이스에서 [!DNL Snowflake] 클라우드 데이터베이스로 복제됩니다.

Adobe Campaign v8에서 사용하는 데이터베이스, 데이터를 복제하는 이유, 복제하는 데이터 및 복제 프로세스의 작동 방식을 이해합니다.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### 데이터 복제 정책 {#data-replication-policies}

복제 정책은 표의 크기를 기반으로 합니다. 일부 테이블은 실시간으로 복제되고 다른 테이블은 시간별로 복제됩니다. 일부 테이블은 교체될 때 증분 업데이트가 있습니다.

기본 제공 **참조 테이블 복제** 기술 워크플로우 외에도 워크플로우에서 데이터 복제를 강제 적용할 수 있습니다.

다음을 수행할 수 있습니다.

* 다음 코드를 사용하여 특정 **Javascript 코드** 활동을 추가합니다.

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

* [워크플로우 시작 방법 알아보기](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=ko){target="_blank"}

* [데이터 보존 기간](../dev/datamodel-best-practices.md#data-retention)
