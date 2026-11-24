---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 17%
---
# toXML

[MemoryBuffer](c-memorybuffer.md)의 콘텐츠에서 가져온 XML JavaScript 개체를 반환합니다. 이 함수는 더 이상 사용되지 않습니다. [toDocument()](m-memorybuffer-todocument.md)을(를) 사용하십시오.

```text
toXML ( [codePage ])
```

## 매개변수

**codePage** 사용된 문자 페이지를 코딩하는 정수입니다. 기본적으로 MemoryBuffer.CODEPAGE\_UTF8입니다.

## 반환 값

XML 객체 형태의 스탬프 컨텐츠입니다.

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
