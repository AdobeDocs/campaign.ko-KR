---
title: 데이터 복제
description: 기술 워크플로우 및 데이터 복제
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: b8f774ce507cff67163064b6bd1341b31512c08f
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 2%

---


# 데이터 복제 {#wf-data-replication}

## 원칙

[엔터프라이즈(FFDA) 배포](enterprise-deployment.md)의 컨텍스트에서 데이터 복제는 Campaign 로컬 데이터베이스(PostgreSQL)와 클라우드 데이터베이스([!DNL Snowflake])의 두 데이터베이스가 동시에 작동하며 실시간으로 동기화된 상태를 유지하도록 합니다.

클라우드 데이터베이스([!DNL Snowflake])는 1백만 개의 주소 업데이트와 같은 대용량 데이터 일괄 처리를 처리하도록 최적화되었습니다. 한편, Campaign 로컬 데이터베이스(PostgreSQL)는 단일 시드 주소 업데이트와 같은 개별 또는 소규모 볼륨 작업에 더 적합합니다. 동기화는 백그라운드에서 자동으로 투명하게 수행되므로 Campaign 로컬 데이터베이스(PostgreSQL)의 데이터가 클라우드 데이터베이스([!DNL Snowflake])에 실시간으로 복제되어 두 데이터베이스가 모두 동기화됩니다. 데이터 동기화에는 스키마 및 테이블과 데이터가 포함됩니다.

➡️[비디오에서 데이터 복제가 작동하는 방식 알아보기](#video)

## 복제 모드 {#modes}

데이터 복제는 사용 사례에 따라 다른 모드에서 발생할 수 있다.

* **실시간 복제**&#x200B;는 실시간 복제가 필요한 경우를 처리합니다. 특정 기술 스레드에 의존하여 확산 생성이나 시드 주소 업데이트와 같은 사용 사례에 대해 데이터를 즉시 복제합니다.
* 즉시 동기화가 필요하지 않은 경우 **예약된 복제**&#x200B;이(가) 사용됩니다. 예약된 복제는 유형화 규칙과 같은 데이터를 동기화하기 위해 매 시간마다 실행되는 특정 [기술 워크플로우](#workflows)를 사용합니다.

## 복제 정책

복제 정책은 Campaign 로컬 데이터베이스(PostgreSQL) 테이블에서 복제되는 데이터의 양을 정의합니다. 이러한 정책은 표의 크기와 특정 사용 사례에 따라 다릅니다. 일부 테이블은 완전히 복제될 때 증분 업데이트가 있습니다. 복제 정책에는 다음과 같은 세 가지 주요 유형이 있습니다.

* **XS**: 이 정책은 크기가 비교적 작은 테이블에 사용됩니다. 전체 테이블이 한 번에 복제됩니다. 증분 복제는 타임스탬프 포인터를 사용하여 최근 변경 사항만 복제함으로써 동일한 데이터를 반복적으로 복제하는 것을 방지합니다.
* **SingleRow**: 이 정책은 한 번에 한 행만 복제합니다. 일반적으로 현재 Campaign 개체 및 관련 개체와 관련된 실시간 복제에 사용됩니다.
* **일부 행**: 이 정책은 쿼리 정의 또는 필터를 사용하여 제한된 데이터 하위 집합을 복제하도록 설계되었습니다. 선택적 복제가 필요한 더 큰 테이블에 사용됩니다.

## 복제 워크플로 {#workflows}

Campaign v8은 특정 기술 워크플로우를 통해 예약된 데이터 복제를 관리합니다. 이러한 기술 워크플로우는 Campaign 탐색기의 **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]** 노드에서 사용할 수 있습니다. **수정해서는 안 됩니다.**

기술 워크플로우는 서버에서 정기적으로 예약된 프로세스 또는 작업을 실행합니다. 기술 워크플로우의 전체 목록은 [이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=ko){target="_blank"}에 자세히 설명되어 있습니다.

데이터 복제를 보장하는 기술 워크플로우는 다음과 같습니다.

