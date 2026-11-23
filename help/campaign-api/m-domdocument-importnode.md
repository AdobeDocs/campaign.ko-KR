---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 25%
---
# importNode

다른 문서에서 노드 복사본을 만듭니다.

```text
importNode (importedNode, deep)
```

## 매개변수

**importedNode** Source 노드.

전체 노드를 복사해야 하는 경우 **deep** true이고, 그렇지 않으면 false입니다.

## 반환 값

노드의 사본.

## 비고

예:

```javascript
var result = doc.importNode(rcpResult, true);
doc.root.appendChild(result);
```

## 기능

**클래스의 메서드:** [DOMDocument](c-domdocument.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 게재 메시지
* 유형화 규칙
* 가져오기
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
