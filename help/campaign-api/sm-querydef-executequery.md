---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 34%
---
# ExecuteQuery

쿼리에서 데이터 가져오기

```text
XML output = queryDef.ExecuteQuery () const
```

## 매개변수

없음.

## 반환 값

**출력** 출력 XML 문서

## 비고

쿼리는 네 가지 유형의 작업을 지원합니다.

* 선택
* get
* getIfExists
* count

## 예제

```javascript
var query = NLWS.xtkQueryDef.create(
  {queryDef: {schema: "xtk:workflow", operation: "select", 
    select: {
        node: [{expr: "@id"},
               {expr: "@label"},
               {expr: "@internalName"}] 
    }, 
    where: {
      condition: [{expr: "[folder/@name]='nmsTechnicalWorkflow'"},
                  {expr: "@production = 1"}]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }})

var res = query.ExecuteQuery()

var workflows = res.getElementsByTagName("workflow")
for each (var w in workflows)
  logInfo(w.getAttribute("internalName"))
        
```

## 기능

**스키마:** [xtk:queryDef](s-xtk-querydef.md)

**정적:**

아니요

**Const:**

예

**키만:**

아니요
