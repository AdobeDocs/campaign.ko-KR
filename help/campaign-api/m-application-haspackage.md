---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 23%
---
# hasPackage

패키지가 설치되었는지 테스트합니다.

```text
hasPackage (name)
```

## 매개변수

패키지의 **이름** 전체 이름.

## 반환 값

패키지가 설치된 경우 True입니다.

## 비고

예:

```javascript
var hasMRM = application.hasPackage("nms:mrm")
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
