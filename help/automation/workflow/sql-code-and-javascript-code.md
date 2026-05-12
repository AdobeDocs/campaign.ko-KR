---
product: campaign
title: SQL 코드 및 JavaScript 코드
description: SQL 및 JavaScript 코드 워크플로우 활동에 대해 자세히 알아보기
feature: Workflows
Role: User
level: Experienced
version: Campaign v8, Campaign Classic v7
exl-id: 8c385847-a320-4cd9-9048-2bf9daf2ee07
TQID: https://experienceleague.adobe.com/J1oZUE7vCyJvodf0-09QoG24gWY9P9sSgqsH7rXibgk
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 9%

---

# SQL 코드 및 JavaScript 코드{#sql-code-and-javascript-code}

## SQL 코드 {#sql-code}

**[!UICONTROL SQL code]** 활동은 SQL 스크립트를 실행합니다. 스크립트는 JST 템플릿입니다.

![](assets/sql_code.png)

* **[!UICONTROL Script]**

  편집기의 중앙 영역에는 실행할 스크립트가 포함되어 있습니다. 이 스크립트는 JST 템플릿이므로 워크플로우 컨텍스트에 따라 구성할 수 있습니다.

* **[!UICONTROL Processing errors]**

  [처리 오류](monitor-workflow-execution.md#processing-errors)를 참조하세요.

### 중요 정보 {#important-notes}

8.9.1부터 **[!UICONTROL SQL code]** 및 **[!UICONTROL SQL Data Management]** 워크플로우 활동이 개선되어 PostgreSQL 데이터베이스를 더 잘 보호하고 Campaign에서 사용자 지정 SQL을 실행할 때 워크플로우가 원활하게 실행됩니다. 다음은 오류가 발생한 경우 따라야 할 몇 가지 모범 사례입니다.

옵션은 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**&#x200B;에서 사용할 수 있습니다. 오류 발생 시 두 가지 솔루션을 사용할 수 있습니다.

**솔루션 1**

`XtkSecurity_FeatureFlag_SqlSensitive`을(를) `0`(으)로 설정합니다. 기능이 비활성화되었습니다.

**솔루션 2**

`XtkSecurity_SqlSensitive_Methods`을(를) 수정합니다. `<method name="TRUNCATE" action="block"/>`을(를) `<method name="TRUNCATE" action="warn"/>`(으)로 변경할 수 있습니다

VACUUM FULL, REINDEX, CREATE INDEX, DROP INDEX와 같은 다른 방법도 데이터베이스 무결성을 보호하기 위해 기본적으로 차단됩니다. 차단 대신 경고로 설정하려면 주의하십시오. 이러한 메서드는 실행 시 데이터베이스 성능에 심각한 영향을 줄 수 있습니다.

## JavaScript 코드 및 고급 JavaScript 코드 {#javascript-code}

**[!UICONTROL JavaScript code]** 및 **[!UICONTROL Advanced JavaScript code]** 활동은 워크플로우의 컨텍스트에서 JavaScript 스크립트를 실행합니다. 스크립팅에 대한 자세한 내용은 다음 섹션을 참조하십시오.

* [JavaScript 스크립트 및 템플릿](javascript-scripts-and-templates.md)
* [워크플로의 JavaScript 코드 예](javascript-in-workflows.md)

### 실행 지연 {#exec-delay}

20.2 릴리스부터 **[!UICONTROL JavaScript code]** 및 **[!UICONTROL Advanced JavaScript code]** 활동에 실행 지연이 추가되었습니다. 기본적으로 실행 단계는 1시간을 초과할 수 없습니다. 이 지연 후에는 프로세스가 중단되고 오류 메시지가 표시되며 활동 실행이 실패합니다.

해당 활동에서 사용할 수 있는 **[!UICONTROL Stop execution after]** 필드에서 이 지연을 변경할 수 있습니다.

이 제한을 무시하려면 값을 **0**(으)로 설정해야 합니다.

### JavaScript 코드 {#js-code-desc}

![](assets/javascript_code.png)

* **[!UICONTROL Script]**: 편집기의 중앙 영역에 실행할 스크립트가 있습니다.

* **[!UICONTROL Process errors]**: [처리 오류](monitor-workflow-execution.md#processing-errors)를 참조하세요.

### 고급 JavaScript 코드 {#adv-js-code-desc}

![](assets/advanced_javascript_code.png)

* **[!UICONTROL First call]**: 편집기의 첫 번째 영역에 첫 번째 호출 중에 실행할 스크립트가 있습니다.
* **[!UICONTROL Next calls]**: 편집기의 두 번째 영역에 다음 호출 중에 실행할 스크립트가 있습니다.
* **[!UICONTROL Transitions]**: 여러 활동 출력 전환을 정의할 수 있습니다.
* **[!UICONTROL Schedule]**: **[!UICONTROL Schedule]** 탭에서 활동을 트리거할 시기를 예약할 수 있습니다.

고급 JavaScript은 지속적인 작업이며 완료된 것으로 표시되지 않은 경우 주기적으로 회수됩니다. 작업을 종료하고 향후 회수를 방지하려면 **[!UICONTROL Next calls]** 섹션에서 **task.setCompleted()** 메서드를 사용해야 합니다.

```
task.postEvent(task.transitionByName("ok")); // to transition to Ok branch
task.setCompleted();

return 0;
```
