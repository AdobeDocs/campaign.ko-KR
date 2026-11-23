---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '34'
ht-degree: 44%
---
# GenCreateOrUpdateSchemaSequenceDDL

autoPk 스키마 시퀀스를 생성하거나 업데이트하는 데 사용되는 SQL 스크립트를 생성합니다.

```text
String sqlDDL = GenCreateOrUpdateSchemaSequenceDDL ( String schemaId, String newSequence, String oldSequence )
```

## 매개변수

**schemaId** 스키마 식별자

**newSequence** 새 시퀀스

**oldSequence** 이전 시퀀스

## 반환 값

**sqlDDL** SQL 스크립트

## 기능

**스키마:** [xtk:builder](s-xtk-builder.md)

**정적:**

예
