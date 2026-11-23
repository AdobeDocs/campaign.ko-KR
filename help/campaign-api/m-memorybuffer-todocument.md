---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 23%
---
# toDocument

이 버퍼의 텍스트 콘텐츠에서 XML 문서를 반환합니다.

```text
toDocument ( [codePage ])
```

## 매개변수

**codePage** 사용된 문자 페이지를 코딩하는 정수입니다. 기본적으로 MemoryBuffer.CODEPAGE\_UTF8입니다.

## 반환 값

[DOMDocument](c-domdocument.md) 형식 개체입니다.

## 기능

**클래스의 메서드:** [MemoryBuffer](c-memorybuffer.md)

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
