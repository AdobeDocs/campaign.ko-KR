---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 5%
---
# setNextProcessingDate

작업의 다음 처리 날짜를 강제 적용합니다.

```text
setNextProcessingDate (timestamp)
```

## 매개변수

**타임스탬프** 다음 처리 날짜입니다. 비어 있는 경우 다음 처리가 즉시 수행됩니다.

## 반환 값

없음.

## 비고

* 이 메서드를 사용하면 스케줄러가 제공한 경우 다음 처리 날짜가 무시됩니다.
* 다음 처리는 항상 \*\_recall() 함수에 의해 수행됩니다.

## 기능

**클래스의 메서드:** [WorkflowTask](c-workflowtask.md)

**다음 위치에서 사용 가능:**

* 워크플로
