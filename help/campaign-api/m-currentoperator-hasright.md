---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 23%
---
# hasRight

연산자에 특정 명명된 권한이 있는지 테스트합니다.

```text
hasRight (name)
```

## 매개변수

**이름** 오른쪽 이름.

## 반환 값

연산자에 이 권한이 있는 경우 True입니다.

## 비고

예:

```javascript
      var hasAdminRight = application.operator.hasRight("admin")
```

## 기능

**클래스의 메서드:** [CurrentOperator](c-currentoperator.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
