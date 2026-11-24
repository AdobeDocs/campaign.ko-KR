---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 6%
---
# cryptString

> 경고:
>
> 이 함수는 완전히 더 이상 사용되지 않습니다. 자세한 내용은 이 [페이지](https://experienceleague.adobe.com/ko/docs/campaign-classic/using/technotes/gcm-functions#deprecated-functions-headding-anchor-depracated-functions)를 참조하세요.

인스턴스 키 또는 다른 키로 문자 문자열을 암호화합니다.

```text
cryptString (str [, key ] [, useSalt ])
```

## 매개변수

**str** 암호화할 문자열입니다.

**키** 키 길이가 32인 경우 256비트, 키 길이가 24인 경우 192비트, 키 길이가 16이거나 키가 지정되지 않은 경우 128비트를 기준으로 AES 암호화 키가 인코딩됩니다.

**useSalt** 데이터의 소금을 사용하여 암호화합니다. 기본적으로 True입니다.

## 반환 값

암호화된 문자열 반환

## 비고

암호화는 다음 방법에 따라 수행됩니다.

* 유니코드 문자 문자열이 UTF-8 문자열로 변환됩니다.
* 확인 문자가 끝에 추가됩니다.
* 이 문자열은 CBC(Cipher Block Chaining) 모드의 AES 알고리즘을 사용하여 null 초기화 벡터로 암호화됩니다. 매개 변수로 제공된 키가 없는 경우 인스턴스 키가 사용됩니다.
* 그 다음 암호화된 블록은 베이스(64)로 변환된다.

암호 해독은 [decryptString](f-decryptstring.md) 함수를 사용하여 수행됩니다.

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
