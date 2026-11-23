---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 31%
---
# 저장

데이터베이스에 엔티티를 저장합니다.

```text
save ()
```

## 매개변수

없음.

## 반환 값

없음.

## 비고

예:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.label = "Diffusion 12345"
delivery.save()
```

## 기능

**클래스의 메서드:** [엔티티](c-entity.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
