---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 5%
---
# DOMNode(클래스)

DOMNode는 문서를 구성하는 여러 구성 요소의 상위 클래스입니다.

## 방법

| 방법 | 설명 |
| --- | --- |
| [insertBefore](m-domnode-insertbefore.md) | 특정 위치 앞에 노드를 삽입합니다. |
| [replaceChild](m-domnode-replacechild.md) | 노드를 바꿉니다. |
| [removeChild](m-domnode-removechild.md) | 노드를 삭제합니다. |
| [appendChild](m-domnode-appendchild.md) | 하위 폴더 목록의 끝에 노드를 삽입합니다. |
| [hasChildNodes](m-domnode-haschildnodes.md) | 노드에 하나 이상의 하위 폴더가 있는지 테스트합니다. |
| [정규화](m-domnode-normalize.md) | 노드를 정규화합니다. 인접한 텍스트 노드가 병합되고 빈 텍스트 노드가 삭제됩니다. |
| [hasAttributes](m-domnode-hasattributes.md) | 노드에 특성이 하나 이상 있는지 테스트합니다. |
| [isSameNode](m-domnode-issamenode.md) | 지정된 참조가 동일한 노드를 나타내는지 테스트합니다. |
| [isDefaultNamespace](m-domnode-isdefaultnamespace.md) | 지정된 네임스페이스가 기본값인지 테스트합니다. |
| [lookupNamespaceURI](m-domnode-lookupnamespaceuri.md) | 지정된 접두사에 연결된 네임스페이스의 URI를 검색했습니다. |
| [isEqualNode](m-domnode-isequalnode.md) | 두 노드를 비교합니다. |

## 속성

| 속성 | 설명 |
| --- | --- |
| [nodeName](p-domnode-nodename.md) | 적격 노드 이름. 이름은 노드 유형에 따라 다릅니다. |
| [nodeValue](p-domnode-nodevalue.md) | 노드 값. 값은 노드 유형에 따라 다릅니다. |
| [nodeType](p-domnode-nodetype.md) | 노드 유형. |
| [parentNode](p-domnode-parentnode.md) | 상위 노드 또는 null. |
| [자식 노드](p-domnode-childnodes.md) | 자식 노드 목록을 표 형식으로 반환합니다. |
| [첫 번째 자식](p-domnode-firstchild.md) | 이 노드의 첫 번째 하위 노드 또는 하위 노드가 없는 경우 null입니다. |
| [lastChild](p-domnode-lastchild.md) | 이 노드의 마지막 하위 노드 또는 하위 노드가 없는 경우 null입니다. |
| [nextSibling](p-domnode-nextsibling.md) | 이 노드 다음에 오는 노드 또는 null. |
| [previousSibling](p-domnode-previoussibling.md) | 이 노드 바로 앞에 있는 노드 또는 null. |
| [특성](p-domnode-attributes.md) | 노드가 요소인 경우 속성 목록을 포함하는 테이블을 반환하고, 그렇지 않으면 null을 반환합니다. |
| [namespaceURI](p-domnode-namespaceuri.md) | 노드 네임스페이스의 URI. |
| [접두사](p-domnode-prefix.md) | 이 노드의 네임스페이스 접두사이거나 지정되지 않은 경우 비어 있습니다. |
| [localName](p-domnode-localname.md) | 노드의 정규화된 이름에 대한 로컬 부분입니다. |
| [baseURI](p-domnode-baseuri.md) | 이 노드의 기본 URI입니다. |
| [textContent](p-domnode-textcontent.md) | 노드의 텍스트 콘텐츠입니다. 값은 노드 유형에 따라 다릅니다. |
| [ownerDocument](p-domnode-ownerdocument.md) | 이 노드가 속한 문서입니다. |

## 기능

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
