---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 13%
---
# sqlSelect

SQL 쿼리를 실행하고 결과를 XML 문서로 반환합니다.

```text
sqlSelect (format, query [, dataSource ])
```

## 매개변수

**format** 이름:type\[:length\] 형식 목록 docName, \[fieldXPath:type,\]\*으로 예상 데이터 형식을 설명하는 쉼표로 구분된 문자열

**쿼리** SQL 쿼리입니다.

**dataSource** 데이터 소스입니다.

## 반환 값

쿼리 결과의 각 행에 대한 요소 목록을 포함하는 XML 개체입니다.

## 비고

예:

```javascript
var res = sqlSelect("publicUrl,@sstringValue:string",
        "select sstringValue from XtkOption where sname='XtkFileRes_PublicUrl'")
logInfo(res.publicUrl.@sstringValue.toString())
```

```javascript
var xmlRes = sqlSelect("name:string,file:string:64","select relname, relfilenode from  pg_class WHERE relkind='r' AND pg_get_userbyid(relowner)<>'postgres';");
```

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
