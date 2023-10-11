---
product: campaign
title: 표준 시간대 관리
description: 표준 시간대 관리
feature: Workflows
role: User, Admin
exl-id: 04b7638d-55dd-4317-b605-5d618ef014ba
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 4%

---

# 표준 시간대 관리{#managing-time-zones}

Adobe Campaign을 사용하면 동일한 인스턴스로 관련된 다양한 국가 간의 시간 차이를 관리할 수 있습니다. 적용된 구성은 인스턴스 생성 중 구성됩니다.

워크플로우에서 활동 실행 일정을 조정하고 특정 시간대를 활동 또는 전체 워크플로우에 연결할 수 있습니다. 이 구성은 파일을 가져올 때 또는 배달 예약의 프레임워크 내에서 유용할 수 있습니다.

## 실행 예약 {#execution-scheduling}

스케줄러를 사용하여 작업 실행을 예약할 수 있습니다( 참조) [스케줄러](scheduler.md)). 이 기능을 제공하는 활동에서 사용할 수 있는 예약 옵션을 사용할 수도 있습니다. 다음 활동은 다음을 제공합니다. **[!UICONTROL Schedule]** 탭: **[!UICONTROL File collector]**, **[!UICONTROL File transfer]**, **[!UICONTROL Web download]**, **[!UICONTROL Email reception]** 및 **[!UICONTROL SMS]**&#x200B;등

모든 예약된 작업, 즉 예약 옵션이 있는 모든 활동에 대해 적용할 시간대를 선택할 수 있습니다. 시간대는 다음을 통해 선택됩니다. **[!UICONTROL Advanced]** 관련 활동의 탭:

![](assets/wf-timezone-in-a-box.png)

가능한 값:

* 서버 시간대

  Adobe Campaign 애플리케이션 서버의 시간대를 사용합니다.

* 사용자 시간대

  워크플로우를 실행하는 Adobe Campaign 연산자의 시간대를 사용합니다.

* 데이터베이스 시간대

  사용된 데이터베이스 서버의 시간대를 사용합니다.

* 특정 시간대

  선택한 시간대를 사용합니다.

다음과 같은 경우 **[!UICONTROL By default]** 값을 선택하면 워크플로의 시간대가 적용되거나, 그렇지 않으면 애플리케이션 서버의 시간대가 적용됩니다.

## 활동에 시간대 연결 {#linking-a-time-zone-to-an-activity}

다음 **[!UICONTROL Advanced]** 워크플로우 활동의 탭에서는 시간대를 선택할 수 있습니다. 대부분의 시간대에서는 워크플로우의 시간대로 충분하지만, 날짜를 올바른 시간대로 연결하기 위해 데이터 가져오기와 같은 특정 활동에 대해 워크플로우를 지금부터 다시 오버로드해야 할 수 있습니다.
