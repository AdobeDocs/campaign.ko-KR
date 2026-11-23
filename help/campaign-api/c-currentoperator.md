---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 9%
---
# CurrentOperator(클래스)

현재 연산자에 대한 정보가 포함된 개체(이름, 식별자, 권한 등)입니다.

이 클래스에는 응용 프로그램 서버의 특정 속성에 대한 액세스를 제공하는 단일 인스턴스가 있습니다. 이 단일 항목은 `application` 전역 변수의 속성을 통해 액세스할 수 있습니다.

예:

```text
var operator = application.operator logInfo("login: " + operator.login) logInfo("id: " + operator.id) logInfo("description: " + operator.computeString) logInfo("=== Groups ===") for each(var id in operator.groups) logInfo(id) logInfo("=== Rights ===") for each(var right in operator.rights) logInfo(right)
```

## 방법

| 방법 | 설명 |
| --- | --- |
| [hasRight](m-currentoperator-hasright.md) | 연산자에 특정 명명된 권한이 있는지 테스트합니다. |

## 속성

| 속성 | 설명 |
| --- | --- |
| [로그인](p-currentoperator-login.md) | 현재 연산자의 로그인을 반환합니다. |
| [id](p-currentoperator-id.md) | 현재 연산자의 내부 식별자를 반환합니다. |
| [computeString](p-currentoperator-computestring.md) | 현재 연산자 설명 문자열을 반환합니다. 기본적으로 연산자 이름 다음에 해당 로그인이 옵니다. |
| [그룹](p-currentoperator-groups.md) | 현재 연산자 그룹의 식별자 목록을 반환합니다. |
| [권한](p-currentoperator-rights.md) | 현재 연산자의 권한 목록을 반환합니다. |
| [표준 시간대](p-currentoperator-timezone.md) | 현재 연산자에 사용된 표준 시간대 이름을 반환합니다. |
| [홈](p-currentoperator-home.md) | 현재 연산자의 루트 폴더 이름을 반환합니다. |

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
