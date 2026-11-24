---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 6%
---
# wait

비동기 쿼리 목록이 끝날 때까지 기다립니다.

```text
wait (requests,waitAll)
```

## 매개변수

쿼리 표를 **요청**&#x200B;합니다.

**waitAll** 부울(기본적으로 true)입니다. 쿼리 목록의 모든 요청이 완료될 때까지 기다리십시오. false로 설정하면, 하나 이상의 요청이 완료되면 함수가 수신 루프를 벗어납니다.

## 반환 값

없음.

## 비고

이 함수는 쿼리에 적용되지 않지만 HttpClientRequest 빈의 함수입니다. 예:

```javascript
var req = new HttpClientRequest("http://www.adobe.com/kr/")
req.complete = function(req, context, status) { logInfo(status) }
req.execute(false, true)

HttpClientRequest.wait( [req] )
```

쿼리는 비동기적이고 [execute](m-httpclientrequest-execute.md) 호출에서 예외를 발생시키지 않은 경우에만 목록에 추가할 수 있습니다. 쿼리가 완료되면 목록에서 자동으로 삭제됩니다. 즉, 함수가 컨트롤을 반환할 때 매개 변수로 전달된 테이블이 비어 있습니다. [complete](p-httpclientrequest-complete.md) 함수에 의해 목록을 수정할 수 있습니다. 예를 들어 새 쿼리를 시작하고 목록에 추가할 수 있습니다.

## 기능

**클래스의 메서드:** [HttpClientRequest](c-httpclientrequest.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
