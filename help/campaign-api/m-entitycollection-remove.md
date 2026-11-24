---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 20%
---
# 제거

컬렉션에서 엔티티를 삭제합니다.

```text
remove (index|object)
```

## 매개변수

**index\|object** 삭제할 엔터티 또는 엔터티 자체의 색인입니다.

## 반환 값

없음.

## 비고

예:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.remove(1)
delivery.save()
```

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
var attach = delivery.attachment[1]
delivery.attachment.remove(attach)
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
