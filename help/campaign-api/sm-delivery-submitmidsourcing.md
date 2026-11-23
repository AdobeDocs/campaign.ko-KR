---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 21%
---
# SubmitMidSourcing

중간 소싱 모드의 게재를 제출합니다.

```text
[ Number remoteId, Number remoteMatchId ] = SubmitMidSourcing ( XML delivery, XML routingMatch, String folderName )
```

## 매개변수

게재를 나타내는 **게재** 문서.

**routingMatch** 더 이상 사용되지 않음

**folderName** 보낸 사람 데이터베이스의 전체 폴더 이름입니다.

## 반환 값

받는 사람 데이터베이스의 **remoteId** 게재 식별자.

**remoteMatchId** 더 이상 사용되지 않음

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

예
