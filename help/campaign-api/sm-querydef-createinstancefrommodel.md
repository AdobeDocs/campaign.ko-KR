---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 29%
---
# CreateInstanceFromModel

템플릿을 통해 오브젝트의 인스턴스를 인스턴스화합니다.

```text
Number output = CreateInstanceFromModel ( String schema, Number modelId, XML diff )
```

## 매개변수

**스키마** 인스턴스 스키마

템플릿의 **modelId** ID

템플릿에 적용할 **diff** XML 패치

## 반환 값

생성된 인스턴스의 **출력** ID

## 기능

**스키마:** [xtk:queryDef](s-xtk-querydef.md)

**정적:**

예
