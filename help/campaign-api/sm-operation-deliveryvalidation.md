---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 27%
---
# 게재 유효성 검사

캠페인의 게재 승인.

```text
DeliveryValidation ( Number deliveryId, Number type, Boolean refused, String comment )
```

## 매개변수

**deliveryId** 게재 식별자

**유형** 승인 유형(타겟팅=0, 콘텐츠=1, 예산=2, 추출=3)

**거부** 거부

**댓글** 댓글

## 반환 값

없음.

## 기능

**스키마:** [nms:operation](s-nms-operation.md)

**정적:**

예
