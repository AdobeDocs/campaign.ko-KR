---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 22%
---
# LoadChildrenWithPath

주어진 노드의 하위 항목 목록 로드

```text
XML result = LoadChildrenWithPath ( String parentKey, String folderFilter, Boolean writeAccess, String fullName, String path, Boolean sort )
```

## 매개변수

**parentKey** 상위 키

폴더에 대한 **folderFilter** 필터

**writeAccess** 반환된 폴더는 쓰기 가능해야 합니다.

선택한 노드의 **fullName** 전체 이름

선택한 노드의 **경로** 전체 이름

**정렬** 알파벳순으로 정렬

## 반환 값

**결과** 결과 문서

## 기능

**스키마:** [xtk:folder](s-xtk-folder.md)

**정적:**

예
