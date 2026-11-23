---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 14%
---
# joinPart

각 요소가 조인 조건을 나타내는 SchemaNode 인스턴스 테이블을 반환합니다.

```text
joinParts
```

## 비고

표의 각 요소에는 두 가지 속성이 있습니다.

* source - 소스 테이블의 필드를 나타내는 요소입니다.
* destination - 대상 테이블의 필드를 나타내는 요소입니다.

예:

```javascript
var schema = application.getSchema("nms:recipient")
var root = schema.root

var link = root.children.country
for each(var join in link.joinParts)
{
  logInfo("src = " + join.source.name)
  logInfo("dst = " + join.destination.name)
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
