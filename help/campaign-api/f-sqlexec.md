---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 6%
---
# sqlExec

SQL 스크립트를 실행합니다.

```text
sqlExec (query [, value1, ... ])
```

## 매개변수

**쿼리** SQL 쿼리입니다.

SQL 쿼리의 **value1, ...** 변수.

## 반환 값

UPDATE ou INSERT SQL 명령의 경우 업데이트되거나 삽입된 레코드 수입니다.

## 비고

변수는 명령의 매개 변수를 대체합니다. 변수 유형은 명령에서 선언된 매개 변수와 일치해야 합니다. 이러한 변수는 &#39;select&#39; 또는 &#39;update&#39; 형식 선언에서 사용할 수 있습니다. 다음과 같은 유형이 있습니다.

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
* $(dur) 시간 범위 en 밀리초(ms)

다음 대체 매개 변수(&quot;업데이트&quot;에만 유효함)는 자동으로 값으로 대체되며 연결된 변수는 필요하지 않습니다.

* $(id) 식별자 생성
* $(id:NmsTrackingLogId) 특정 시퀀스를 사용하여 식별자를 생성합니다.
* $(curdate) 현재 날짜 및 시간

이 함수를 사용하려면 연산자에게 &#39;sql&#39; 권한이 있어야 합니다. 그렇지 않으면 예외가 발생합니다. 예:

```javascript
      var sql4 = "INSERT INTO Reporting (sClientdesc,sClient) values ('" + client.@description.toString() + "','" + client.@clientCode.toString() +"')";
sqlExec(sql4);
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
