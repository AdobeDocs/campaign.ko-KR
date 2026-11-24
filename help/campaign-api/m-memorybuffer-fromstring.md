---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 18%
---
# fromString

문자열의 내용을 버퍼에 로드합니다.

```text
fromString (string [, codepage ])
```

## 매개변수

**문자열** 문자열.

버퍼에서 문자열을 직렬화하는 데 사용되는 **codepage** 코드 페이지입니다. 이 선택적 매개 변수를 사용하여 문자 인코딩을 지정할 수 있습니다. 예제:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## 반환 값

없음.

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
