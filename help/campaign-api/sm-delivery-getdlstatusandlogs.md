---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 33%
---
# GetDlStatusAndLogs

저널 및 게재 상태에서 마지막 로그를 가져옵니다.

```text
[ Number deliveryState, XML returnLogs ] = GetDlStatusAndLogs ( Number deliveryId, Number lastLogId )
```

## 매개변수

**deliveryId** 게재 식별자

**lastLogId** 이전 호출에서 반환된 마지막 저널 항목의 식별자입니다.

## 반환 값

**deliveryState** 배달 상태

**returnLogs** 로그 메시지

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

예
