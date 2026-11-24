---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 5%
---
# getTimezoneJson

시간대의 UNIX 기간과 비교한 UTC 시간 및 시작 날짜와의 시간 차이 목록의 JSON 표현인 문자열을 반환합니다.

```text
getTimezoneJson ( [timezone ])
```

## 매개변수

**표준 시간대** UTC와 비교하여 시간 차이 목록을 반환해야 하는 표준 시간대의 이름입니다. 각 시간 차이는 다음 시작 날짜까지 적용할 수 있는 시작 날짜에 연결됩니다. 값이 반환되지 않으면 에서는 기본 연산자 시간대를 사용합니다.

## 반환 값

날짜를 기반으로 적용할 시간 차이의 JSON 표현인 문자열을 반환합니다. 반환된 JSON 문자열은 {startDate, offset} 커플 테이블에 평가됩니다. 반환된 문자열의 형식은 다음과 같습니다.

```javascript
[
  {"startDate" : -1855958901000, "offset" : 0},
  {"startDate" : -1689814800000, "offset" : 3600000}
]
```

* startDate는 경과가 적용되는 Posix 시간입니다.
* offset 은 UTC와의 시간 차 값(밀리초)입니다. 예를 들어 UTC+02:00은 7200000입니다.

## 비고

getTimezoneJson은 애플리케이션 인스턴스를 통해 호출됩니다.

```javascript
var tzList = eval(application.getTimezoneJson());
```

## 기능

**클래스의 메서드:** [응용 프로그램](c-application.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
