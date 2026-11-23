---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 6%
---
# GetReportData

```text
XML result = GetReportData ( Number cubeId, String queryDef, Boolean selectAll, Boolean useAggregates, XML cube )
```

## 매개변수

**cubeId** 큐브 식별자입니다. 큐브가 매개 변수로 전달되면 0으로 설정할 수 있습니다.

보고서에 정의된 **queryDef** QueryDef

**모두 선택** 모두 선택

**useAggregates** 집계 사용 활성화

큐브를 설명하는 **큐브** XML입니다.

## 반환 값

**결과** 결과

## 기능

**스키마:** [xtk:olapCube](s-xtk-olapcube.md)

**정적:**

예
