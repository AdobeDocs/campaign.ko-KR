---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 5%
---
# 실행

SQL 명령을 실행합니다.

```text
execute (command [, value1, ... ])
```

## 매개변수

**command** SQL 명령입니다.

명령의 **값1, ...** 변수.

## 반환 값

실행된 명령에 해당되는 경우 업데이트되거나 삽입된 레코드 수(그렇지 않은 경우 0).

## 비고

변수는 명령의 매개 변수를 대체하는 데 사용됩니다. 변수 형식은 명령에서 선언된 형식과 일치해야 합니다. 유형은 다음과 같습니다.

* $(sz) 문자열
* $(m) 메모
* $(l) 길이
* $(s) short
* $(b) 바이트
* $(d) double
* $(f) 부동
* $(ts) 타임스탬프
* $(dt) 날짜
* $(tm) 시간
* $(dur) 시간 범위 en 밀리초(ms)

다음 대체 매개 변수는 값으로 자동 대체되므로 관련 변수가 필요하지 않습니다.

* $(id) 식별자 생성
* $(id:NmsTrackingLogId) 특정 시퀀스를 사용하여 식별자를 생성합니다.
* $(curdate) 현재 날짜 및 시간

이 함수를 사용하려면 연산자에 &#39;sql&#39; 권한이 필요합니다. 그렇지 않으면 예외가 발생합니다.

## 기능

**클래스의 메서드:** [DBEngine](c-dbengine.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
