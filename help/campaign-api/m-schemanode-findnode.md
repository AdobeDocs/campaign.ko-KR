---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 7%
---
# findNode

노드가 존재하지 않고 mustExist 매개 변수가 false로 설정된 경우 [SchemaNode](c-schemanode.md)의 인스턴스를 반환하거나 null을 반환합니다.

```text
findNode (name [, strict ] [, mustExist ])
```

## 매개변수

**name** XPath는 검색할 노드의 이름을 나타냅니다.

경로에 있는 마지막 항목의 이름이 있는 그대로 없으면 특성 또는 요소로 검색해야 하는지 여부를 나타내는 **strict** 부울입니다. 기본적으로 true입니다.

노드가 없는 경우 예외를 발생시켜야 하는지 여부를 나타내는 **mustExist** 부울입니다. 기본적으로 true입니다.

## 반환 값

노드를 찾을 수 있는 경우 [SchemaNode](c-schemanode.md) 인스턴스를 반환하고, mustExist 매개 변수가 false로 설정된 경우 null을 반환합니다.

## 비고

예:

```javascript
var schema = application.getSchema("nms:recipient");

logInfo("netSales: " + schema.root.findNode("@netSales"));
logInfo("merchandise/@lastPurchaseDate: " + schema.root.findNode("merchandise/@lastPurchaseDate", true, false));
```

결과:

```javascript
netSales: [object NodeDef]
merchandise/@lastPurchaseDate: [object NodeDef]
```

## 기능

**클래스의 메서드:** [SchemaNode](c-schemanode.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
