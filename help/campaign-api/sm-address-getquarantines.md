---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 10%
---
# GetQuarantines

최신 격리 및 격리 종료를 가져옵니다.

```text
[ XML result, Date nextDate, Boolean hasMore ] = GetQuarantines ( Date startDate, String pointerName, Number quarantineCount, Date callerDate )
```

## 매개변수

**startDate** 이 날짜 이후에 수정된 격리를 검색합니다. 비어 있으면 포인터 값이 사용됩니다.

**pointerName** 이 포인터 이후에 수정된 격리를 검색합니다(선택 사항).

**quarantineCount** 같은 시간에 업데이트되지 않은 경우 검색할 최대 격리 수입니다.

**callerDate** 호출자 참조 날짜입니다. 격리 날짜 참조를 수정할 수 있습니다(선택 사항).

## 반환 값

**결과** 출력 문서, 격리 목록입니다.

**nextDate** 검색되지 않은 첫 번째 격리 날짜입니다(startDate보다 정확히 높음).

**hasMore** 이 경우 검색할 격리가 아직 있습니다.

## 기능

**스키마:** [nms:address](s-nms-address.md)

**정적:**

예
