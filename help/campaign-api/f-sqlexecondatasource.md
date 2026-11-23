---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 8%
---
# sqlExecOnDataSource

데이터 소스에서 SQL 스크립트를 실행합니다.

```text
sqlExecOnDataSource (query, dataSource [, value1, ... ])
```

## 매개변수

**쿼리** SQL 쿼리입니다.

**dataSource** 데이터 소스입니다.

SQL 쿼리의 **value1, ...** 변수.

## 반환 값

UPDATE 또는 INSERT SQL 명령에 업데이트되거나 삽입된 레코드 수입니다.

## 비고

데이터 소스에 대해 승인된 값은 다음과 같습니다.

* &quot;&quot; 또는 &quot;default&quot;는 Adobe Campaign 데이터베이스를 가리킵니다

* &quot;nms:extAccount:InternalName&quot;은(는) Adobe Campaign 외부 계정(FDA)에 정의된 데이터 소스를 가리킵니다

* &quot;name&quot;(데이터 소스의 이름)은 다음 형식의 인스턴스 구성 파일(config-instance.xml)에 정의된 데이터 소스를 가리킵니다.

  ```xml
                   <dataStore hosts="*" lang="">
        <dataSource name="datasourcename">
          <dbcnx encrypted="" login="" password=""
                 provider="" server=""/>
        </dataSource>
      </dataStore>
  ```

예:

```javascript
sqlExecOnDataSource("UPDATE XtkOption SET sStringValue = $(sz) WHERE sName = $(sz)", oracleExternalDB, 'WdbcOptions_TableSpaceWork_nms:extAccount:' + sExtAccount)
```

이 함수의 매개 변수로 설정된 선택적 변수는 [sqlGetString(query, value1, ...)](f-sqlgetstring.md)에 정의되어 있습니다.

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
