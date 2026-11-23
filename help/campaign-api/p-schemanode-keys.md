---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '35'
ht-degree: 28%
---
# 키

현재 노드의 [SchemaKey](c-schemakey.md) 키에 대한 정의가 있는 테이블을 반환합니다.

```text
keys
```

## 비고

예:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var key in schema.root.keys)
  logInfo("Key: " + key.name + "\t is-internal: " + key.isInternal)
    
```

## 기능

**클래스의 속성:** [SchemaNode](c-schemanode.md)

**읽기 전용:**

예

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
