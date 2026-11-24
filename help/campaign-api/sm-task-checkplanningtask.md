---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 6%
---
# CheckPlanningTask

작업 연산자의 일정 내에서 오버로드를 확인하는 데 사용되는 내부 함수입니다(오버로드의 경우 &#39;true&#39; 반환). 이 기능 역시 관련 업무 일정의 일관성을 확인하고 필요한 경우 업데이트한다.

```text
Boolean workloadAlert = CheckPlanningTask ( Number taskId )
```

## 매개변수

**taskId** 작업 식별자.

## 반환 값

**workloadAlert** 리소스 오버로드 경고

## 기능

**스키마:** [nms:task](s-nms-task.md)

**정적:**

예
