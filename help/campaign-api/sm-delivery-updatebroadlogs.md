---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 31%
---
# UpdateBroadlogs

게재 로그 상태를 업데이트하고, 오류 처리를 수행하고, 게재 카운터를 업데이트합니다.

```text
UpdateBroadLogs ( Number deliveryId, XML logs, Boolean deliveryMustExist )
```

## 매개변수

**deliveryId** 게재 식별자

업데이트할 nms:broadLog 레코드가 포함된 **로그** 컬렉션(@id, @status, @eventDate 및 @lastModified을 지정해야 함)

**deliveryMustExist** 잘못된 게재 식별자에 대해 오류를 발생시킬지 여부를 지정합니다.

## 반환 값

없음.

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

예
