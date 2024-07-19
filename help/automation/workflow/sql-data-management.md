---
product: campaign
title: SQL 데이터 관리
description: SQL 데이터 관리 워크플로우 활동에 대해 자세히 알아보기
feature: Workflows
Role: User
Level: Experienced
exl-id: a1e08d57-0387-4802-b447-f6d9ad87072a
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 3%

---

# SQL 데이터 관리{#sql-data-management}

**SQL 데이터 관리** 활동을 사용하면 고유한 SQL 스크립트를 작성하여 작업 테이블을 만들고 채울 수 있습니다.

## 필수 구성 요소 {#prerequisites}

활동을 구성하기 전에 다음 전제 조건이 충족되는지 확인하십시오.

* 활동은 원격 데이터 소스에만 사용할 수 있습니다.
* 아웃바운드 스키마는 데이터베이스에 있어야 하며 FDA 데이터베이스에 연결되어 있어야 합니다.


## SQL 데이터 관리 활동 구성 {#configuring-the-sql-data-management-activity}

1. **[!UICONTROL Label]** 활동을 지정하십시오.
1. 사용할 **[!UICONTROL External account]**&#x200B;을(를) 선택한 다음 이 외부 계정에 연결된 **[!UICONTROL Outbound schema]**&#x200B;을(를) 선택하십시오.

   >[!CAUTION]
   >
   >아웃바운드 스키마는 고정되어 편집할 수 없습니다.

1. SQL 스크립트를 추가합니다.

   >[!CAUTION]
   >
   >SQL 스크립트가 작동하고 해당 참조(필드 이름 등)가 작동하는지 확인하는 것은 SQL 스크립트 작성자의 책임입니다. 은 아웃바운드 스키마를 따릅니다.

   기존 SQL 코드를 로드하려면 **[!UICONTROL The SQL script is contained in an entity stored in the database]** 옵션을 선택하십시오. SQL 스크립트를 만들고 **[!UICONTROL Administration]** / **[!UICONTROL Configuration]** / **[!UICONTROL SQL scripts]** 메뉴에 저장해야 합니다.

   그렇지 않으면 전용 영역에 SQL 스크립트를 입력하거나 복사하여 붙여넣습니다.

   ![](assets/sql_datamanagement.png)

   활동을 통해 스크립트에서 다음 변수를 사용할 수 있습니다.

   * **activity.tableName**: 아웃바운드 작업 테이블의 SQL 이름입니다.
   * **task.incomingTransitionByName(&#39;name&#39;).tableName**: 사용할 들어오는 전환에 의해 전달되는 작업 테이블의 SQL 이름(전환은 해당 이름으로 식별됨).

     >[!NOTE]
     >
     >(&#39;name&#39;) 값은 전환 속성의 **[!UICONTROL Name]** 필드에 해당합니다.

1. SQL 스크립트에 아웃바운드 작업 테이블을 만드는 명령이 이미 있는 경우 **[!UICONTROL Automatically create work table]** 옵션을 선택 취소합니다. 그렇지 않으면 워크플로우가 실행되면 작업 테이블이 자동으로 만들어집니다.
1. **[!UICONTROL Ok]**&#x200B;을(를) 클릭하여 활동 구성을 확인합니다.

이제 활동이 구성되었습니다. 워크플로우에서 실행할 준비가 되었습니다.

>[!CAUTION]
>
>활동이 실행되면 아웃바운드 전환 레코드 수가 표시용으로만 표시됩니다. SQL 스크립트의 복잡성 수준에 따라 달라질 수 있습니다.
>  
>활동이 다시 시작되면 실행 상태에 관계없이 전체 스크립트가 처음부터 실행됩니다.

## SQL 스크립트 샘플 {#sql-script-samples}

>[!NOTE]
>
>이 섹션의 스크립트 샘플은 PostgreSQL에서 실행되도록 설계되었습니다.

아래 스크립트를 사용하면 작업 테이블을 만들고 동일한 작업 테이블에 데이터를 삽입할 수 있습니다.

```
CREATE UNLOGGED TABLE <%= activity.tableName %> (
  iRecipientId INTEGER DEFAULT 0,
  sFirstName VARCHAR(100),
  sMiddleName VARCHAR(100),
  sLastName VARCHAR(100),
  sEmail VARCHAR(100)
);

INSERT INTO <%= activity.tableName %>
SELECT iRecipientId, sFirstName, sMiddleName, sLastName, sEmail
FROM nmsRecipient
GROUP BY iRecipientId, sFirstName, sMiddleName, sLastName, sEmail;
```

아래 스크립트를 사용하면 CTAS 작업(CREATE TABLE AS SELECT)을 수행하고 작업 테이블 인덱스를 만들 수 있습니다.

```
CREATE TABLE <%= activity.tableName %>
AS SELECT iRecipientId, sEmail, sFirstName, sLastName, sMiddleName
FROM nmsRecipient
WHERE sEmail IS NOT NULL
GROUP BY iRecipientId, sEmail, sFirstName, sLastName, sMiddleName;

CREATE INDEX ON <%= activity.tableName %> (sEmail);

ANALYZE <%= activity.tableName %> (sEmail);
```

아래 스크립트를 사용하면 두 개의 작업 테이블을 병합할 수 있습니다.

```
CREATE TABLE <%= activity.tableName %>
AS SELECT i1.sFirstName, i1.sLastName, i2.sEmail
FROM <%= task.incomingTransitionByName('input1').tableName %> i1
JOIN <%= task.incomingTransitionByName('input2').tableName %> i2 ON (i1.id = i2.id)
```
