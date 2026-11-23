---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 12%
---
# getNewIds

내부 데이터베이스 키의 ID 목록을 반환합니다.

```text
getNewIds (count [, sequence ])
```

## 매개변수

**count** 메서드가 반환해야 하는 ID 수입니다.

**시퀀스** 사용할 시퀀스의 이름입니다.

## 반환 값

ID 목록이 포함된 표:

## 비고

이 메서드는 보다 효율적이지만 NLWS.xtkSession.GetNewIds() 및 NLWS.xtkSession.GetNewIdsEx() SOAP 메서드와 같습니다.

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
