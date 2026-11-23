---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 3%
---
# WakeupTask

하나 이상의 보류 중인 작업의 사전 처리를 강제합니다.

```text
WakeupTask ( String workflowId, String taskIdentifier, String activityName )
```

## 매개변수

**workflowId** 워크플로의 식별자 또는 내부 이름입니다.

**taskIdentifier** 작업의 식별자(@taskIdentifier 필드) 또는 주어진 활동과 관련하여 보류 중인 모든 작업의 조기 처리를 강제하는 빈 문자열입니다.

**activityName** 연결된 모든 작업 또는 빈 문자열의 조기 처리를 강제하는 활동의 이름입니다.

## 반환 값

없음.

## 비고

taskIdentifier 및 activityName을 지정하지 않으면 보류 중인 모든 작업이 고려됩니다.

## 기능

**스키마:** [xtk:workflow](s-xtk-workflow.md)

**정적:**

예
