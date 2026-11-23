---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 31%
---
# removeAll

컬렉션에서 모든 엔티티를 삭제합니다.

```text
removeAll ()
```

## 매개변수

없음.

## 반환 값

없음.

## 비고

예:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.removeAll()
delivery.save()
```

## 기능

**클래스의 메서드:** [EntityCollection](c-entitycollection.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
