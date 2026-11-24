---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 12%
---
# 로그온

스크립트 실행 컨텍스트를 현재 로그인으로 변경합니다.

```text
logon (sessionToken)
```

```text
logon (login, password)
```

```text
logon (context)
```

## 매개변수

**sessionToken** 사용할 세션 토큰입니다.

**login** 사용할 연산자 로그인입니다.

**암호** 연산자 암호입니다. 현재 로그인에 &quot;관리자&quot; 권한이 있는 경우 암호는 빈 문자열이 될 수 있습니다.

**context** 로그인을 나타내는 개체로, 이전에 로그온을 호출하여 반환되었습니다.

## 반환 값

이전 로그인과 일치하는 개체를 반환합니다. 이렇게 하면 이 매개 변수를 로그온 함수에 전달하여 이전 로그인을 복원할 수 있습니다.

## 비고

예:

```javascript
var oldContext = logon("jdoe", "")

// ...

logon(oldContext)
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
