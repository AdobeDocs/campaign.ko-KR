---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 27%
---
# 열거형

이 스키마에 정의된 [열거형](c-enumeration.md) 목록을 포함하는 테이블을 반환합니다.

```text
enumerations
```

## 비고

예:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var e in schema.enumerations)
{
  logInfo(e.name)
}
```

## 기능

**클래스의 속성:** [스키마](c-schema.md)

**읽기 전용:**

예

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
