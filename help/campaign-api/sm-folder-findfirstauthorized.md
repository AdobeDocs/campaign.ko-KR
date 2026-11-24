---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 28%
---
# FindFirstAuthorized

folderFilter 조건을 충족하는 현재 사용자의 첫 번째 적격 폴더를 찾습니다.

```text
XML folderEntity = FindFirstAuthorized ( String folderFilter, Boolean writeAccess, Number orgUnit )
```

## 매개변수

폴더에 대한 **folderFilter** 필터

**writeAccess** 반환된 폴더는 쓰기 가능해야 합니다.

**orgUnit** 반환된 폴더는 지정된 조직 엔터티와 호환되어야 합니다

## 반환 값

**folderEntity** 연결된 폴더 엔터티를 반환합니다(null은 폴더를 찾을 수 없음).

## 기능

**스키마:** [xtk:folder](s-xtk-folder.md)

**정적:**

예
