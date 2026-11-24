---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 8%
---
# decryptDES

> 경고:
>
> 이 함수는 더 이상 사용되지 않습니다. [decryptString()](f-decryptstring.md)을(를) 사용하십시오.

DES 알고리즘으로 문자열의 암호화를 해제합니다.

```text
decryptDES (key, value [, cipher mode ] [, initialization vector ])
```

## 매개변수

**key** 16진수로 표시된 키입니다. 키는 64비트 길이 또는 16개의 16진수 문자여야 합니다.

**값** 암호화할 데이터는 Base 64에 표시됩니다.

**암호화 모드** 블록을 코딩하는 방법입니다. 일련의 문자들. 예: &quot;CBC&quot;, &quot;ECB&quot; 또는 &quot;EDE&quot;. 기본적으로 &quot;CBC&quot;입니다.

**초기화 벡터** 16진수 문자열 형식의 초기화 벡터입니다. 정확히 8옥텟, 즉 16자. 기본적으로 빈 문자열.

## 반환 값

지우기 텍스트의 문자 문자열.

## 비고

* DES 키에는 56개의 유용한 비트와 패리티에 사용되는 8개의 비트가 있으며 이러한 비트는 무시됩니다.
* 데이터는 Windows 1252 코드 페이지에서 8비트 문자열로 암호화되지 않습니다.
* 암호화된 데이터의 길이는 64비트의 배수여야 한다.

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
