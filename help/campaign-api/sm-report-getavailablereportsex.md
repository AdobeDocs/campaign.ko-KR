---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 25%
---
# GetAvailableReportsEx

데이터 정렬 조건 및 페이지 번호 매기기를 고려하여 기록이 없는 보고서 목록을 복구합니다.

```text
XML reports = GetAvailableReportsEx ( String activeContext, String schema, String selection, XML where, XML orderBy, Number editionMode, Number lineCount, Number startLine, String locationName )
```

## 매개변수

**activeContext** 활성 컨텍스트(선택, 전역)

**스키마** 관련 스키마

선택한 엔터티의 **선택** ID를 &#39;,&#39;로 구분

**where** &#39;where&#39; 노드 필터링

**orderBy** &#39;orderBy&#39; 노드 정렬

**editionMode** 편집하는 동안 게시되지 않은 보고서도 표시됩니다

**lineCount** 수집할 보고서 수

페이지 번호 매기기를 적용할 **startLine** 오프셋

**locationName**

## 반환 값

**보고서** 적격 보고서 목록

## 기능

**스키마:** [xtk:report](s-xtk-report.md)

**정적:**

예
