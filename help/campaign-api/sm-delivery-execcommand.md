---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '34'
ht-degree: 26%
---
# Exec 명령

게재 시 명령을 실행합니다.

```text
Number newState = ExecCommand ( String deliveryId, String command )
```

## 매개변수

**deliveryId** 게재 식별자

**명령** 명령 이름(&#39;play&#39;, &#39;pause&#39; 또는 &#39;stop&#39;)

## 반환 값

명령이 실행된 후 **newState** 게재 상태

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

예
