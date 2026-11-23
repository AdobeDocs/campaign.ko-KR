---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 31%
---
# RecipientSubscribe

선택한 수신자를 정보 서비스 목록에 구독/구독 취소합니다.

```text
XML confirmationIds = RecipientSubscribe ( XML recipientList, XML serviceList, Boolean subscribe, XML sendConfirmation )
```

## 매개변수

**recipientList** 수신자 목록

**serviceList** 서비스 목록

받는 사람 **구독** 구독/구독 취소

**sendConfirmation** 확인 메시지 보내기

## 반환 값

**confirmationIds** 확인 ID 목록

## 기능

**스키마:** [nms:subscription](s-nms-subscription.md)

**정적:**

예
