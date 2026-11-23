---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 20%
---
# fromXMLString

XML 문자 문자열로 새 문서를 만듭니다.

```text
fromXMLString (string)
```

## 매개변수

**문자열** XML 문자의 문자열입니다.

## 반환 값

없음.

## 비고

인수가 유효한 XML 문서가 아니면 예외가 발생합니다. 이 함수는 DOMDocument 클래스에 적용됩니다. 예:

```javascript
var doc = DOMDocument.fromXMLString(
    '<?xml version="1.0" encoding="ISO-8859-1"?>' +
    '<form name="address" namespace="nms" colcount="2"/>')
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
