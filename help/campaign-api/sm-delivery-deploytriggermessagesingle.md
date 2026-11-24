---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 6%
---
# DeployTriggerMessageSingle

실행 인스턴스에 트랜잭션 메시지를 게시합니다. 게시가 성공하면 true를 반환하고 그렇지 않으면 false를 반환합니다.

```text
Boolean isSuccess = DeployTriggerMessageSingle ( Number deliveryId, Boolean localPublish )
```

## 매개변수

배포할 게재의 **deliveryId** ID

**localPublish** 컨트롤 인스턴스에만 게시하시겠습니까?

## 반환 값

**isSuccess** 게시 완료

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

예
