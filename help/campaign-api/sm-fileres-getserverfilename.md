---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 51%
---
# GetServerFileName

필요한 경우 업로드 폴더에 복사한 후 서버의 파일 이름을 반환합니다.

```text
String serverFileName = fileRes.GetServerFileName ()
```

## 매개변수

없음.

## 반환 값

**serverFileName** 서버에 있는 파일의 전체 이름(파일이 없으면 비어 있음).

## 예제

```javascript
var query = xtk.queryDef.create(
  {queryDef: {schema: "xtk:fileRes", operation: "get", 
    select: {
      node: [
      {expr: "@label"}, 
      {expr: "@originalName"}, 
      {expr: "@storageType"}, 
      {expr: "@fileName"}, 
      {expr: "@md5"}]
    }, 
    where: {
      condition: {expr: "@id = 4216"}
    }
  }})

var fileRes = xtk.fileRes.create(query.ExecuteQuery())
var sFileName = fileRes.GetServerFileName();
        
```

## 기능

**스키마:** [xtk:fileRes](s-xtk-fileres.md)

**정적:**

아니요

**Const:**

아니요

**키만:**

아니요
