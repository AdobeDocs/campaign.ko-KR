---
title: Campaign API 스테이징 메커니즘
description: Campaign API 스테이징 메커니즘
feature: API, FFDA
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 96693af9-50db-4298-ae02-c238d35e52b4
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 2%

---

# Campaign API 스테이징 메커니즘

의 맥락에서 [엔터프라이즈(FFDA) 배포](enterprise-deployment.md), 성능(지연 및 동시 실행)과 관련하여 단일 호출을 폭파하지 않는 것이 좋습니다. 일괄 처리 작업이 항상 선호됩니다. 성능을 개선하기 위해 수집 API는 로컬 데이터베이스로 리디렉션됩니다.

Campaign 스테이징 기능은 일부 기본 제공 스키마에서 기본적으로 활성화됩니다. 모든 사용자 지정 스키마에서 활성화할 수도 있습니다. 간단히 말해 스테이징 메커니즘:

* 데이터 스키마 구조가 로컬 스테이징 테이블에 복제됨
* 데이터 수집 전용 새 API는 로컬 스테이징 테이블로 직접 전송됩니다. [자세히 알아보기](new-apis.md)
* 예약된 워크플로우는 매 시간마다 트리거되며 데이터를 클라우드 데이터베이스로 다시 동기화합니다. [자세히 알아보기](replication.md)

nmsSubscriptionRcp, nmsAppSubscriptionRcp, nmsRecipient와 같은 일부 내장 스키마는 기본적으로 준비됩니다.

Campaign Classic v7 API는 계속 사용할 수 있지만 이 새로운 스테이징 메커니즘의 이점을 이용할 수 없습니다. API 호출은 클라우드 데이터베이스로 직접 전송됩니다. Adobe은 Campaign Cloud 데이터베이스에 대한 전체 압력과 지연을 줄이기 위해 가능한 한 새 스테이징 메커니즘을 사용하는 것을 권장합니다.

>[!CAUTION]
>
>* 이 새로운 메커니즘을 사용하면 채널 옵트아웃, 구독, 구독 취소 또는 모바일 등록에 대한 데이터 동기화가 수행됩니다 **비동기**.
>
>* 스테이징은 클라우드 데이터베이스에 저장된 스키마에만 적용됩니다. 복제된 스키마에 스테이징을 사용하지 마십시오. 로컬 스키마에서 스테이징을 사용하지 마십시오. 스테이징된 스키마에서 스테이징을 사용하지 않음
>


## 구현 단계{#implement-staging}

특정 표에서 캠페인 스테이징 메커니즘을 구현하려면 아래 단계를 따르십시오.

1. Campaign Cloud 데이터베이스에 샘플 사용자 지정 스키마를 만듭니다. 이 단계에서 활성화된 스테이징이 없습니다.

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

   ![](../assets/do-not-localize/glass.png) 에서 사용자 정의 스키마 만들기에 대해 자세히 알아보기 [이 페이지](../dev/create-schema.md).

1. 데이터베이스 구조를 저장하고 업데이트합니다.  [자세히 알아보기](../dev/update-database-structure.md)

1. 다음을 추가하여 스키마 정의에서 스테이징 메커니즘 활성화 **autoStg=&quot;true&quot;** 매개 변수.

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

1. 데이터베이스 구조를 업데이트합니다. 스테이징 테이블이 Campaign 로컬 데이터베이스에 만들어집니다.
