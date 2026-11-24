---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 15%
---
# escapeUrl

문자열을 URL에 삽입하도록 변환합니다.

```text
escapeUrl (value)
```

## 매개변수

변환할 **값** 문자열.

## 반환 값

변환 후 문자열입니다.

## 비고

이 함수는 $-\_.\!\*&#39;(),?/:@&amp;= 이외의 영문자가 아닌 문자를 해당 16진수 값으로 변환합니다. 이 함수는 RFC1738 사양을 준수하며 ISO-라틴 문자만 인코딩할 수 있습니다. UTF-8 문자를 인코딩하려면 encodeURIComponent() JavaScript 함수를 사용합니다. 예:

```javascript
escapeUrl("a#value!")               // "a%23value!"
escapeUrl("Système d'exploitation") // "Syst%E8me%20d'exploitation"
```

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
