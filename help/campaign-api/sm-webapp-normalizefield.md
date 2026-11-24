---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 4%
---
# 필드 정규화

```text
NormalizeField ( XML selectedWebApp, XML archivedField, String newSQLName, String tableName, String schemaId, Boolean rename )
```

## 매개변수

**selectedWebApp** 정규화할 필드를 포함할 수 있는 설문 조사 목록입니다.

**archivedField** 정규화할 필드에 대한 정보입니다.

**newSQLName** 이 필드의 새 SQL 이름입니다.

**tableName** 새 SQL 필드를 포함할 테이블 이름입니다.

새 필드에 속하는 참조를 추가할 **schemaId** 스키마 식별자(보기)(선택 사항).

**이름 바꾸기** 이전에 표준화된 필드도 이름을 바꿉니다.

## 반환 값

없음.

## 기능

**스키마:** [nms:webApp](s-nms-webapp.md)

**정적:**

예
