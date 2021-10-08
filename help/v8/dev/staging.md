---
title: Campaign API 스테이징 메커니즘
description: Campaign API 스테이징 메커니즘
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 96693af9-50db-4298-ae02-c238d35e52b4
source-git-commit: 9e07353859e63b71abb61526f40675f18837bc59
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 2%

---

# Campaign API 스테이징 메커니즘

Campaign Cloud 데이터베이스를 사용하면 성능(지연 및 동시성)과 관련하여 단방향 호출을 권장하지 않습니다. 일괄 처리 작업이 항상 선호됩니다. 성능을 향상시키기 위해 수집 API가 로컬 데이터베이스로 리디렉션됩니다.

Campaign 스테이징 기능은 일부 기본 제공 스키마에서 기본적으로 활성화되어 있습니다. 모든 사용자 지정 스키마에서 활성화할 수도 있습니다. nutshell의 스테이징 메커니즘:

* 데이터 스키마 구조는 로컬 스테이징 테이블에 복제됩니다
* 데이터 수집 전용 API가 로컬 스테이징 테이블로 바로 유입됩니다. [자세히 알아보기](new-apis.md)
* 예약된 워크플로우는 매시간 트리거되고 데이터를 다시 클라우드 데이터베이스에 동기화합니다. [자세히 알아보기](../config/replication.md)

일부 기본 제공 스키마는 nmsSubscriptionRcp, nmsAppSubscriptionRcp, nmsRecipient와 같이 기본적으로 준비됩니다.

Campaign Classic v7 API는 계속 사용할 수 있지만 이 새로운 스테이징 메커니즘을 사용할 수는 없습니다. API 호출은 클라우드 데이터베이스에 직접 연결되도록 플로우됩니다. Adobe은 Campaign Cloud 데이터베이스의 전체 압력 및 지연을 줄이기 위해 가능한 한 새로운 스테이징 메커니즘을 사용하는 것이 좋습니다.

>[!CAUTION]
>
>* 이 새로운 메커니즘을 통해 이제 채널 옵트아웃, 구독, 구독 취소 또는 모바일 등록에 대한 데이터 동기화가 **비동기**&#x200B;입니다.
>
>* 스테이징은 클라우드 데이터베이스에 저장된 스키마에 대해서만 적용됩니다. 복제된 스키마에 스테이징을 활성화하지 마십시오. 로컬 스키마에서 스테이징을 활성화하지 마십시오. 스테이징된 스키마에 스테이징을 사용하지 않음

>


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

   ![](../assets/do-not-localize/glass.png)  [이 페이지에서 사용자 지정 스키마 만들기에 대한 자세한 내용을 살펴보십시오](create-schema.md).

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
