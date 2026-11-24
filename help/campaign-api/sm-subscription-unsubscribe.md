---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '29'
ht-degree: 41%
---
# 구독 취소

정보 서비스에서 수신자를 구독 취소합니다.

```text
Unsubscribe ( String serviceName, XML recipient )
```

## 매개변수

정보 서비스 이름의 **serviceName** 목록(쉼표로 구분)

**수신자** 수신자

## 반환 값

없음.

## 예제

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Unsubscribe("SVC1", recipient)
        
```

## 기능

**스키마:** [nms:subscription](s-nms-subscription.md)

**정적:**

예
