---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 12%
---
# getBooleanValue

지정된 XPath에서 참조하는 부울 노드 값을 반환합니다.

```text
getBooleanValue (xpath)
```

## 매개변수

**xpath** 경로입니다.

## 반환 값

true 참조 노드의 텍스트 값이 &#39;true&#39; 또는 &#39;1&#39;이면 false는 &#39;false&#39; 또는 &#39;0&#39;입니다.

## 비고

XPath 구문은 XPath 언어 하위 집합만 허용합니다. 값 테스트는 대/소문자를 구분하지 않습니다. 경로의 형식이 잘못되었거나 값이 유효한 부울이 아니면 예외가 발생합니다.

## 기능

**클래스의 메서드:** [DOMElement](c-domelement.md)

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
