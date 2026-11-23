---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 15%
---
# batchDelete

패킷별로 테이블의 레코드를 삭제합니다.

```text
batchDelete (table, pk [, where ])
```

## 매개변수

테이블의 **테이블** SQL 이름입니다.

**pk** 필드 이름이 기본 키로 사용되었습니다.

**where** SQL 레코드 필터링 조건

## 반환 값

없음.

## 비고

예:

```javascript
      engine.batchDelete("NmsRecipient", "iRecipientId", "sName IS NULL")
```

이 함수를 사용하려면 연산자에 &#39;sql&#39; 권한이 필요합니다. 그렇지 않으면 예외가 발생합니다.

## 기능

**클래스의 메서드:** [DBEngine](c-dbengine.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
