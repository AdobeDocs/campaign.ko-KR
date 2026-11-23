---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 11%
---
# 만들기

지정된 스키마에 해당하는 새 엔티티를 만듭니다.

```text
create ( [content ])
```

## 매개변수

**content** 만들 엔터티의 XML에 해당하는 선택적 문자열입니다.

## 반환 값

JavaScript 개체 형태로 엔티티를 반환합니다.

## 비고

create 는 전역 함수가 아니라 스키마 메서드입니다. 호출하려면 원하는 스키마로 접두사를 지정해야 합니다. 예제:

```javascript
var recipient = NLWS.nmsRecipient.create(
      {recipient: {
        email: "support@adobe.com", 
        lastName: "Adobe", 
        firstName: "Support"}})
recipient.save()
```

문서가 자동으로 데이터베이스에 저장되지 않습니다. 엔터티에 ⌐⌐[save()](m-entity-save.md) 메서드를 사용해야 합니다.

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
