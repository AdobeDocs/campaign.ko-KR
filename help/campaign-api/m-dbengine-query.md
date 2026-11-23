---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 4%
---
# 쿼리

SELECT 유형 SQL 쿼리를 실행합니다.

```text
query (command [, value1, ... ])
```

## 매개변수

**command** SQL 명령입니다.

명령의 **값1, ...** 변수.

## 반환 값

쿼리 결과를 반복할 수 있는 커서.

## 비고

경고: 기능 섹션에 설명된 것과 달리 쿼리 함수는 WebApp에서 사용할 수 없습니다. 변수는 명령의 매개 변수를 대체합니다. 변수 형식은 명령에서 선언된 매개 변수와 일치해야 합니다. 다음 유형을 사용할 수 있습니다.

* $(sz) 문자열
* $(m) 메모
* $(l) 길이
* $(s) short
* $(b) 바이트
* $(d) double
* $(f) 부동
* $(ts) 타임스탬프
* $(dt) 날짜
* $(tm) 시간
* $(dur) 기간

다음 대체 매개 변수는 값으로 자동 대체되므로 연결된 변수가 필요하지 않습니다.

* $(id) 식별자 생성
* $(id:NmsTrackingLogId) 특정 시퀀스를 사용하여 식별자를 생성합니다.
* $(curdate) 현재 날짜 및 시간

커서에 대한 반복은 &quot;for each&quot;를 통해 발생하며 복구된 각 행에 대한 테이블을 반환합니다. 테이블의 각 요소는 쿼리의 필드와 일치하고 요소 유형은 필드의 유형에 따라 다릅니다. 예:

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)", 1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

이 예에서 row\[0\]은 iOperatorId와 일치하는 숫자이고, row\[1\]은 sName과 일치하는 문자 문자열이며, row\[2\]는 tsLastModified와 일치하는 날짜입니다. 이 함수를 사용하려면 연산자에 &#39;sql&#39; 권한이 필요합니다. 그렇지 않으면 예외가 발생합니다.

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
