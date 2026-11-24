---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 15%
---
# GetMidBroadLogs

중간 소싱 모드에서 마지막으로 수정된 게재 로그를 가져옵니다.

```text
[ XML result, Date nextDate ] = GetMidBroadLogs ( Date startDate, Number logCount, Date emitterDate )
```

## 매개변수

**startDate** (중간 소싱 서버에서) 이 날짜 이후에 수정된 로그를 검색합니다.

**logCount** 같은 시간 내에 업데이트되지 않는 한 검색할 최대 로그 수입니다.

발급 서버의 **emitterDate** 참조 날짜입니다. 게재 로그 날짜를 조정하는 데 사용됩니다.

## 반환 값

**결과** 출력 문서, 게재 로그 목록.

**nextDate** 검색된 첫 번째 로그 날짜입니다(startDate보다 큼).

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

예
