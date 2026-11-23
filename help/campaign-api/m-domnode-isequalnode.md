---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 12%
---
# isEqualNode

두 노드를 비교합니다.

```text
isEqualNode (arg)
```

## 매개변수

**arg** 두 번째 노드입니다.

## 반환 값

두 노드가 동일하면 true이고, 그렇지 않으면 false입니다.

## 비고

다음 조건이 확인되면 두 노드가 같습니다.

* 두 노드는 유형 유형입니다.
* nodeName, localName, namespaceURI, prefix 및 nodeValue 속성은 동일해야 합니다.
* 두 노드는 유형 유형입니다.
* 속성은 같아야 합니다.
* 노드는 같아야 합니다.

표준화는 균등에 영향을 줄 수 있으므로 비교하기 전에 표준화하는 것이 좋습니다.

## 기능

**클래스의 메서드:** [DOMNode](c-domnode.md)

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
