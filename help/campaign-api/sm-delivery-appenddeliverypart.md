---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 13%
---
# AppendDeliveryPart

준비 중인 게재에 한 부분을 추가합니다.

```text
[ Number deliveryPartId, Number fatalError, String fatalErrorMsg ] = AppendDeliveryPart ( XML deliveryPart, Boolean retry )
```

## 매개변수

**deliveryPart** 게재 부분(또는 게재 부분의 컬렉션)을 나타내는 문서입니다.

**다시 시도** 이 게재 부분 제출이 새로운 시도인 경우 지정합니다.

## 반환 값

데이터베이스의 **deliveryPartId** 게재 부분 식별자(컬렉션이 아닌 경우).

**fatalError** 호출자가 사용 중지를 수행하지 못하도록 오류 코드를 반환합니다. 그렇지 않으면 일시적인 오류일 수 있습니다.

&#39;fatalError&#39; 오류 코드와 연결된 **fatalErrorMsg** 오류 메시지.

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

예
