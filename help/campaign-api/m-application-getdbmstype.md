---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 9%
---
# getDBMSType

데이터베이스의 서버 유형을 반환합니다.

```text
getDBMSType ( [name ] [, checkIfUpdated ])
```

## 매개변수

데이터 원본의 **이름** 이름입니다.

**checkIfUpdated** 캐시에서 스키마가 업데이트되었는지 확인합니다. 스키마가 스크립트에 이미 인스턴스화된 경우 영향을 주지 않습니다.

## 반환 값

데이터베이스의 서버 유형을 포함하는 텍스트 문자열입니다.

## 비고

데이터 원본이 지정되지 않은 경우 이 함수는 기본적으로 &#39;nms:default&#39;을 사용합니다. 데이터 소스가 있어야 합니다. 그렇지 않으면 예외가 발생합니다.

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
