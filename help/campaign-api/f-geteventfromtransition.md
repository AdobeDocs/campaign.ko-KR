---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 6%
---
# getEventFromTransition

지정된 전환을 경험할 마지막 이벤트를 반환합니다.

```text
getEventFromTransition (transitionName)
```

## 매개변수

**transitionName** 전환의 내부 이름입니다.

## 반환 값

지정된 전환 또는 null을 겪은 마지막 이벤트입니다. 개체가 &#39;xtk:workflowEvent&#39; 스키마의 엔터티에 해당합니다.

## 기능

**다음 위치에서 사용 가능:**

* 워크플로
