---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 25%
---
# 하위

각 속성이 그 이름으로 인덱싱된 자식 노드인 개체를 반환합니다.

```text
children
```

## 비고

예:

```javascript
var schema = application.getSchema("nms:recipient")
var root = schema.root

logInfo(root.children["@firstName"].label)
logInfo(root.children.country.label)

// root.children is a map which :
//   each key is the name of the child
//   each value the corresponding SchemaNode instance
for each(var node in root.children)
{
  logInfo(node.label + " (" + node.type + ")")
}
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
