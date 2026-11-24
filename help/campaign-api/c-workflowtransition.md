---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '33'
ht-degree: 9%
---
# WorkflowTransition(클래스)

워크플로우 전환을 나타냅니다.

전환은 또는 와 같은 방법을 사용하여 복구되고 작업 전환을 활성화하는 데 사용되는 불투명 객체입니다.

예:

```text
var done = task.doneTransition() task.postEvent(done) task.setCompleted() return 0
```

## 기능

**다음 위치에서 사용 가능:**

* 워크플로
