---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '34'
ht-degree: 41%
---
# CreateWorkflowFromModelId

워크플로 템플릿을 기반으로 캠페인에서 워크플로를 생성합니다.

```text
Number workflowId = CreateWorkflowFromModelId ( Number modelId, XML operationPlanning )
```

## 매개변수

**modelId** 워크플로 템플릿 식별자

**operationPlanning** 캠페인 일정

## 반환 값

만들어진 인스턴스의 **workflowId** 식별자

## 기능

**스키마:** [nms:operation](s-nms-operation.md)

**정적:**

예
