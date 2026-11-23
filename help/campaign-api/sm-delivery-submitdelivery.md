---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%
---
# 전송

시나리오(해당 내부 이름)에서 게재 생성 및 제출.

```text
Number deliveryId = SubmitDelivery ( String scenarioName, XML content )
```

## 매개변수

게재 템플릿의 **scenarioName** 내부 이름

템플릿에 추가할 **content** XML 콘텐츠

## 반환 값

**deliveryId** 새 게재 식별자(분석이 실패하더라도 반환됨)

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

예
