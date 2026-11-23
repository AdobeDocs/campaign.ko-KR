---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 15%
---
# FinalizeMidPreparation

중간 소싱 모드에서 게재 분석을 완료합니다.

```text
[ Number fatalError, String fatalErrorMsg ] = FinalizeMidPreparation ( Number deliveryId, Number errorCode, XML properties, Boolean retry )
```

## 매개변수

**deliveryId** 게재 식별자

**errorCode** 마케팅 데이터베이스에 대한 분석에서 반환된 오류 코드(이 경우 메서드 수준 오류 코드가 사용되지 않음)

업데이트할 **속성** 게재 속성

**다시 시도** 메서드 호출을 위한 다시 시도인 경우 지정합니다.

## 반환 값

**fatalError** 호출자가 사용 중지를 수행하지 못하도록 오류 코드를 반환합니다. 그렇지 않으면 일시적인 오류일 수 있습니다.

&#39;fatalError&#39; 오류 코드와 연결된 **fatalErrorMsg** 오류 메시지.

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

예
