---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 15%
---
# 난독화

정수를 문자열로 난독화합니다. [unobfuscate](f-unobfuscate.md)을(를) 호출하여 원래 값을 복구할 수 있습니다.

```text
obfuscate (value [, size ] [, version ])
```

## 매개변수

**값** 난독화할 정수입니다.

**size** 난독화로 인한 문자열 크기입니다. 6과 10 사이의 정수입니다. 기본적으로 6입니다.

**version** 적용할 난독화 버전입니다. 기본적으로 0입니다.

## 반환 값

난독화된 정수를 나타내는 문자열.

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
