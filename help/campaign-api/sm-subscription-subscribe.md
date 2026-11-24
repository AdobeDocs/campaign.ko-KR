---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 32%
---
# 구독

정보 서비스에 대한 수신자 구독 생성 또는 업데이트

```text
Subscribe ( String serviceName, XML recipient, Boolean create )
```

## 매개변수

정보 서비스 이름의 **serviceName** 목록(쉼표로 구분)

**받는 사람** 등록하고 선택적으로 만들 받는 사람

**만들기** 존재하지 않는 경우 받는 사람 만들기

## 반환 값

없음.

## 예제

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Subscribe("SVC1", recipient, false)
        
```

## 기능

**스키마:** [nms:subscription](s-nms-subscription.md)

**정적:**

예
