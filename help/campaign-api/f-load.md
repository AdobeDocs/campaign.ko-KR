---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 8%
---
# 로드

> 경고:
>
> 파일 API를 통한 액세스는 Adobe Campaign의 **var**, **sftp** 및 임시 폴더로 제한됩니다.

주어진 스키마 및 키에 해당하는 엔티티를 로드하고 반환합니다.

```text
load (key)
```

## 매개변수

**key** 엔터티의 키에 해당하는 문자열입니다.

## 반환 값

JavaScript 개체 형태로 엔티티를 반환합니다.

## 비고

load는 전역 함수가 아니라 스키마 메서드입니다. 호출하려면 원하는 스키마로 접두사를 지정해야 합니다. 예제:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
```

이 개체의 속성 및 하위 속성은 언제든지 수정할 수 있습니다. [get()](f-get.md) 메서드와 달리 문서가 데이터베이스에 자동으로 저장되지 않으므로 개체에서 [save()](m-entity-save.md) 메서드를 호출해야 합니다. 데이터베이스에서 엔티티를 찾을 수 없는 경우 오류가 발생하고 스크립트가 중단됩니다.

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
