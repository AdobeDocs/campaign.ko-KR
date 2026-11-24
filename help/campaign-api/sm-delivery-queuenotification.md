---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 21%
---
# QueueNotification

게재 템플릿을 참조하는 알림에 대한 큐 대기 요청.

```text
QueueNotification ( String scenarioName, XML target )
```

## 매개변수

템플릿의 **scenarioName** 내부 이름

**target** 게재 대상 모집단

## 반환 값

없음.

## 비고

이 API는 웹 애플리케이션/온라인 설문 조사 컨텍스트에서만 사용할 수 있습니다. SubmitNotification과 달리 QueueNotification은 대기열에 추가된 알림에 전용 스레드를 사용합니다.

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

예
