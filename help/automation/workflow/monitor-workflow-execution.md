---
product: campaign
title: 워크플로 실행 모니터링
description: 워크플로 실행 모니터링
feature: Workflows
role: Admin
version: Campaign v8, Campaign Classic v7
exl-id: bc13d706-7888-42eb-9116-5538e68cd515
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '1926'
ht-degree: 2%

---

# 워크플로 실행 모니터링 {#monitoring-workflow-execution}

이 섹션에서는 워크플로우 실행을 모니터링하는 방법에 대해 설명합니다.

[이 섹션](workflow-supervision.md#supervising-workflows)에서 &quot;일시 중지됨&quot;, &quot;중지됨&quot; 또는 &quot;오류 있음&quot;인 워크플로 집합의 상태를 모니터링할 수 있는 워크플로를 만드는 방법에 대한 사용 사례도 확인할 수 있습니다.

또한 인스턴스 관리자는 **감사 추적**&#x200B;을 사용하여 워크플로우에 수행된 활동 및 마지막 수정 사항, 즉 워크플로우의 상태를 확인할 수 있습니다. 이 [페이지](../../v8/reporting/audit-trail.md){target="_blank"}에서 감사 추적에 대해 자세히 알아보세요.

## 진행 상황 표시 {#displaying-progress}

도구 모음에서 적절한 아이콘을 사용하여 진행 상황을 표시하여 실행을 모니터링할 수 있습니다.

**[!UICONTROL Display progress information]** 아이콘을 사용하면 실행 화면에 상태와 활동 결과를 표시할 수 있습니다.

![](assets/s_user_segmentation_toolbar_progr.png)

이 옵션을 선택하면 실행된 활동은 파란색으로 표시되고, 보류 중인 활동은 깜박이며, 경고는 주황색으로 표시되고, 오류는 빨간색으로 표시됩니다. 이 옵션은 또한 아웃바운드 전환의 활동 결과를 표시한 다음 활동 속성에 정의된 결과의 레이블과 1초를 초과하는 경우 작업 기간을 표시합니다

![](assets/s_user_segmentation_results.png)

## 로그 표시 {#displaying-logs}

로그에는 워크플로우의 기록 또는 감사 추적이 포함되어 있습니다. 모든 사용자 작업, 수행된 모든 작업 및 발생한 오류를 등록합니다. 다음을 수행할 수 있습니다.

* 세부 정보에서 **[!UICONTROL Tracking]** 탭을 선택합니다. 이 목록에는 모든 워크플로우 메시지가 포함되어 있습니다.

  ![](assets/new-workflow-display-log-tab.png)

* 활동별로 로그 메시지를 필터링합니다. 이렇게 하려면 다이어그램 위에 있는 도구 모음에서 **[!UICONTROL Display the tasks and the log]**&#x200B;을(를) 클릭하여 다이어그램 아래에 **[!UICONTROL Log]** 및 **[!UICONTROL Tasks]** 탭을 표시합니다. 모든 관련 메시지를 볼 활동을 선택하십시오. 이 목록에는 활동을 선택하지 않은 경우 모든 메시지가 포함됩니다.

  ![](assets/new-workflow-display-log-activity.png)

  >[!NOTE]
  >
  >다이어그램의 배경을 클릭하여 모든 요소의 선택을 취소합니다.

* 주어진 작업에 연결된 메시지만 봅니다. 이렇게 하려면 **[!UICONTROL Tasks]** 탭을 선택한 다음 목록을 제한하기 위해 다이어그램에서 활동을 선택합니다. 작업을 두 번 눌러 정보를 표시합니다. 창의 마지막 탭에 로그가 포함됩니다.

  ![](assets/new-workflow-display-tasks-activity.png)

  **[!UICONTROL Details...]** 단추를 사용하면 활동 실행에 대한 모든 추가 정보를 표시할 수 있습니다. 예를 들어 유효성 검사 연산자와 적용 가능한 경우 승인 중에 입력한 설명을 볼 수 있습니다.

>[!NOTE]
>
>워크플로우가 다시 시작될 때 로그가 삭제되지 않습니다. 모든 메시지가 유지됩니다. 이전 실행에서 보낸 메시지를 취소하려면 기록을 지워야 합니다.

로그에는 타겟팅 워크플로우 활동과 관련된 실행 메시지의 시간 목록이 표시됩니다.

* 타깃팅 캠페인 로그

  타겟팅 캠페인이 실행되면 **[!UICONTROL Tracking]** 탭을 클릭하여 실행 추적을 확인합니다.

  ![](assets/s_user_segmentation_journal.png)

  모든 캠페인 메시지가 표시됩니다. 캠페인은 물론 경고 또는 오류도 수행됩니다.

* 활동 로그

  실행 로그와 각 활동의 세부 정보도 볼 수 있습니다. 두 가지 방법으로 이 작업을 수행할 수 있습니다.

   1. 타깃팅된 활동을 선택하고 **[!UICONTROL Display the tasks and the log]** 아이콘을 클릭합니다.

      ![](assets/s_user_segmentation_show_logs.png)

      다이어그램의 아래 섹션에는 로그와 작업, 이렇게 두 개의 탭이 표시됩니다.

      다이어그램 내에서 선택한 활동은 로그 및 작업 목록에서 필터 역할을 합니다.

      ![](assets/s_user_segmentation_logs.png)

   1. 타깃팅된 활동을 마우스 오른쪽 단추로 클릭하고 **[!UICONTROL Display logs]**&#x200B;을(를) 선택합니다.

      ![](assets/s_user_segmentation_logs_menu.png)

      로그는 별도의 창에 표시됩니다.

## 로그 삭제 {#purging-the-logs}

워크플로우 내역은 자동으로 삭제되지 않습니다. 기본적으로 모든 메시지가 유지됩니다. **[!UICONTROL File > Actions]** 메뉴를 사용하거나 목록 위의 도구 모음에 있는 **[!UICONTROL Actions]** 단추를 클릭하여 기록을 삭제할 수 있습니다. **[!UICONTROL Purge history]**&#x200B;을(를) 선택합니다. **[!UICONTROL Actions]** 메뉴에서 사용할 수 있는 옵션은 [작업 도구 모음](start-a-workflow.md) 섹션에 자세히 설명되어 있습니다.

![](assets/purge_historique.png)

## 작업 테이블 및 워크플로 스키마 {#worktables-and-workflow-schema}

워크플로는 특정 활동을 통해 조작할 수 있는 작업 테이블을 전달합니다. Adobe Campaign을 사용하면 데이터 관리 활동을 통해 워크플로 작업테이블의 열을 수정하고, 이름을 바꾸고, 보강할 수 있습니다. 예를 들어 클라이언트의 필요에 따라 명명법에 맞게 열을 정렬하고, 계약의 공동 수혜자에 대한 추가 정보를 수집하는 등의 작업을 수행할 수 있습니다.

다양한 작업 차원 사이에 링크를 만들고 차원 변경 사항을 정의할 수도 있습니다. 예를 들어 데이터베이스에 기록된 각 계약에 대해 주 보유자를 주소화하고 추가 정보에 있는 공동 보유자 데이터를 사용합니다.

워크플로우가 수동화되면 워크플로우의 작업테이블이 자동으로 삭제됩니다. 작업 테이블을 유지하려면 **[!UICONTROL List update]** 활동을 통해 목록에 저장합니다([목록 업데이트](list-update.md) 참조).

## 오류 관리 {#managing-errors}

오류가 발생하면 워크플로가 일시 중지되고 오류가 발생하면 실행 중인 활동이 빨간색으로 깜박입니다. 워크플로 개요에서 **[!UICONTROL Monitoring]** 탭 - **[!UICONTROL Workflows]** 링크 아래에 아래와 같이 오류만 있는 워크플로를 표시할 수 있습니다.

![](assets/wf-global-view_filter_only_errors.png)

Adobe Campaign 탐색기에서 기본적으로 워크플로 목록에 **[!UICONTROL Failed]** 열이 표시됩니다.

![](assets/wf-explorer_errors_col.png)

워크플로우가 오류일 때 워크플로우 감독 그룹에 속하는 운영자는 이메일 주소가 프로필에 나열되어 있는 한 이메일로 알림을 받게 됩니다. 이 그룹은 워크플로 속성의 **[!UICONTROL Supervisor(s)]** 필드에서 선택됩니다.

![](assets/wf-properties_select-supervisors.png)

알림 콘텐츠가 **[!UICONTROL Workflow manager notification]** 기본 템플릿에 구성되어 있습니다. 이 템플릿은 워크플로 속성의 **[!UICONTROL Execution]** 탭에서 선택됩니다. 알림에 오류 워크플로우의 이름과 관련 작업이 표시됩니다.

알림 예:

![](assets/wf-notification_error-msg.png)

이 링크를 사용하면 웹 모드에서 Adobe Campaign 클라이언트 콘솔에 액세스하고 로그인한 후 오류 워크플로우를 작업할 수 있습니다.

![](assets/wf-notification_error-console.png)

오류 발생 시 실행을 일시 중지하지 않고 계속하도록 워크플로를 구성할 수 있습니다. 이렇게 하려면 **[!UICONTROL Properties]** 워크플로우를 편집하고 **[!UICONTROL Error management]** 섹션에서 **[!UICONTROL In case of error]** 필드의 **[!UICONTROL Ignore]** 옵션을 선택합니다. 그런 다음에는 프로세스가 일시 중지되기 전에 무시할 수 있는 연속 오류 수를 지정할 수 있습니다.

이 경우 오류 작업이 중단됩니다. 이 모드는 나중에 캠페인을 다시 시도하도록 설계된 워크플로우(주기적 작업)에 특히 적합합니다.

![](assets/wf_edit_properties_for_error_mgt.png)

>[!NOTE]
>
>각 활동에 대해 개별적으로 이 구성을 적용할 수 있습니다. 이렇게 하려면 활동 속성을 편집하고 **[!UICONTROL Advanced]** 탭에서 오류 관리 모드를 선택하십시오.

## 처리 오류 {#processing-errors}

활동과 관련하여 **[!UICONTROL Process errors]** 옵션에는 오류가 발생하면 사용할 수 있는 특정 전환이 표시됩니다. 이 경우 워크플로우가 오류 모드로 전환되지 않고 실행이 계속됩니다.

파일 시스템 오류(파일 이동 불가, 디렉터리 액세스 불가 등)를 고려하는 오류는 다음과 같습니다.

이 옵션은 활동 구성과 관련된 오류, 즉 잘못된 값을 처리하지 않습니다. 잘못된 구성과 관련된 오류는 이 전환을 활성화하지 않습니다(디렉토리가 없는 등).

워크플로가 일시 중지되면(오류 발생 후 수동으로 또는 자동으로) **[!UICONTROL Start]** 단추가 중지된 워크플로 실행을 다시 시작합니다. 잘못된 활동(또는 일시 중지된 활동)이 다시 실행됩니다. 이전 활동은 다시 실행되지 않습니다.

모든 워크플로우 활동을 다시 실행하려면 **[!UICONTROL Restart]** 단추를 사용하십시오.

이미 실행된 활동을 수정하는 경우, 워크플로우 실행이 다시 시작될 때 변경 사항은 고려되지 않습니다.

실행되지 않은 활동을 수정하는 경우 워크플로우 실행이 다시 시작될 때 고려됩니다.

일시 중지된 활동을 수정하면 워크플로우를 다시 시작할 때 변경 사항을 올바르게 고려할 수 없습니다.

가능한 경우 수정을 수행한 후 워크플로우를 완전히 다시 시작하는 것이 좋습니다.

## 인스턴스 감독 {#instance-supervision}

**[!UICONTROL Instance supervision]** 페이지에서는 Adobe Campaign 서버 활동을 보고 오류가 있는 워크플로우 및 게재 목록을 표시할 수 있습니다.

이 페이지에 액세스하려면 **[!UICONTROL Monitoring]** 탭으로 이동하여 **[!UICONTROL General view]** 링크를 클릭하십시오.

![](assets/wf-monitoring_from-homepage.png)

모든 워크플로를 표시하려면 **[!UICONTROL Workflows]** 링크를 클릭하십시오. 드롭다운 목록을 사용하여 상태에 따라 플랫폼의 워크플로우를 표시합니다.

![](assets/wf-monitoring_edit-wf.png)

오류가 있는 워크플로우의 링크를 클릭하여 워크플로우를 열고 로그를 확인합니다.

![](assets/wf-monitoring_edit-task-wf.png)

## 동시 다중 실행 방지 {#preventing-simultaneous-multiple-executions}

단일 워크플로우에서는 여러 개의 실행이 동시에 실행될 수 있습니다. 경우에 따라 이러한 일이 발생하지 않도록 해야 합니다.

예를 들어 스케줄러가 한 시간마다 워크플로우 실행을 트리거하도록 할 수 있지만 경우에 따라 전체 워크플로우를 실행하는 데 한 시간 이상이 걸립니다. 워크플로우가 이미 실행 중인 경우 실행을 건너뛸 수 있습니다.

워크플로우 시작 시 신호 활동이 있는 경우 워크플로우가 실행 중인 경우 신호를 건너뛸 수 있습니다.

일반적인 원칙은 다음과 같습니다.

![](assets/workflow-reentrancy-protection-principle.png)

해결 방법은 인스턴스 변수를 사용하는 것입니다. 인스턴스 변수는 워크플로우의 모든 병렬 실행에 의해 공유됩니다.

다음은 간단한 테스트 워크플로입니다.

![](assets/wkf_simultaneous_execution1.png)

**[!UICONTROL Scheduler]**&#x200B;이(가) 매 분마다 이벤트를 트리거하고 있습니다. 다음 **[!UICONTROL Test]** 활동은 **isRunning** 인스턴스 변수를 테스트하여 실행을 계속할지 여부를 결정합니다.

![](assets/wkf_simultaneous_execution2.png)

>[!NOTE]
>
>**isRunning**&#x200B;은(는) 이 예제에 대해 선택한 변수 이름입니다. 기본 제공 변수가 아닙니다.

**yes** 분기에서 **[!UICONTROL Test]**&#x200B;을(를) 바로 다음에 오는 작업은 해당 **초기화 스크립트**&#x200B;에서 인스턴스 변수를 설정해야 합니다.

```
instance.vars.isRunning = true
```

**yes** 분기의 마지막 활동은 **초기화 스크립트**&#x200B;에서 변수를 false로 되돌려야 합니다.

```
instance.vars.isRunning = false
```

참고:

* 워크플로 **속성**&#x200B;의 **변수** 탭을 통해 인스턴스 변수의 현재 값을 확인할 수 있습니다.
* 인스턴스 변수는 워크플로우를 다시 시작할 때 재설정됩니다.
* JavaScript에서 정의되지 않은 값은 테스트에서 false이므로 인스턴스 변수를 초기화하기 전에도 테스트할 수 있습니다.
* &quot;no&quot; 끝의 초기화 스크립트에 로깅 명령을 추가하여 이 메커니즘으로 인해 처리되지 않는 활동을 모니터링할 수 있습니다.

  ```
  logInfo("Workflow already running, parallel execution not allowed.");
  ```

사용 사례는 이 섹션에 나와 있습니다. [데이터 업데이트 조정](coordinate-data-updates.md).

## 데이터베이스 유지 관리 {#database-maintenance}

워크플로우는 공간을 소모하는 많은 작업 표를 사용하며, 유지하지 않을 경우 전체 플랫폼의 속도를 느리게 합니다.

**관리 > 프로덕션 > 기술 워크플로우** 노드를 통해 액세스할 수 있는 **데이터베이스 정리** 워크플로우를 사용하면 데이터베이스의 기하급수적인 증가를 방지하기 위해 오래된 데이터를 삭제할 수 있습니다. 워크플로우는 사용자의 개입 없이 자동으로 트리거됩니다.

또한 특정 기술 워크플로우를 만들어 불필요한 데이터 사용 공간을 제거할 수도 있습니다. 을(를) 참조하십시오   이 [섹션](#purging-the-logs)과(와) 함께입니다.

## 일시 중지된 워크플로우 처리 {#handling-of-paused-workflows}

기본적으로 워크플로우가 일시 중지되면 작업 테이블이 삭제되지 않습니다. 빌드 8880에서 너무 오랫동안 일시 중지된 워크플로우가 자동으로 중지되고 작업 테이블이 삭제됩니다. 이 동작은 다음과 같이 트리거됩니다.

* 7일 이상 일시 중지된 워크플로우는 모니터링 대시보드(및 모니터링 API)에 경고로 표시되며 감독자 그룹에 알림이 전송됩니다.
* **[!UICONTROL cleanupPausedWorkflows]** 기술 워크플로우가 트리거되는 매주 동일한 상황이 발생합니다. 워크플로에 대한 자세한 내용은 [이 섹션](delivery.md)을 참조하세요.
* 4개의 알림(즉, 기본적으로 일시 중지된 상태에서 1개월) 이후 워크플로우가 무조건 중지됩니다. 로그가 중지되면 워크플로우에 나타납니다. 다음 실행 **[!UICONTROL cleanup]** 워크플로우에서 테이블이 제거됩니다.

이러한 기간은 NmsServer_PausedWorkflowPeriod 옵션을 통해 구성할 수 있습니다.

워크플로 감독자에게 알림이 전송됩니다. 워크플로우를 수정한 작성자 및 마지막 사용자에게도 알림이 표시됩니다. 관리자가 알림을 받지 못합니다.

## 상태에 따라 워크플로우 필터링 {#filtering-workflows-status}

Campaign Classic 인터페이스를 사용하면 사전 정의된 **보기**&#x200B;를 사용하여 인스턴스에 있는 모든 워크플로우의 실행 상태를 모니터링할 수 있습니다. 이 보기에 액세스하려면 **[!UICONTROL Administration]** / **[!UICONTROL Audit]** / **[!UICONTROL Workflows Status]** 노드를 여십시오.

다음 보기를 사용할 수 있습니다.

* **[!UICONTROL Running]**: 실행 중인 모든 워크플로를 나열합니다.
* **[!UICONTROL Paused]**: 일시 중지된 워크플로를 모두 나열합니다.
* **[!UICONTROL Failed]**: 실패한 모든 워크플로를 나열합니다.
* ** ).

![](assets/workflow-monitoring-views.png)

기본적으로 이러한 보기는 **[!UICONTROL Audit]** 폴더에서 액세스할 수 있습니다. 그러나 폴더 트리에서 선택한 위치에 다시 만들 수 있습니다. 이렇게 하면 관리 권한이 없는 표준 사용자가 사용할 수 있습니다.

방법은 다음과 같습니다.

1. 보기를 추가할 폴더를 마우스 오른쪽 단추로 클릭합니다.
1. **[!UICONTROL Add new folder]** / **[!UICONTROL Administration]**&#x200B;에서 추가할 보기를 선택합니다.
1. 폴더가 트리에 추가되면 해당 원래 폴더가 무엇이든 간에 모든 워크플로우를 표시할 수 있도록 해당 폴더를 보기로 구성해야 합니다. 보기를 구성하는 방법에 대한 자세한 내용은 [이 페이지](../../v8/audiences/folders-and-views.md#turn-a-folder-to-a-view)를 참조하세요.

이러한 보기 외에 필터 폴더를 설정하여 실행 상태에 따라 워크플로 목록을 필터링할 수 있습니다. 방법은 다음과 같습니다.

1. 워크플로 유형 폴더에 액세스한 다음 **[!UICONTROL Filters]** / **[!UICONTROL Advanced filter]** 메뉴를 선택합니다.
1. 워크플로우의 **[!UICONTROL @status]** 필드가 선택한 상태와 같도록 필터를 구성합니다.
1. 필터를 저장하고 필터 이름을 지정합니다. 그런 다음 필터 목록에서 바로 사용할 수 있습니다.

![](assets/workflow-monitoring-filter.png)

자세한 내용은 다음 섹션을 참조하십시오.
