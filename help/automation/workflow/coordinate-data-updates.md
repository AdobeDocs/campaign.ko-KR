---
product: campaign
title: 데이터 업데이트 조정
description: 데이터 업데이트 조정
feature: Workflows, Data Management
role: User
exl-id: 9faf7ee7-07c1-415b-b234-a945994792c7
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 4%

---

# 데이터 업데이트 조정{#coordinating-data-updates}



이 사용 사례에서는 워크플로우의 여러 실행을 사용할 때 수반되는 업데이트를 관리할 수 있는 워크플로우 만들기에 대해 자세히 설명합니다.

다른 업데이트 작업을 실행하기 전에 업데이트 프로세스가 종료되었는지 확인하는 것이 목적입니다. 이를 위해 인스턴스 변수를 설정하고, 인스턴스가 실행 중인지 워크플로 테스트를 수행하여 워크플로 실행을 계속하고 업데이트를 수행할지 여부를 결정합니다.

![](assets/uc_dataupdate_wkf.png)

이 워크플로우는 다음과 같이 구성됩니다.

* 특정 빈도에서 워크플로우를 실행하는 **스케줄러** 활동.
* 워크플로우가 이미 실행 중인지 확인하는 **Test** 활동.
* 워크플로우가 아직 실행되지 않은 경우 **쿼리** 및 **데이터 업데이트** 활동을 실행한 다음 워크플로우 인스턴스 변수를 false로 다시 초기화하는 **End** 활동을 실행합니다.
* 워크플로우가 이미 실행 중인 경우 **End** 활동.

워크플로우를 빌드하려면 아래 단계를 수행합니다.

1. **스케줄러** 활동을 추가한 다음 필요에 따라 빈도를 구성하십시오.
1. **Test** 활동을 추가하여 워크플로우가 이미 실행 중인지 확인한 다음 아래와 같이 구성하십시오.

   >[!NOTE]
   >
   >&quot;isRunning&quot;은 이 예제에 대해 선택한 인스턴스 변수 이름입니다. 기본 제공 변수가 아닙니다.

   ![](assets/uc_dataupdate_test.png)

1. **End** 활동을 **No** 포크에 추가하십시오. 이 방법에서는 워크플로우가 이미 실행 중인 경우 아무것도 실행되지 않습니다.
1. **예** 포크에 원하는 활동을 추가합니다. 이 예제에서는 **쿼리** 및 **데이터 업데이트** 활동을 수행합니다.
1. 첫 번째 활동을 연 다음 **[!UICONTROL Advanced]** 탭에서 **instance.vars.isRunning = true** 명령을 추가합니다. 이 방법으로 인스턴스 변수는 실행 중으로 설정됩니다.

   ![](assets/uc_dataupdate_query.png)

1. **[!UICONTROL Yes]** 포크의 끝에 **End** 활동을 추가한 다음 **[!UICONTROL Advanced]** 탭에서 **instance.vars.isRunning = false** 명령을 추가합니다.

   이 방법을 사용하면 워크플로우가 실행되는 동안에는 작업이 실행되지 않습니다.

   ![](assets/uc_dataupdate_end.png)

**관련 항목:**

* [동시 다중 실행 방지](monitor-workflow-execution.md#preventing-simultaneous-multiple-executions)
* [데이터 업데이트 활동](update-data.md)