| 기술 워크플로 | 설명 |
|------|-----------|
| **[!UICONTROL Replicate Reference tables]**(ffdaReplicateReferenceTables) | Campaign 로컬 데이터베이스(PostgreSQL) 및 클라우드 데이터베이스([!DNL Snowflake])에 있어야 하는 기본 제공 테이블의 자동 복제를 수행합니다. 매시간, 매일 실행되도록 예약되어 있습니다. **lastModified** 필드가 있으면 복제가 점진적으로 발생하고 그렇지 않으면 전체 테이블이 복제됩니다. |
| **[!UICONTROL Replicate Staging data]**(ffdaReplicateStagingData) | 단일 호출에 대한 스테이징 데이터를 복제합니다. 매시간, 매일 실행되도록 예약되어 있습니다. |
| **[!UICONTROL Deploy FFDA immediately]**(ffdaDeploy) | 클라우드 데이터베이스에 대한 즉각적인 배포를 수행합니다. |
| **[!UICONTROL Replicate FFDA data immediately]**(ffdaReplicate) | 지정된 외부 계정에 대한 XS 데이터를 복제합니다. |

필요한 경우 데이터 동기화를 수동으로 시작할 수 있습니다. 이렇게 하려면 **스케줄러** 활동을 마우스 오른쪽 단추로 클릭하고 **지금 보류 중인 작업 실행**&#x200B;을 선택합니다.

기본 제공 **참조 테이블 복제** 기술 워크플로우 외에 다음 방법 중 하나를 사용하여 워크플로우에서 데이터 복제를 강제 적용할 수 있습니다

+++데이터 복제 강제 수행 방법

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

+++

<br/>

>[!NOTE]
>
>즉석 복제는 워크플로가 아닌 특정 기술 스레드에서 처리됩니다. 이 모드의 구성은 serverConf.xml 파일에서 관리됩니다. XS 테이블을 전체가 아닌 증분 복제하도록 요청하는 것과 같은 특정 사용 사례에 맞게 serverConf.xml을 구성할 수 있습니다. 자세한 내용은 Adobe 담당자에게 문의하세요.

## API

API를 사용하면 Campaign 로컬 데이터베이스(PostgreSQL)에서 클라우드 데이터베이스([!DNL Snowflake])로 사용자 지정 데이터와 기본 제공 데이터를 모두 복제할 수 있습니다. 이러한 API를 사용하면 사전 정의된 워크플로를 무시하고 사용자 지정 테이블을 복제하는 것과 같은 특정 요구 사항에 맞게 복제를 사용자 지정할 수 있습니다.

예:

```
var dataSource = "nms:extAccount:ffda";
var xml = xtk.builder.CopyXxlData(
    <params dataSource={dataSource} policy="xs">
        <srcSchema name="cus:recipient"/>
    </params>
);
```

## 복제 큐

대량의 복제 요청이 동시에 발생하면 MERGE 작업 중 테이블 수준 잠금으로 인해 클라우드 데이터베이스([!DNL Snowflake])에 성능 문제가 발생할 수 있습니다. 이를 완화하기 위해 중앙 집중식 복제 워크플로는 요청을 대기열로 그룹화합니다.

각 큐는 특정 테이블에 대한 복제를 관리하는 기술 워크플로우에서 처리되며 보류 중인 요청을 단일 병합 작업으로 실행합니다. 이러한 워크플로우는 새 복제 요청을 처리하기 위해 20초마다 트리거됩니다.

| 기술 워크플로 | 설명 |
|------|-----------|
| **nmsDelivery 큐 복제**(ffdaReplicateQueueDelivery) | `nms:delivery` 테이블에 대한 큐. |
| **nmsDlvExclusion 큐 복제**(ffdaReplicateQueueDlvExclusion) | `nms:dlvExclusion` 테이블에 대한 큐. |
| **nmsDlvMidRemoteIdRel 큐 복제**(ffdaReplicateQueueDlvMidRemoteIdRel) | `nms:dlvRemoteIdRel` 테이블에 대한 큐. |
| **nmsTrackingUrl 큐 복제**(ffdaReplicateQueueTrackingUrl)<br/>**동시 실행 시 nmsTrackingUrl 큐 복제**(ffdaReplicateQueueTrackingUrl_2) | 서로 다른 우선 순위를 기준으로 요청을 처리하여 효율성을 개선하기 위해 두 개의 워크플로우를 활용하는 `nms:trackingUrl` 테이블의 동시 큐. |

## 튜토리얼 {#video}

이 비디오는 Adobe Campaign v8에서 사용하는 데이터베이스, 데이터를 복제하는 이유, 복제하는 데이터 및 복제 프로세스의 작동 방식에 대한 주요 개념을 소개합니다.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)

추가 Campaign v8 클라이언트 콘솔 자습서는 [여기](https://experienceleague.adobe.com/ko/docs/campaign-learn/tutorials/overview)에서 확인할 수 있습니다.
