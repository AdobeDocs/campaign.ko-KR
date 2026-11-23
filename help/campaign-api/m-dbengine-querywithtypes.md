---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 15%
---
# queryWithTypes

열 유형 지정으로 SELECT 유형 SQL 쿼리를 실행합니다.

```text
queryWithTypes (command, types [, value1, ... ])
```

## 매개변수

**command** SQL 명령입니다.

열 형식을 포함하는 **types** 테이블입니다.

**value1, ...** 명령 변수.

## 반환 값

쿼리 결과를 반복할 수 있는 커서.

## 비고

경고: 기능 섹션에 설명된 것과 달리 queryWithTypes 함수는 WebApp에서 사용할 수 없습니다. 함수가 추가된 열 형식을 사용하는 [query](m-dbengine-query.md)과(와) 동일합니다. 대부분의 경우 열 유형은 자동으로 추론될 수 있으므로 사용되지 않습니다. 따라서 [쿼리](m-dbengine-query.md)를 선호해야 합니다. 그러나 경우에 따라 특히 Oracle 및 날짜 유형 열을 사용하면 형식을 명시적으로 지정해야 할 수 있습니다. 열 유형은 다음 목록에 있는 문자 문자열입니다.

* 문자열
* datetime
* 날짜
* 시간
* timespan
* 중복
* 부동
* 부울
* 바이트
* short
* 롱
* int64
* 메모
* blob
* 링크
* 빈

예:

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)",
                     ["long", "string", "datetime"],
                     1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

이 함수를 사용하려면 연산자에 &#39;sql&#39; 권한이 있어야 합니다. 그렇지 않으면 예외가 발생합니다.

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
