---
product: campaign
title: 작업 만들기 및 관리
description: 작업 만들기 및 관리
source-git-commit: c835a96b315d2c68b64869082fc626243dd006e9
workflow-type: tm+mt
source-wordcount: '3703'
ht-degree: 0%

---

# 작업 만들기 및 관리{#creating-and-managing-tasks}

Adobe Campaign을 사용하면 작업을 만들고 애플리케이션 내에서 직접 전체 라이프 사이클을 관리할 수 있습니다. 프로그램 및 캠페인 구현을 Adobe Campaign 운영자 또는 외부 서비스 제공자에게 할당된 작업으로 분류할 수 있습니다. 이 작업 모드에서는 모든 프로그램 참여자와 외부 참여자를 포함하는 개방형 공동 작업 환경을 만들 수 있습니다.

작업 목록 또는 캠페인 대시보드에서 작업을 만들고, 보고, 모니터링할 수 있습니다. 마케팅 계획, 프로그램 및 캠페인의 일정에서 보고 추적할 수도 있습니다.

작업은 캠페인에 연결되며, 종속성과 관련된 작업 등을 가질 수 있습니다. 각 작업에는 상태, 우선 순위, 예상 로드 및 관련 비용이 있습니다.

모든 작업은 **캠페인** 탭. 자세한 내용은 [액세스 작업](#accessing-tasks).

해당 항목이 속한 프로그램 일정에 표시될 수 있습니다.

![](assets/d_ncs_user_tasks_in_planning.png)

## 액세스 작업 {#accessing-tasks}

### 작업 표시 {#displaying-tasks}

작업은 을 통해 액세스할 수 있는 작업 목록에 표시됩니다 **[!UICONTROL Campaigns]** 탭.

![](assets/s_ncs_user_task_edit_view.png)

연결된 연산자의 모든 작업을 여기에서 볼 수 있습니다.

자세한 내용은 [작업의 실행 상태](#execution-status-of-a-task) 및 [작업의 진행 상태](#progress-status-of-a-task).

### 작업 필터링 {#filtering-tasks}

이 보기를 표시할 때는 자동으로 필터링되어 표시만 됩니다 **[!UICONTROL operator tasks]**. 창의 위쪽 섹션에 있는 필드를 사용하여 작업을 필터링할 수도 있습니다.

![](assets/s_ncs_user_task_filter_from_view.png)

### 작업 편집 {#editing-tasks}

작업을 클릭하여 편집합니다.

![](assets/s_ncs_user_task_edit_from_view.png)

## 새 작업 만들기 {#creating-a-new-task}

작업을 만들려면 **[!UICONTROL Tasks]** 링크 위치 **[!UICONTROL Campaigns]** 탭을 선택하고 **[!UICONTROL Create]**.

![](assets/s_ncs_user_task_create_new.png)

작업의 이름을 적어도 입력하고 연결된 캠페인을 선택합니다. 시작 및 종료 날짜도 지정해야 합니다. 이 세 가지 정보는 필수입니다.

클릭 **[!UICONTROL Save]** 작업을 만들려면

![](assets/s_ncs_user_task_create_simple.png)

캠페인의 대시보드를 통해 작업을 만들 수도 있습니다. 이 경우 만든 캠페인에 자동으로 연결됩니다.

![](assets/s_ncs_user_task_create_new_from_op.png)

작업이 만들어지면 캠페인 일정 및 작업 목록에 추가됩니다. 작업을 편집하려면 예약에서 선택하거나 작업 개요에서 해당 이름을 클릭한 다음 **[!UICONTROL Open]** 링크를 클릭합니다.

![](assets/s_ncs_user_task_edit_simple.png)

구성하려면 다음을 표시해야 합니다.

* 관리자 및 참여자: 참조 [관리자 및 참가자](#manager-and-participants).
* 생성 일정: 참조 [실행 일정](#execution-schedule).
* 약정된 비용: 참조 [비용 및 수입](#expenses-and-revenues).

검토자를 추가할 수도 있습니다( [검토자](#reviewers)) 및 참조된 문서(참조 [참조된 문서](#documents-referenced)).

작업 라이프 사이클은 [라이프 사이클](#life-cycle).

### 관리자 및 참가자 {#manager-and-participants}

작업을 담당하는 연산자만 작업을 닫을 수 있습니다.

기본적으로 Adobe Campaign 연산자가 작업을 만들면 자동으로 해당 작업에 할당됩니다. 다른 연산자를 선택하려면 **[!UICONTROL Assigned to]** 필드.

![](assets/s_ncs_user_task_edit_simple_general_tab.png)

>[!NOTE]
>
>운영자 관리는에 자세히 설명되어 있습니다. [이 섹션](../../v8/start/permissions.md).

작업 수행과 관련된 연산자를 지정할 수 있습니다. 이 연산자는 작업을 닫을 권한이 없습니다. 할당된 작업만 승인할 수 있습니다.

이러한 ID는 **[!UICONTROL Resources]** 아이콘을 클릭합니다. 클릭 **[!UICONTROL Add]** 관련 연산자를 선택합니다.

![](assets/s_ncs_user_task_add_resources.png)

클릭 **[!UICONTROL Ok]** 그런 다음 사용률을 입력합니다. 작업 실행 기간 동안 연산자에 할당된 로드를 나타냅니다. 이 비율은 표시 전용이며 백분율로 표시됩니다.

예를 들어 실행 일정이 10일로 설정된 작업의 경우 사용 비율이 50%인 연산자가 10일 동안 작업 시간의 절반을 이 작업에 동원됩니다.

각 연산자에 대해 스케줄링된 작업 로드와 실제 작업 로드를 입력할 수 있습니다. 이러한 기간은 정보 용도로만 사용됩니다.

미리 알림을 구성하여 해당 종료 날짜 이전에 작업에 관련된 모든 작업자에게 자동으로 전송됩니다.

를 통해 Adobe Campaign 운영자 프로필을 볼 수 있습니다 **[!UICONTROL Edit link]** 아이콘.

![](assets/s_ncs_user_task_edit_resource_profile.png)

운영자 대시보드를 사용하여 작업 로드(진행 중인 다른 작업)를 확인할 수 있습니다.

![](assets/s_ncs_user_task_edit_resource_planning.png)

### 검토자 {#reviewers}

참여자 외에, 담당자가 작업을 마감한 후 작업을 검토할 연산자를 정의할 수 있습니다. 이렇게 하려면 **[!UICONTROL Enable task approval]** 페이지의 왼쪽 아래 섹션에 있는 옵션 **[!UICONTROL Resources]** 창을 엽니다. 개별 연산자, 연산자 그룹 또는 연산자 목록일 수 있습니다.

![](assets/s_ncs_user_task_edit_resource_validation.png)

연산자 목록을 지정하려면 **[!UICONTROL Edit...]** 첫 번째 검토자의 오른쪽에 연결하고 아래 표시된 대로 필요한 만큼 연산자를 추가합니다.

![](assets/s_ncs_user_task_edit_resource_operators.png)

검토자 구성 창의 아래 섹션에서 작업에 대한 승인 일정을 정의할 수 있습니다. 기본적으로 검토자는 제출 날짜부터 3일을 시작하여 작업을 승인합니다. 미리 알림을 구성하여 승인 마감 시간 전에 관련 운영자에게 자동으로 보낼 수 있습니다.

![](assets/s_ncs_user_edit_op_valid_calendar.png)

다른 작업자가 이미 이 작업을 수행하도록 지정된 경우에도 작업 담당자는 자신에게 승인 작업을 할당할 수 있습니다. 검토자가 정의되지 않은 경우 작업을 담당하는 사람에게 알림이 전송됩니다. 다른 모든 Adobe Campaign 연산자 **[!UICONTROL Administrator]** 권한을 통해 작업을 승인할 수도 있습니다. 하지만 알림을 받지 않습니다.

### 참조된 문서 {#documents-referenced}

추가할 수 있습니다 [문서 및 마케팅 리소스](managing-marketing-resources.md) 작업을 수행할 수 있습니다. 이렇게 하려면 작업을 열고 **[!UICONTROL Documents]** 아이콘을 클릭합니다.

클릭 **[!UICONTROL Add]** 작업에 추가할 문서를 선택합니다. 마케팅 리소스에 동일한 프로세스를 적용합니다.

![](assets/s_ncs_user_task_edit_documents.png)

참조된 문서는 작업 대시보드뿐만 아니라 작업에 관련된 운영자에게 전송된 알림에 나타납니다.

![](assets/s_ncs_user_task_notification_documents.png)

### 실행 일정 {#execution-schedule}

작업의 유효 기간은 **[!UICONTROL Start]** 및 **[!UICONTROL End]** 필드. 예약된 로드는 기간 동안 수행할 작업 로드를 나타냅니다. 일 또는 시간 단위로 표시됩니다.

>[!NOTE]
>
>작업의 라이프 사이클은 [라이프 사이클](#life-cycle).

다음 **[!UICONTROL Workload performed]** 일 및 시간 단위로 표시되는 필드에서는 예약된 작업 로드와 관련된 작업 진행 상황을 수동으로 업데이트할 수 있습니다.

![](assets/s_ncs_user_task_percentage_done_enter.png)

다음 **[!UICONTROL Progress status]** 백분율로 표시되는 작업의 경우, 관련 연산자가 수행한 작업에 따라 자동으로 업데이트됩니다. 수동으로 입력할 수 있습니다.

이 정보는 작업 대시보드에서 볼 수 있습니다.

![](assets/s_ncs_user_task_percentage_done_from_dashboard.png)

캠페인 탭에도 표시됩니다.

![](assets/s_ncs_user_task_percentage_done_from_op.png)

작업 실행 일정 종료 날짜에 도달했지만 작업이 완료되지 않으면 작업이 수행됩니다 **[!UICONTROL Late]**. 경고 연산자에도 경고 메시지가 표시됩니다.

자세한 내용은 [작업의 진행 상태](#progress-status-of-a-task).

### 비용 및 수입 {#expenses-and-revenues}

각 태스크에 대한 관련 비용과 예측 수익을 정의할 수 있습니다. 이러한 데이터는 계산된 다음 작업이 첨부된 캠페인에 대해 통합됩니다.

이 정보를 지정하려면 **[!UICONTROL Expenses and revenue]** 아이콘을 클릭합니다.

![](assets/s_ncs_user_task_edit_costs.png)

기본적으로 부과된 예산은 작업이 첨부된 캠페인의 예산입니다. 작업 세부 사항에 표시됩니다.

>[!NOTE]
>
>비용 및 예산에 대한 자세한 내용은 [이 섹션](../campaigns/providers--stocks-and-budgets.md#cost-commitment--calculation-and-charging).

이 창에서 도달할 목표를 정의할 수도 있습니다. 목표들은 태스크에 대한 예측 수익 관점에서 표시됩니다.

### 서비스 공급자 {#service-providers}

외부 서비스 공급자가 작업 관리에 관여할 수 있습니다.

이렇게 하려면 작업 속성을 편집하고 관련 서비스 공급자를 선택합니다. 서비스 제공자와 연관된 비용 범주는 창의 중앙 섹션에 자동으로 나열됩니다.

태스크 실행과 관련된 원가 범주를 선택합니다. 이렇게 하려면 원가 유형을 선택하고 필요한 경우 추가 요금을 추가합니다.

![](assets/s_ncs_user_task_edit_simple_costs_tab.png)

>[!NOTE]
>
>예산 및 비용 관리 방법은 [비용 제어](controlling-costs.md).

서비스 공급자를 선택하면 작업 대시보드에 표시됩니다.

![](assets/s_ncs_user_task_supplier_view.png)

### 지연 작업 {#late-tasks}

상태가 로 변경되지 않고 종료 날짜에 도달하면 작업이 늦습니다. **[!UICONTROL Finished]**. 기본적으로 작업이 늦으면 연산자에게 경고가 표시되지 않습니다. 알림 전자 메일의 게재를 구성할 수 있습니다. 작업자가 작업에 참여하지 않더라도 모든 작업자에게 알림을 받을 수 있습니다.

로 이동합니다. **[!UICONTROL Resources]** 상자를 열고 연산자를 **[!UICONTROL Assignation]** 필드. 여러 사용자에게 알리려면 연산자 그룹을 선택합니다.

![](assets/mrm_task_alert_if_late.png)

### 초기 알림 {#initial-notifications}

나중에 시작 날짜가 있는 작업을 만들거나 수정하면 Adobe Campaign에서 작업 담당자에게 전자 메일을 보내어 작업 시작 시점을 알려줍니다.

![](assets/mrm_task_first_notif.png)

그러나 생성 중인 작업이 오래 걸리는 경우 작업이 시작되기 전에 알림 전송을 예약하는 것이 좋을 수 있습니다. 예를 들어 작업이 한 달에 시작하는 경우 작업이 시작되기 1주일 전에 담당자에게 알릴 수 있습니다.

알림을 예약하려면 **[!UICONTROL Resources]** 상자 및 **[!UICONTROL Initial notification]** 필드.

![](assets/mrm_task_alert_before.png)

* 캠페인 내 작업의 경우 특정 날짜 및 시간을 선택합니다.
* 캠페인 템플릿 내의 작업의 경우, 알림 시간은 작업이 시작되기 전 남은 시간으로 표시됩니다(예를 들어, **[!UICONTROL Initial notification]** 필드, 작업 시작 날짜보다 2일 전에 이메일이 전송됩니다.

알림을 예약한 경우 작업을 저장하면 Adobe Campaign에서 즉시 알림을 전송하도록 오퍼를 유지합니다. 전송을 결정할 수 있으며 이렇게 해도 예약된 알림이 대체되지 않습니다.

### 프로그램에 연결된 작업 {#task-linked-to-a-program}

프로그램에서 직접 작업을 만들어 특정 캠페인이 아닌 전체 조직과 관련된 작업을 관리할 수 있습니다(예: 프로그램 내에서 예정된 캠페인의 주제를 논의하기 위한 모임). 작업이 프로그램 일정에 나타납니다.

프로그램에 직접 연결된 작업을 만들려면

1. 프로그램 일정을 엽니다. 홈 페이지에서 **[!UICONTROL Campaigns > Browse > Other choices > Programs]**. 전체 프로그램 스케줄이 창의 오른쪽 섹션에 열립니다.
1. 예약에서 원하는 프로그램을 클릭합니다. 그 안에 프로그램이 나타납니다.
1. 이 창에서 **[!UICONTROL Open]**. 프로그램 일정이 열립니다.
1. 을(를) 클릭합니다. **[!UICONTROL Add]** 오른쪽에 있는 일정 위에 있는 버튼을 클릭한 다음 **[!UICONTROL Add a task]**.

![](assets/mrm_task_create_from_prg.png)

### 운영자 가용성 {#operator-availability}

작업 대시보드에서 운영자 이름 옆에 있는 아이콘은 작업이 적용되는 기간 동안 다른 작업 또는 이벤트에서 이미 작업 중임을 나타냅니다. 연산자가 담당하거나 관련된 작업이 **[!UICONTROL Assigned to]** 필드 또는 작업 **[!UICONTROL Resources]** 상자.

![](assets/mrm_task_alert_operator_busy.png)

### 워크플로우의 작업 {#task-in-a-workflow}

사용 **[!UICONTROL Task]** 캠페인 워크플로우의 요소를 사용하면 작업이 승인되었는지 여부에 따라 두 가지 시나리오를 정의할 수 있습니다.

![](assets/mrm_task_in_workflow.png)

캠페인 워크플로우에서 **[!UICONTROL Task]** 활동은 **[!UICONTROL Flow control]** 탭.

## 작업 유형 {#types-of-task}

캠페인을 통해 작업을 만들 때 특정 작업을 만들 수 있습니다. 선택한 템플릿에 작업 유형이 정의됩니다.

![](assets/s_ncs_user_task_select_template.png)

다음 작업을 예약할 수 있습니다.

* [작업 제어](#control-tasks),
* [그룹화 작업](#grouping-task),
* [그룹화 작업](#grouping-task),
* [알림 작업](#notification-task).

>[!NOTE]
>
>**[!UICONTROL Control task]** 및 **[!UICONTROL Grouping]** 작업을 만들 수 있습니다. **전용** campaign 대시보드 를 통해 을 참조하십시오.\
>할당된 연산자의 작업 맵에 표시됩니다. 자세한 내용은 [액세스 작업](#accessing-tasks).

### 작업 제어 {#control-tasks}

A **[!UICONTROL Control task]** 은(는) 배달 승인에 연결되어 있습니다. 타겟팅, 컨텐츠, 추출 파일, 예산 또는 증명 승인.

![](assets/s_ncs_user_task_new_control.png)

생성된 작업은 캠페인 대시보드에 추가됩니다.

![](assets/s_ncs_user_task_edit_from_board.png)

그런 다음 편집하고 매개 변수를 지정할 수 있습니다.

### 마케팅 리소스 만들기 작업 {#marketing-resource-creation-task}

마케팅 리소스 만들기 작업은 마케팅 리소스의 작성 및 게시를 관리하는 데 사용할 수 있습니다. 리소스 자체가 아니라 작업을 통해 리소스를 관리하는 경우 다음을 수행할 수 있습니다.

* 캠페인을 통해 리소스 생성 프로세스를 제어합니다.
* 스케줄에서 리소스 생성 프로세스를 봅니다.
* 리소스 만들기 프로세스(미리 알림, 알림)를 관리합니다.
* 자원 생성과 관련된 비용을 계산하고 제어합니다.
* 작업을 통해 리소스를 승인하고 게시합니다(관련 옵션이 활성화된 경우).

#### 작업과 연결된 리소스 간의 상호 작용 {#interaction-between-the-task-and-its-linked-resource}

마케팅 리소스 생성 작업은 마케팅 리소스 생성 작업에 연결된 리소스와 상호 작용합니다. 이것의 의미는 다음과 같습니다.

* 자원 생성 일정 및 이에 연결된 비용은 작업을 통해 관리됩니다.
* 연산자는 일반(다운로드 또는 업로드, 잠금 및 잠금 해제)과 같은 리소스에서 작업할 수 있습니다. 작업에 영향을 주지 않습니다.
* 작업을 통해 리소스 승인 및 게시를 수행할 수 있습니다. if **[!UICONTROL Publish the marketing resource]** 옵션이 활성화되면 작업이 완료되면 리소스가 승인되고 자동으로 게시됩니다. 옵션이 활성화되지 않으면 작업과 리소스가 상호 작용하지 않습니다. 한 사람에 대해 행동하는 것은 다른 사람에게 영향을 주지 않는다.

   일련의 연결된 작업을 사용하여 전체 승인 주기를 정의할 수 있습니다. 을(를) 확인합니다. **[!UICONTROL Publish the marketing resource]** 마지막 작업에 대해서만 옵션을 선택합니다. 리소스를 게시하려면 모든 작업을 완료해야 합니다. 또한 하위 마케팅 리소스 작업을 만들면 하위 작업에서 리소스가 자동으로 선택됩니다.

   * **리소스 사용**: 승인을 위해 리소스를 제출하거나 승인하면 이러한 작업은 작업에 영향을 주지 않습니다.
   * **작업 사용**: if **[!UICONTROL Publish the marketing resource]** 작업에서 옵션을 선택하면 작업이 완료되면 리소스가 승인되고 자동으로 게시됩니다(위 참조). 옵션을 선택하지 않으면 작업과 리소스가 상호 작용하지 않습니다. 한 사람에 대해 행동하는 것은 다른 사람에게 영향을 주지 않는다.

#### 마케팅 리소스 만들기 작업 구성 {#configuring-a-marketing-resource-creation-task}

작업을 검토하는 사람은 리소스에 정의된 컨텐츠를 검토하는 동일한 사람이 필요하지 않습니다. 그러나 **[!UICONTROL Publish the marketing resource]** 옵션을 선택합니다(아래 참조). 작업을 마치면 자동으로 리소스를 승인하거나 검토자가 정의되지 않은 경우 작업 관리자가 리소스 콘텐츠를 승인할 수 있습니다.

![](assets/mrm_task_asset_creation.png)

에서 **[!UICONTROL Marketing resource]** 필드에서 이 작업을 통해 관리할 리소스를 정의합니다. 다음을 수행할 수 있습니다.

* 기존 리소스를 선택합니다. 드롭다운 목록은 상태가 있는 모든 리소스를 제공합니다 **[!UICONTROL Being edited]**.
* 리소스 만들기: 를 클릭합니다. **[!UICONTROL Select the link]** 아이콘을 클릭한 다음 **[!UICONTROL Create]** 아이콘.

다음 **[!UICONTROL Publish the marketing resource]** 옵션을 사용하면 리소스 게시를 자동화할 수 있습니다. 작업이 **[!UICONTROL Finished]**&#x200B;로 설정하면 리소스의 상태가 자동으로 로 전환됩니다. **[!UICONTROL Published]**&#x200B;을 지정하면 승인 또는 승인을 위해 제출되지 않은 경우에도 작업을 완료하는 검토자가 리소스에 정의된 컨텐츠 검토자가 아닌 경우입니다.

다음 **[!UICONTROL Publish the resource]** 버튼을 사용할 수 있게 되고 리소스 게시 검토자가 게시할 준비가 되었음을 알리는 알림 이메일을 받게 됩니다. 에서 **[!UICONTROL Edit > Tracking]** 탭, 작업 검토자가 검토 및 게시할 수 있습니다. 리소스 사후 처리 워크플로우가 정의된 경우 지금 실행됩니다.

![](assets/mrm_resource_audit_tab.png)

### 그룹 작업 {#grouping-task}

다음 **[!UICONTROL Grouping task]** 유형 작업을 사용하면 여러 작업을 그룹화하고 진행 상황과 승인 관리를 동기화할 수 있습니다.

그룹핑 태스크에는 연결된 비용 또는 자원이 없습니다.

그룹화 작업에 그룹화된 모든 작업은 자체 대시보드에서 볼 수 있습니다. 이렇게 하면 작업 목록을 필터링하여 원하는 작업만 표시할 수 있습니다.

그룹화 작업의 링크를 통해 그룹화된 작업을 쉽게 만들 수 있습니다.

그룹화 작업을 기반으로 그룹화된 작업을 만들려면 캠페인 대시보드로 이동하여 그룹화 작업 이름을 클릭하여 설명을 표시한 다음 를 클릭합니다 **[!UICONTROL Add a task]**.

![](assets/mrm_task_grouped_create.png)

그러나 그룹화 작업에 연결할 작업을 이미 만든 경우에는 **[!UICONTROL Linked to]** 필드 **[!UICONTROL Properties]** 상자.

![](assets/s_ncs_user_task_group_with.png)

### 알림 작업 {#notification-task}

알림 작업을 사용하면 운영자, 운영자 그룹, 서비스 공급자 등에 대한 이메일 게재 일정을 예약할 수 있습니다. 이렇게 하면 미리 알림을 예약할 수 있습니다. 예를 들어, 캠페인이 곧 완료되고 있음을 다른 사람에게 알리거나 캠페인 시작 전에 문서를 전송하여 운영자가 준비할 수 있도록 할 수 있습니다. 즉, 캠페인이나 프로그램 내에서 커뮤니케이션을 추적하고 이를 통해 수행한 작업을 자세히 확인할 수 있습니다.

#### 라이프 사이클 {#life-cycle}

알림 작업은 승인이 필요하지 않습니다. 표준 작업보다 라이프 사이클이 단순하다는 뜻이다.

![](assets/mrm_task_notif_lifecycle.png)

알림 작업에는 다음 상태가 있을 수 있습니다.

* **[!UICONTROL Scheduled]** 이메일을 보낼 때까지
* **[!UICONTROL In progress]** 전자 메일이 전송되고 종료 날짜가 될 때까지
* **[!UICONTROL Finished]** 종료 날짜에 도달하면

#### 구성 {#configuration}

![](assets/mrm_task_notif_dashboard.png)

생성 중에 작업에 다음 요소를 입력해야 합니다.

* **[!UICONTROL Assigned to]** : 이메일을 받을 운영자 또는 운영자 그룹입니다. 전자 메일이 전송되면 작업을 다시 할당하면 새 연산자에게 전자 메일이 전송되지 않습니다(이 경우 작업을 다시 초기화하고 시작 날짜를 변경해야 함).
* **작업 시작 날짜**: 알림 이메일을 전송할 날짜입니다. 이 날짜는 작업 기록 시 나중에 수행해야 합니다.
* **작업 종료 날짜**: 작업 상태가 **[!UICONTROL Finished]**. 기본적으로 종료 날짜는 시작 날짜와 동일합니다. 그러나 작업에 기간을 할당하면 필요한 경우 작업자가 일정에 따라 작업해야 하는 시간을 나타낼 수 있습니다.
* **[!UICONTROL Description]** : 여기에 입력한 텍스트가 알림 전자 메일 본문에 나타납니다.

   ![](assets/mrm_task_notif_dashboard_msg.png)

작업 및 알림 전자 메일에 첨부 파일을 추가할 수 있습니다. 이렇게 하려면 **[!UICONTROL Documents]** 아이콘 을 클릭하여 제품에서 사용할 수 있습니다.

## 라이프 사이클 {#life-cycle-1}

### 작업 간 링크 {#links-between-tasks}

다음 **[!UICONTROL Properties]** 각 작업의 버튼을 사용하면 캠페인에서 작업 사이의 링크를 정의할 수 있습니다. 그룹화 작업을 사용하여 작업을 하위 작업으로 분할할 수 있습니다( [연결된 작업](#linked-tasks)) 또는 작업 간의 종속성을 정의하거나 정의합니다( 참조). [그룹화 작업](#grouping-tasks)).

#### 연결된 작업 {#linked-tasks}

를 사용하십시오 **[!UICONTROL Linked task]** 그룹화 작업과 작업을 연결할 필드입니다. 자세한 내용은 [작업 유형](#types-of-task).

다음 예에서는 타겟팅 승인이 4개의 하위 작업으로 분류됩니다.

![](assets/s_ncs_user_task_linked_tasks.png)

각 하위 작업은 기본 작업에 연결된 표준 작업입니다.

![](assets/s_ncs_user_task_depends_on.png)

#### 그룹 작업 {#grouping-tasks}

를 사용하십시오 **[!UICONTROL Grouped to]** 작업 실행을 위한 필드는 다른 작업 실행에 따라 다릅니다.

![](assets/s_ncs_user_task_group_with.png)

작업 간의 종속성은 캠페인 대시보드의 화살표로 표시됩니다.

![](assets/s_ncs_user_task_dependencies_from_board.png)

그룹화된 작업의 경우 Adobe Campaign에서는 상위 작업의 종료 날짜를 하위 작업에 시작 날짜로 자동으로 할당합니다. 예를 들어 **초대 만들기** 작업은 10월 15일 오후 3시 30분에 종료됩니다. **초대 전자 메일 보내기** 하위 작업은 10월 15일 오후 3시 30분에 시작됩니다.

또한 상위 작업의 끝을 연기하면 일부 하위 작업이 영향을 받을 수 있습니다. 상태는 하위 작업입니다. **[!UICONTROL Scheduled]** 및 시작 날짜가 상위 작업의 새 종료 날짜보다 이전입니다. 작업 기간은 동일하게 유지됩니다. 하위 작업의 시작 날짜가 상위 작업의 새 종료 날짜보다 늦은 경우 하위 작업은 영향을 받지 않습니다.

**예제**

10월 9일 오후 5시에 종료될 예정인 상위 태스크에는 두 개의 하위 태스크인 태스크 A와 태스크 B가 있습니다. 태스크 A는 10월 10일 오후 2시에 시작될 예정이며 태스크 B는 10월 12일 오전 8시에 시작하도록 예정되어 있습니다.

상위 작업을 연기합니다. 10월 11일 오후 1시에 끝납니다 작업 A만 연기되고 10월 11일 오후 1시에 시작됩니다.

![](assets/mrm_task_parent_postpones_child.png)

### 작업의 실행 상태 {#execution-status-of-a-task}

작업 상태는 작업 맵에서 볼 수 있습니다. 작업의 실행 상태는 운영자 작업에 따라 자동으로 업데이트됩니다.

작업은 다음과 같습니다. **[!UICONTROL Scheduled]**, **[!UICONTROL In progress]**, **[!UICONTROL Finished]**, **[!UICONTROL Canceled]**, **[!UICONTROL Pending approval]** 또는 **[!UICONTROL Rejected]**.

* 작업이 만들어지면 **[!UICONTROL Scheduled]** 시작 날짜가 미래인 경우 이 상태는 시작 날짜가 될 때까지 유지됩니다.
* 작업이 시작되면 **[!UICONTROL In progress]**. 작업을 담당하는 사람이 작업을 닫으면 **[!UICONTROL Finished]**.
* 검토자가 정의된 경우 해당 작업이 **[!UICONTROL Pending approval]** 관리자가 닫으면 검토자가 승인할 때까지 검토자가 거부하면 작업이 **[!UICONTROL Rejected]**.
* 대시보드 또는 을 통해 해당 작업을 담당하는 사람이 작업을 취소할 수 있습니다 **[!UICONTROL Task map]** 다음을 클릭하여 **[!UICONTROL Cancel]** 버튼을 클릭합니다.
* 작업을 예약하려면 나중에 시작 날짜를 입력합니다. 그런 다음 작업 수행과 관련된 Adobe Campaign 운영자에게 첫 번째 알림을 보낼 수 있습니다. 자세한 내용은 [작업 수명 주기 완료](#complete-task-life-cycle).

>[!NOTE]
>
>* 작업 상태가 자동으로 업데이트됩니다.
>* 유효 기간이 끝났더라도 닫히지 않은 작업은 진행 중인 작업 목록에 계속 나타납니다. 경고 메시지가 작업자에게 작업이 지연되었음을 알립니다.
>


### 작업의 진행 상태 {#progress-status-of-a-task}

실행 상태 외에 작업을 진행 상태와 연결할 수 있습니다. **[!UICONTROL Late]**, **[!UICONTROL To approve]**, **[!UICONTROL To do today]** 또는 **[!UICONTROL To do this week]**. 이 정보는 작업 일정에 따라 자동으로 입력됩니다.

프로세스 또는 진행 상태별로 작업 목록을 필터링할 수 있습니다.

자세한 내용은 [작업 액세스](#accessing-tasks).

### 작업 수명 주기 완료 {#complete-task-life-cycle}

다음은 담당 담당자가 참가자 및 검토자를 정의한 전체 작업 수명 주기 단계입니다.

1. 담당자는 작업을 만들고 다양한 필드를 입력합니다. 자세한 내용은 [새 작업 만들기](#creating-a-new-task).

   작업을 만들고 편집할 때 **나중에 예약됨** (작업 시작 날짜에 도달하지 않은 경우) 참가자와 관리자에게 새 작업이 예약되었음을 알리는 알림을 보낼 수 있습니다.

   ![](assets/s_ncs_user_task_planed_send_message.png)

   이 첫 번째 알림을 보내려면 **[!UICONTROL Yes]**. 이 알림은 다음 작업에 대해 알려 주며 컨텐츠에 대한 세부 정보와 마감일까지 남은 일 수를 포함합니다.

   나중에 작업을 만들고 예약할 때 상태는 다음과 같습니다 **[!UICONTROL Scheduled]**.

1. 작업 시작 날짜에 담당자와 참가자는 작업이 시작되었음을 알리는 알림을 받습니다. 상태가 **[!UICONTROL In progress]**.
1. 사용자에게 지정된 섹션을 완료한 후 참여자가 다음 중 하나를 사용하여 작업을 승인할 수 있습니다.

   * 알림 이메일을 통해 전송됩니다.
   * 콘솔 또는 웹 인터페이스를 통해 작업 대시보드에서 작업을 수행할 수 있습니다.

      ![](assets/s_ncs_user_task_start_rea.png)

1. 참가자가 작업을 승인할 때마다 작업의 진행 상태가 업데이트됩니다.

   ![](assets/s_ncs_user_task_percentage_done_op.png)

1. 검토자는 운영자가 자신에게 지정된 섹션을 완료했음을 알리는 알림 이메일을 수신하게 됩니다.

   작업 대시보드의 진행 상황을 추적할 수 있습니다.

   ![](assets/s_ncs_user_task_follow_from_dashboard.png)

1. 작업을 담당하는 사람이 작업을 완료했다고 결정하면 작업이 시작될 때 보낸 알림 이메일의 링크, 콘솔 또는 인터페이스를 사용하여 작업을 닫을 수 있습니다.

   ![](assets/s_ncs_user_task_console_ressource_validation.png)

   >[!NOTE]
   >
   >작업 담당자는 승인이 없는 경우에도 언제든지 작업을 닫을 수 있습니다. 진행 상태가 자동으로 100%로 변경됩니다.

1. 작업 상태가 **[!UICONTROL To approve]**&#x200B;로 설정되면 알림이 검토자에게 전송됩니다.

   알림 이메일, 콘솔 또는 웹 인터페이스를 통해 작업을 승인합니다.

   캠페인 대시보드를 통해 작업할 수 있습니다.

   ![](assets/s_ncs_user_task_console_validation.png)

   작업 승인 단추를 사용할 수도 있습니다.

   ![](assets/s_ncs_user_task__validation.png)

   >[!NOTE]
   >
   >작업 상태는 **[!UICONTROL To approve]** 활성화한 경우 **[!UICONTROL Enable task validation]** 옵션 **[!UICONTROL Resources]** 작업의 창.\
   >검토자가 작업을 거부하면 검토자의 상태가 **[!UICONTROL Rejected]**&#x200B;로 설정되면 작업 라이프 사이클이 자동으로 다시 시작됩니다.

1. 작업 상태가 **[!UICONTROL Finished]**. 알림은 관련된 모든 사람에게 전송됩니다.

   >[!NOTE]
   >
   >작업이 완료되면 관리자가 해당 라이프 사이클을 다시 초기화할 수 있습니다. 이렇게 하려면 작업을 열고 **[!UICONTROL Reset task to execute it again...]** 대시보드 하단에 연결합니다.
