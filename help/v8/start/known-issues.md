---
title: Campaign v8 알려진 문제
description: 최신 Campaign 릴리스의 알려진 문제
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
source-git-commit: 3d84bb9493251afa7b7e89a07469d299ff412c24
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 3%

---

# 알려진 문제{#known-issues}

이 페이지에는 **최신 Campaign v8 릴리스**. 또한 Campaign v8에는 제한 사항이 나열되어 있습니다 [이 페이지에서](ac-guardrails.md).


>[!NOTE]
>
>Adobe은 자체 재량에 따라 이 알려진 문제 목록을 게시합니다. 고객 보고서 수, 심각도 및 해결 방법을 기반으로 합니다. 표시되는 문제가 나열되지 않으면 이 페이지에 게시하기 위한 기준에 맞지 않을 수 있습니다.

<!--
## Change Data Source activity issue #1 {#issue-1}

### Description{#issue-1-desc}

The **Change Data Source** activity is failing when transfering data from Campaign local database to Snowflake cloud database. When switching directions, the activity can generate issues.

### Reproduction steps{#issue-1-repro}

1. Connect to the client console and create a workflow.
1. Add a **Query** activity and a **Change Data Source** activity.
1. Define a query on the **email**, which is a string.
1. Run the workflow and right-click the transition to view the population: the email records are displayed replaced by `****`.
1. Check the workflow logs: the **Change Data Source** activity interprets these records as numeric values.

### Error message{#issue-1-error}

```sql
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

### Workaround{#issue-1-workaround}

To have the data transfered from Snowflake cloud database to Campaign local database and back to Snowflake, you must use two different **Change Data Source** activities.

### Internal reference{#issue-1-ref}

Reference: NEO-45549 
-->


## 데이터 소스 활동 변경 문제 {#issue-2}

### 설명{#issue-2-desc}

Campaign을 사용하여 Snowflake 클라우드 데이터베이스에 데이터를 삽입할 때 **쿼리** 그리고 **데이터 소스 변경** 활동, 백슬래시 문자가 데이터에 있으면 프로세스가 실패합니다. 소스 문자열이 이스케이프되지 않고 데이터가 Snowflake 시 올바르게 처리되지 않습니다.

이 문제는 백슬래시 문자가 문자열 끝에 있는 경우에만 발생합니다(예: ). `Barker\`.


### 복제 단계{#issue-2-repro}

1. 클라이언트 콘솔에 연결하고 워크플로우를 만듭니다.
1. 추가 **쿼리** 활동을 구성하고 구성합니다.
1. 위에 설명된 특성을 사용하여 데이터를 선택합니다.
1. 추가 **데이터 소스 변경** 활동을 구성하고 Snowflake 클라우드 데이터베이스를 선택하도록 구성합니다.
1. 워크플로우를 실행하고 워크플로우 로그를 확인하여 오류를 확인합니다.


### 오류 메시지{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

### 해결 방법{#issue-2-workaround}

해결 방법은 문자열 끝에서 백슬래시 문자가 포함된 데이터를 제외하거나 소스 파일에서 제거하는 것입니다.

<!--
As a workaround, export the files with double quotes around the problematic values (like `Barker\`) and include a file format option `FIELD_OPTIONALLY_ENCLOSED_BY = '"'`.
-->

### 내부 참조{#issue-2-ref}

참조: NEO-45549


## 데이터 로드(파일) 활동이 서버의 파일을 업로드하지 못했습니다. {#issue-3}

### 설명{#issue-3-desc}

를 사용하여 Campaign 서버에 파일을 업로드할 때 **데이터 로드(파일)** 활동, 프로세스는 100%에서 중지되지만 종료되지 않습니다.

### 복제 단계{#issue-3-repro}

1. 클라이언트 콘솔에 연결하고 워크플로우를 만듭니다.
1. 추가 **데이터 로드(파일)** 활동을 구성하고 구성합니다.
1. 을(를) 선택합니다 **서버에 업로드** 선택 사항입니다.
1. 로컬 컴퓨터에서 파일을 선택하고
1. 클릭 **업로드**


### 오류 메시지{#issue-3-error}

프로세스가 종료되지 않습니다.

### 해결 방법{#issue-3-workaround}

해결 방법은 이전 클라이언트 콘솔을 사용하는 것입니다. 그러면 서버에 파일을 업로드할 수 있습니다.

Campaign 관리자는 [Adobe 소프트웨어 배포](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Repeat&amp;1_group.propertyvalues.operation=equals&amp;1_group.propertyvalues.0_values=target-version%3Acampaign%2F8&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&amp;orderby.sort=desc&amp;layout=list&amp;p.offset=0&amp;p.limit=4){target=&quot;_blank&quot;}.

Adobe 소프트웨어 배포에 액세스하는 방법 알아보기 [이 페이지에서](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=ko){target=&quot;_blank&quot;}.

클라이언트 콘솔을 업그레이드하는 방법 알아보기 [이 페이지에서](connect.md)

### 내부 참조{#issue-3-ref}

참조: NEO-47269
