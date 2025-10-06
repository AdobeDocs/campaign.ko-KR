---
title: Adobe Campaign 워크플로우를 통해 프로세스 관리 및 자동화
description: 워크플로 시작
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 95c944963feee746a2bb83a85f075134c91059d1
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 4%

---

# 워크플로 시작{#gs-with-workflows}

강력한 마케팅 캠페인 자동화 기능을 활용하도록 Campaign을 구성합니다.

다음을 설정할 수 있습니다.

* 워크플로
* 반복 캠페인
* 엔드 투 엔드 유효성 검사 주기
* 경고
* 자동 보고서 전송
* 트리거된 이벤트

>[!NOTE]
>
>Adobe Campaign 웹 사용자 인터페이스에는 워크플로우에 대한 재설계된 캔버스가 함께 제공되므로 보다 동적이고 개인화된 고객 여정을 만들 수 있습니다. 웹 UI용 워크플로에 대한 자세한 내용은 [Adobe Campaign 웹 UI 설명서](https://experienceleague.adobe.com/en/docs/campaign-web/v8/wf/gs-workflows){target=_blank}를 참조하세요.


## 워크플로 디자인 및 사용 {#gs-ac-wf}

Adobe Campaign 워크플로우를 사용하여 세그먼트 만들기, 메시지 준비에서 게재에 이르기까지 마케팅 캠페인의 모든 측면에 대한 속도와 규모를 개선합니다.

다음 페이지에서 워크플로우 사용자 인터페이스 및 실행에 대해 자세히 알아보십시오.

* [워크플로 시작](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=ko){target="_blank"}

* [워크플로 모범 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}

* [기본 제공 기술 워크플로우](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}

* [워크플로우 실행 모니터링](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

* [마케팅 캠페인 워크플로우에서 대상자 만들기](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=ko){target="_blank"}

## 워크플로 활동 {#wf-activities}

[이 섹션](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html?lang=ko){target="_blank"}에서 사용 가능한 워크플로우 활동에 대해 자세히 알아보세요.

워크플로우 활동은 범주별로 그룹화됩니다. 네 가지 활동 카테고리를 사용할 수 있습니다.

* [타깃팅 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"}: 쿼리, 목록 읽기, 데이터 보강, 결합 등
* [흐름 제어 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"}: 스케줄러, 포크, 경고, 외부 신호 등
* [작업 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html){target="_blank"}: 크로스 채널 게재, Javascript 코드, CRM 활동, 업데이트 집계 등
* [이벤트 활동](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html){target="_blank"}: 파일 전송, 웹 다운로드 등

<!--
### Change data source activity {#change-data-source-activity}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. This provides more flexibility to manage data across different data sources such as FDA, FFDA and local database.

The **[!UICONTROL Working table]** allows Adobe Campaign workflow to handle data and share data with the workflow activities.
By default, the **[!UICONTROL Working table]** is created in the same database as the source of the data we query on.

For example, when querying the **[!UICONTROL Profiles]** table, stored on the Cloud database, you will create a **[!UICONTROL Working table]** on the same Cloud database.
To change this, you can add the **[!UICONTROL Change Data Source]** activity to choose a different data source for your **[!UICONTROL Working table]**.

Note that when using the **[!UICONTROL Change Data Source]** activity, you will need to switch back to the Cloud database to continue the workflow execution.

To use the **[!UICONTROL Change Data Source]** activity:

1. Create a workflow.

1. Query your targeted recipients with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}.

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

    For more information on the **[!UICONTROL JavaScript code]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html){target="_blank"}.

1. Add another **[!UICONTROL Change data source]** activity to switch back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. You can now start your workflow.
-->

## 가상 웨어하우스 관리 {#warehouse}

워크플로우를 만든 후 추가 구성을 위해 **[!UICONTROL Properties]** 단추를 사용하여 추가 옵션에 액세스할 수 있습니다.

**이 페이지**&#x200B;에서 [워크플로 속성](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html){target="_blank"}에 대해 자세히 알아보세요.

워크플로우 **[!UICONTROL Execution]**&#x200B;의 **[!UICONTROL Properties]** 탭에서 워크플로우를 다른 웨어하우스에 연결하고 워크로드 관리를 최적화하도록 선택할 수 있습니다. **웨어하우스**&#x200B;에 대한 자세한 내용은 [Snowflake 설명서](https://docs.snowflake.com/en/user-guide/warehouses-overview.html){target="_blank"}를 참조하세요.

![](assets/warehouse.png)

워크플로우의 목적에 따라 **[!UICONTROL Warehouse]** 드롭다운에서 다음 세 개의 웨어하우스 중에서 선택할 수 있습니다.

* **[!UICONTROL Default]** / **[!UICONTROL Campaign]**: 새 워크플로우를 만들 때 기본적으로 설정됩니다.

* **[!UICONTROL Import / Export]**: 활동 성능을 최적화하려면 가져오기 또는 내보내기 워크플로우로 설정해야 합니다.

* **[!UICONTROL Campaign Burst]**: 게재 처리 시간을 최적화하려면 캠페인 또는 게재 워크플로우로 설정해야 합니다.

>[!NOTE]
>
>**[!UICONTROL System]** 웨어하우스는 기본 제공 워크플로우에 대해서만 설정됩니다.

## 반복 캠페인 설정

워크플로우를 실행할 때마다 반복 워크플로우를 디자인하고 새 게재 인스턴스를 만듭니다. 예를 들어 워크플로우가 일주일에 한 번 실행되도록 디자인되면 1년 후 52회 게재가 됩니다. 즉, 로그가 각 게재 인스턴스에 의해 구분됩니다.

[이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html?lang=ko){target="_blank"}에서 반복 캠페인을 만드는 방법을 알아보세요.


## 트리거 이벤트 활용

Campaign 트랜잭션 메시지를 사용하여 정보 시스템에서 트리거된 이벤트에서 생성된 메시지를 자동화합니다. 이러한 트랜잭션 메시지는 예를 들어 송장, 주문 확인, 배송 확인, 암호 변경, 제품 불가능 알림, 계정 명세서 또는 웹 사이트 계정 생성일 수 있습니다. 이러한 메시지는 이메일, SMS 또는 푸시 알림을 통해 개별적으로 또는 일괄적으로 전송할 수 있습니다.

[이 섹션](../send/transactional.md)에서 트랜잭션 메시지 기능에 대해 자세히 알아보세요.

Adobe Campaign 및 Adobe Analytics을 연결하여 사용자 작업을 검색하고 거의 실시간으로 개인화된 메시지를 전송합니다.

[이 섹션](../start/connect.md)에서 Campaign을 다른 솔루션과 통합하는 방법을 알아봅니다.


## 워크플로 전체 사용 사례{#end-to-end-uc}

이 섹션[에서 캠페인 워크플로우 기능 &#x200B;](../../automation/workflow/workflow-use-cases.md)을(를) 활용하는 사용 사례를 통해 알아봅니다.
