---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 33%
---
# DOMDocument

새 문서를 만듭니다.

```text
DOMDocument (name [, namespaceURI ])
```

## 매개변수

**이름** 문서 이름.

**namespaceURI** 문서 네임스페이스 URI.

## 반환 값

없음.

## 비고

예:

```javascript
var doc = new DOMDocument("test")
var doc2 = new DOMDocument("html", "http://www.w3.org/1999/xhtml")
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
