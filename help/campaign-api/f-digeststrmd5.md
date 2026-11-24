---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 16%
---
# digestStrMd5

> 경고:
>
> 이 함수는 개인 정보를 기반으로 해시를 만드는 데 사용해서는 안 됩니다.

문자 문자열에 대한 MD5 해시 함수를 계산합니다. 이 문자열은 계산 전에 자동으로 UTF-8로 코딩됩니다.

```text
digestStrMd5 (string)
```

## 매개변수

**string** 해시 함수를 계산할 문자열입니다.

## 반환 값

문자열의 MD5 해시가 매개 변수로 전달되었습니다.

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
