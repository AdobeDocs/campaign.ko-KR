---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 5%
---
# EvaluateTarget

주문에 연결된 각 캠페인 게재에 대한 캠페인 타깃팅을 평가합니다. 이 평가는 운영자 권한을 사용하여 주문할 때 로컬 캠페인이 생성되기 전에 수행됩니다.

```text
XML result = EvaluateTarget ( XML order )
```

## 매개변수

주문 정보가 포함된 **order** 요소입니다.

## 반환 값

각 캠페인 게재의 **결과** 카운트 결과.

## 기능

**스키마:** [nms:localOrder](s-nms-localorder.md)

**정적:**

예
