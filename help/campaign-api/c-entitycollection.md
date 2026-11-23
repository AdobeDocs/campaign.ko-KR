---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 14%
---
# EntityCollection(클래스)

엔티티의 컬렉션을 나타냅니다.

이러한 개체는 직접 인스턴스화할 수 없습니다. create(), get() 또는 load() 메서드를 사용해야 합니다.

컬렉션의 요소는 `for` 또는 `for each`(으)로 열거될 수 있습니다. 이 예제에서는 게재 작업에 연결된 파일 열거형을 보여 줍니다.

```text
var delivery = NLWS.nmsDelivery.load("12345") for each(var attach in delivery.attachment) logInfo(attach.label)
```

## 방법

| 방법 | 설명 |
| --- | --- |
| [추가](m-entitycollection-add.md) | 새 엔티티를 컬렉션에 추가합니다. |
| [제거](m-entitycollection-remove.md) | 컬렉션에서 엔티티를 삭제합니다. |
| [removeAll](m-entitycollection-removeall.md) | 컬렉션에서 모든 엔티티를 삭제합니다. |

## 속성

| 속성 | 설명 |
| --- | --- |
| [길이](p-entitycollection-length.md) | 컬렉션의 엔티티 번호를 반환합니다. |

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
