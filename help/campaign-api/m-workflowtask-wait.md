---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 2%
---
# wait

신호를 기다립니다.

```text
wait (timeout)
```

## 매개변수

**시간 초과** 대기 시간(밀리초)

## 반환 값

대기 시간이 만료되기 전에 신호가 수신되는 경우 true로 부울.

## 비고

신호는 [Wakeup](sm-workflow-wakeup.md) 및 [WakeupTask](sm-workflow-wakeuptask.md) SOAP 메서드에서 발행됩니다. 사용된 프로토콜(UDP)은 메시지 수신을 보장하지 않습니다. 이 신호는 작업을 더 빠르게 실행하는 데에만 유용합니다. 경고: 이 신호는 하위 워크플로우에서 수신되지 않습니다. 예: 다음은 일반적인 사용 예입니다. 루프는 큐(poll())에서 오는 작업을 처리한 다음 각 작업 사이에 특정 시간을 대기합니다. 워크플로우 보호를 강제 적용하기 위해 추가 지연이 추가됩니다.

```javascript
var lifetime = 30 * 60 * 1000 // 30 minutes
var frequency = 30 * 1000 // 30 seconds
var start = new Date().getTime()
while( new Date().getTime() - start < lifetime )
{
  poll()
  task.wait(frequency)
}
 
```

## 기능

**클래스의 메서드:** [WorkflowTask](c-workflowtask.md)

**다음 위치에서 사용 가능:**

* 워크플로
