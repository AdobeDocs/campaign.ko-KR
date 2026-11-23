---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 9%
---
# getSchema

Adobe Campaign 스키마에 대한 매핑을 반환하거나 스키마가 존재하지 않는 경우 null을 반환합니다.

```text
getSchema (name [, checkIfUpdated ])
```

## 매개변수

**이름** 전체 스키마 이름.

**checkIfUpdated** 캐시에서 스키마가 업데이트되었는지 확인합니다. 스키마가 이미 스크립트에 인스턴스화된 경우에는 영향을 주지 않습니다.

## 반환 값

스키마 매핑([Schema](c-schema.md) 개체 참조) 또는 메서드 시작 예외는 이름과 일치하는 스키마가 없습니다.

## 비고

스크립트에 설치된 모든 스키마는 스크립트가 종료될 때까지 메모리에 할당된 상태로 유지됩니다. 예:

```javascript
      var schema = application.getSchema("nms:recipient")
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
