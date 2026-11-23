---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 19%
---
# GetMidDeliveries

중간 소싱 모드에서 마지막으로 수정된 게재 상태를 가져옵니다.

```text
[ XML result, Date nextDate ] = GetMidDeliveries ( Date startDate, Number maxCount, Date emitterDate )
```

## 매개변수

**startDate** (중간 소싱 서버에서) 이 날짜 이후의 수정 사항을 검색합니다.

**maxCount** 같은 시간에 업데이트되지 않은 경우 검색할 최대 게재 수입니다.

발급 서버의 **emitterDate** 참조 날짜입니다. 게재 날짜를 조정하는 데 사용됩니다.

## 반환 값

**결과** 출력 문서, 게재 목록이 업데이트되었습니다.

**nextDate** 다음 호출 시작 날짜입니다.

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

예
