---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '33'
ht-degree: 51%
---
# BuildSqlSchemaDiff

실제 데이터베이스 구조와 해당 논리적 설명 간의 차이점을 설명하는 문서를 생성합니다.

```text
XML sqlSchemaDiff = BuildSqlSchemaDiff ( XML sqlDiffParam, XML package )
```

## 매개변수

**sqlDiffParam** 확장 매개 변수

**패키지** 초기 패키지

## 반환 값

**sqlSchemaDiff** SqlSchemaDiff 생성됨

## 기능

**스키마:** [xtk:builder](s-xtk-builder.md)

**정적:**

예
