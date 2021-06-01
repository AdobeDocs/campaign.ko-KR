---
product: Adobe Campaign
title: Campaign API 스테이징 메커니즘
description: Campaign API 스테이징 메커니즘
feature: 개요
role: Data Engineer
level: Beginner
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 3%

---

# Campaign API 스테이징 메커니즘

Campaign Cloud 데이터베이스를 사용하면 성능(지연 및 동시성)으로 인해 단일 호출을 권장하지 않습니다. 배치 작업이 항상 선호됩니다. API의 최적 성능을 보장하기 위해 Campaign은 로컬 데이터베이스 수준에서 API 호출을 계속 처리합니다.

기본 제공 및 사용자 지정 테이블에 대해 캠페인 스테이징 메커니즘을 사용할 수 있으며 다음과 같은 이점을 제공합니다.

* 데이터 스키마 구조가 로컬 스테이징 테이블에 복제됩니다
* 섭취 처리를 위한 새 API가 스테이징 테이블로 바로 유입됩니다. [자세히 알아보기](new-apis.md)
* 예약된 워크플로우는 매시간 트리거되고 데이터를 다시 클라우드 데이터베이스에 동기화합니다. [자세히 알아보기](../config/replication.md)

일부 기본 제공 스키마는 nmsSubscriptionRcp, nmsAppSubscriptionRcp, nmsRecipient와 같이 기본적으로 준비됩니다.

Campaign Classic v7 API는 계속 사용할 수 있지만 이 새로운 스테이징 메커니즘을 사용할 수는 없습니다.API 호출은 클라우드 데이터베이스에 직접 연결되도록 플로우됩니다. Adobe은 Campaign Cloud 데이터베이스의 전체 압력 및 지연을 줄이기 위해 가능한 한 새로운 스테이징 메커니즘을 사용하는 것이 좋습니다.

>[!CAUTION]
>
>이 새로운 메커니즘을 통해 구독, 구독 취소 또는 모바일 등록에 대한 데이터 동기화는 이제 **비동기**&#x200B;입니다.


## 구현 단계{#implement-staging}

특정 테이블에서 Campaign 스테이징 메커니즘을 구현하려면 아래 단계를 수행하십시오.

1. Campaign Cloud 데이터베이스에서 샘플 사용자 지정 스키마를 만듭니다. 이 단계에서 활성화된 스테이징이 없습니다.

   ```
   <srcSchema _cs="Sample Table (dem)" created="YYYY-DD-MM"
           entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
           lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
           modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
   <element autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
           name="sampleTable">
       <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
       <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
   </element>
   </srcSchema>
   ```

   [!DNL :bulb:]  [이 페이지에서 사용자 지정 스키마 만들기에 대한 자세한 내용을 살펴보십시오](create-schema.md).

1. 데이터베이스 구조를 저장하고 업데이트합니다.  [자세히 알아보기](update-database-structure.md)

1. **autoStg=&quot;true&quot;** 매개 변수를 추가하여 스키마 정의에서 스테이징 메커니즘을 활성화합니다.

   ```
   <srcSchema _cs="Sample Table (dem)" "YYYY-DD-MM"
           entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
           lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
           modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
   <element autoStg="true" autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
           name="sampleTable">
       <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
       <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
   </element>
   </srcSchema>
   ```

1. 수정 사항을 저장합니다. 초기 스키마의 로컬 복사본인 새 스테이징 스키마를 사용할 수 있습니다.

   ![](assets/staging-mechanism.png)

1. 데이터베이스 구조를 업데이트합니다. 스테이징 테이블은 Campaign 로컬 데이터베이스에 만들어집니다.
