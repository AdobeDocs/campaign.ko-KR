---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 6%
---
# encryptDES

> 경고:
>
> 이 함수는 더 이상 사용되지 않습니다. [cryptString()](f-cryptstring.md)을(를) 사용하십시오.

DES 알고리즘으로 문자열을 암호화합니다.

```text
encryptDES (key, value [, cipher mode ] [, initialization vector ] [, padding ])
```

## 매개변수

**key** 16진수로 표시된 키입니다. 키는 64비트 길이, 즉 16개의 16진수 문자여야 합니다.

**값** 암호화할 문자열

**암호화 모드** 블록을 코딩하는 방법입니다. 일련의 문자들. 예: &quot;CBC&quot;, &quot;ECB&quot; 또는 &quot;EDE&quot;. 기본적으로 &quot;CBC&quot;입니다.

**초기화 벡터** 16진수 문자열 형식의 초기화 벡터입니다. 정확히 8옥텟, 즉 16자. 기본적으로 빈 문자열.

**패딩** 패딩의 유형입니다. 문자열(예: &quot;PKCS5PADDING&quot; 또는 &quot;PKCS7PADDING&quot;). 기본적으로 빈 문자열이 있으며, 이는 암호화할 문자열 끝에 &#39;\\0&#39;이(가) 추가됨을 의미합니다.

## 반환 값

밑줄 64에 표시된 암호화된 문자열.

## 비고

* DES 키에는 56개의 유용한 비트와 패리티에 사용되는 8개의 비트가 있으며 이러한 비트는 무시됩니다.
* DES 알고리즘에 의해 효과적으로 암호화된 값은 문자열의 8비트 Windows-1252 표현이며, ASCII 0 문자로 끝나고 이진 0으로 64비트의 배수로 채워집니다.
* 암호화된 값은 64비트 단어의 배수입니다.

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
