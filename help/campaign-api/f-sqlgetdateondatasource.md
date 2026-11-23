---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 11%
---
# sqlGetDateOnDataSource

데이터 원본에 대한 SQL 쿼리의 결과 날짜를 반환합니다.

```text
sqlGetDateOnDataSource (query, dataSource [, value1, ... ])
```

## 매개변수

**쿼리** SQL 쿼리입니다.

**dataSource** 데이터 소스입니다.

SQL 쿼리의 **value1, ...** 변수.

## 반환 값

쿼리와 일치하는 날짜 유형 값입니다.

## 비고

&quot;data source&quot; 매개 변수는 [sqlExecOnDataSource(query, dataSource, value1, ...)](f-sqlexecondatasource.md)에 정의되어 있습니다. 함수 이 함수의 매개 변수인 선택적 변수는 [sqlGetString(query, value1, ...)](f-sqlgetstring.md)에 정의되어 있습니다.

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
