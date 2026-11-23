---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 27%
---
# escapeXmlStr

문자열을 XML 형식으로 변환합니다.

```text
escapeXmlStr (value)
```

## 매개변수

변환할 **값** 문자열.

## 반환 값

변환 후 문자열입니다.

## 비고

이 함수는 &amp;, &lt;, > 및 \\&quot; 문자를 해당 이스케이프 시퀀스로 변환합니다.

* &amp; &amp;
* &lt; &lt;
* > >
* &quot; &amp;quot;

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
