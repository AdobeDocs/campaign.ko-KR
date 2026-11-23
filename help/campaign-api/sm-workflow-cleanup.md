---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 5%
---
# 정리

워크플로우 내역을 삭제합니다.

```text
Cleanup ( String workflowId )
```

## 매개변수

**workflowId** 워크플로의 식별자 또는 내부 이름입니다.

## 반환 값

없음.

## 비고

처리된 모든 이벤트, 완료된 작업, 실패한 작업 및 로그 메시지를 삭제합니다. 또한 워크플로우가 완료되면 다이어그램에서 진행률을 삭제합니다. 이 메서드는 워크플로 엔진에서만 더 이상 사용되지 않는 데이터를 삭제하고, 워크플로의 비헤이비어에 영향을 주지 않습니다.

## 기능

**스키마:** [xtk:workflow](s-xtk-workflow.md)

**정적:**

예
