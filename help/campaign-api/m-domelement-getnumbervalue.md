---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 16%
---
# getNumberValue

지정된 XPath에서 참조하는 디지털 노드 값을 반환합니다.

```text
getNumberValue (xpath)
```

## 매개변수

**xpath** 경로입니다.

## 반환 값

디지털 값은 참조된 노드에 해당합니다.

## 비고

XPath 구문은 XPath 언어 하위 집합만 허용합니다. 경로의 형식이 잘못되었거나 값이 올바른 숫자가 아니면 예외가 발생합니다.

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
