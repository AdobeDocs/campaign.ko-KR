---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 14%
---
# fromJSON

JXON 객체에서 새 문서를 만듭니다.

```text
fromJXON (obj)
```

## 매개변수

**obj** 만들 XML 문서를 나타내는 JXON 개체입니다.

## 반환 값

없음.

## 비고

DOMDocument 또는 DOMElement를 매개 변수로 전달하는 함수도 JXON 개체를 직접 허용합니다. 이 기능을 이용하여 중간 객체를 구축할 필요는 없다. 개체가 유효한 JXON 개체가 아닌 경우 예외가 발생합니다. 이 함수는 DOMDocument 클래스에 적용됩니다. 예:

```javascript
var doc = DOMDocument.fromJXON(
    {form : {name: "address", "namespace": "nms", colcount: 2}})
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
