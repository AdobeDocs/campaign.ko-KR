---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 8%
---
# 실행

워크플로를 즉시 실행하고 완료될 때까지 기다립니다.

```text
XML workflow = Execute ( String workflowId, Boolean simulationMode, Boolean keepResult, Boolean logSQL )
```

## 매개변수

**workflowId** 워크플로의 식별자 또는 내부 이름입니다.

**simulationMode** 실행 시뮬레이션.

**keepResult** 중간 결과를 유지합니다.

**logSQL** SQL 주문 추적을 저장해야 합니까?

## 반환 값

**워크플로** 실행 결과입니다.

## 기능

**스키마:** [xtk:workflow](s-xtk-workflow.md)

**정적:**

예
