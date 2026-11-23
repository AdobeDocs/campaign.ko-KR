---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 16%
---
# getConnection

데이터베이스 서버에 대한 새 연결을 반환합니다.

```text
getConnection ()
```

## 매개변수

없음.

## 반환 값

데이터베이스 서버에 대한 [연결](c-dbengine.md)입니다.

## 비고

[dispose](m-dbengine-dispose.md) 메서드를 사용하여 스크립트 실행이 종료되기 전에 연결을 해제할 수 있습니다.

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
