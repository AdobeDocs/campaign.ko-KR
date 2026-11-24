---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 14%
---
# toBase64

밑줄 64에 인코딩된 문자열의 버퍼 또는 일부를 변환합니다.

```text
toBase64 ( [start ] [, length ])
```

## 매개변수

**start** 버퍼 시작 시 무시할 바이트 수입니다. 첫 번째 바이트는 값 0(기본값)에 해당합니다.

**length** 변환할 바이트 수입니다. 기본적으로 나머지 모든 바이트가 고려됩니다.

## 반환 값

베이스(64)에 인코딩된 버퍼의 콘텐츠.

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
