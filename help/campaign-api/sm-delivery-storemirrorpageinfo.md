---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 23%
---
# StoreMirrorPageInfo

정보를 추가하여 게재 부분 세트의 미러 페이지를 생성합니다.

```text
[ Number fatalError, String fatalErrorMsg ] = StoreMirrorPageInfo ( Number deliveryId, Number partsCount, Number firstPartId, Number lastPartId )
```

## 매개변수

**deliveryId** 게재 식별자

**partsCount** 파트 수

**firstPartId** 첫 번째 파트 식별자

**lastPartId** 마지막 파트 식별자

## 반환 값

**fatalError** 호출자가 사용 중지를 수행하지 못하도록 오류 코드를 반환합니다. 그렇지 않으면 일시적인 오류일 수 있습니다.

&#39;fatalError&#39; 오류 코드와 연결된 **fatalErrorMsg** 오류 메시지.

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

예
