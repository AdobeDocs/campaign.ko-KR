---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 14%
---
# dispose

연결된 모든 리소스에서 연결을 해제합니다.

```text
dispose ()
```

## 매개변수

없음.

## 반환 값

없음.

## 비고

[application.getConnection()](m-application-getconnection.md) 메서드를 사용하여 만든 연결은 스크립트 끝에 자동으로 해제됩니다. 이 메서드를 호출하면 긴 수명을 가질 수 있는 스크립트에 유용합니다.

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
