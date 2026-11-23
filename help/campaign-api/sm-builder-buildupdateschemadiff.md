---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 41%
---
# BuildUpdateSchemaDiff

실제 데이터베이스 구조와 해당 논리적 설명 간의 차이점을 설명하는 문서를 생성합니다.

```text
XML sqlSchemaDiff = BuildUpdateSchemaDiff ( XML parameters, Boolean useNamingConventions )
```

## 매개변수

**매개 변수** 업데이트 매개 변수

**useNamingConventions** SQL 명명 규칙을 사용하여 새 필드의 경로를 계산합니다.

## 반환 값

**sqlSchemaDiff** 생성된 스키마

## 기능

**스키마:** [xtk:builder](s-xtk-builder.md)

**정적:**

예
