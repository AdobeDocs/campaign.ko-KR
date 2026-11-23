---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 4%
---
# SimulateWithParameters

시뮬레이션 모드에서 워크플로우를 시작하고 매개변수를 제공합니다.

```text
SimulateWithParameters ( String workflowId, XML parameters )
```

## 매개변수

**workflowId** 워크플로의 식별자 또는 내부 이름입니다.

인스턴스에 전달할 **매개 변수** 매개 변수입니다. 이러한 매개 변수는 워크플로우의 인스턴스 변수가 됩니다. 이 인수는 이름이 변수여야 하며 특성만 포함할 수 있는 XML 요소입니다. 예:

```xml
<variables foo="abc" bar="def">
```

워크플로우 내의 JavaScript 스크립트는 instance.vars 객체에서 다음 변수에 액세스할 수 있습니다.

```javascript
    var foo = instance.vars.foo   // "abc"
    var bar = instance.vars.bar   // "def"
            
```

## 반환 값

없음.

## 비고

명령은 비동기적으로 실행되므로 메서드 반환 후 즉각적인 영향을 주지 않습니다.

## 기능

**스키마:** [xtk:workflow](s-xtk-workflow.md)

**정적:**

예
