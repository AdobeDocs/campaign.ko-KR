---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 4%
---
# GetStatus

작업 처리 진행 정보를 가져옵니다. 경고: 이 API는 고유한 로그 항목 목록을 반환하지 않습니다(호출자는 ID를 사용하여 중복을 제거해야 함).

```text
[ Number status, XML returnLogs, XML properties ] = GetStatus ( String id, Number lastLogId, Number maxLogCount )
```

## 매개변수

**id** 작업 식별자

**lastLogId** 이전 호출에서 반환된 마지막 로그 항목의 식별자

**maxLogCount** 보낼 최대 로그 항목 수

## 반환 값

**상태** 작업 상태

**returnLogs** 로그 메시지

**속성** 속성(진행 중...)

## 기능

**스키마:** [xtk:job](s-xtk-job.md)

**정적:**

예
