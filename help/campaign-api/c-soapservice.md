---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 7%
---
# SoapService(클래스)

웹 서비스에서 SOAP 호출을 수행할 수 있습니다.

## 호출 차단

다음은 일반적인 사용 예입니다. 먼저 연결을 만든 다음 이 연결을 사용하는 서비스를 만든 다음 이 서비스에 대한 SOAP 메서드를 마지막으로 선언해야 합니다. SOAP 메서드는 서비스 객체의 JavaScript 메서드의 형태로 노출된다.

```text
var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0) var session = new SoapService(cnx, "xtk:session") session.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) var result = session.GetOption("admin/", "NmsBroadcast_DefaultProvider") var value = result[0] var type = result[1] logInfo("Value = " + value) logInfo("Type = " + type)
```

## 비차단 호출

비차단(비동기) 호출을 수행할 수 있습니다. 즉, 서버에 SOAP 쿼리를 실행하고 결과를 기다리지 않고 스크립트를 계속 실행할 수 있습니다. 차단 모드와의 주요 차이점은 다음과 같습니다.

* 연결을 비동기 모드로 만들어야 합니다.

* 답변을 읽을 때마다

  [시작](m-soapservice-start.md)

  함수.

* 정의

  [완료](p-soapservice-complete.md)

  응답을 받을 때 호출되는 서비스의 기능입니다.

* 다음

  [SoapService.wait](m-soapservice-wait.md)

  함수는 쿼리 세트의 처리 종료를 기다리는 데 사용합니다.

다음 예제 스크립트는 3개의 연결을 동시에 열어 Adobe Campaign 서버에 대한 일련의 &#39;GetOption&#39; SOAP 호출을 만듭니다.

```text
var list = [ "XtkDatabaseId", "XtkKey", "WdbcTimeZone", "NmsServer_URL", "NmsBroadcast_DefaultProvider"] var requests = [] function complete(service, result, context, status) { if( status == "success" ) logInfo("option " + context + ": value = " + result[0]) else if( status == "fault" ) logInfo("option " + context + ": fault = " + result.message) else logInfo("option " + context + ": " + status) sendNext(service) } function createService() { // Create the connection var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0, true) // Create the service var service = new SoapService(cnx, "xtk:session") service.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) // Change the timeout to 5 seconds service.timeout = 5000 // Setup the callback function service.complete = complete return service } function sendNext(service) { if( list.length == 0) return // Pick an item from the list var name = list.shift() // Use the name as context var context = name // Send the request var req = service.start(context, "GetOption", "admin/", name) // Add the request to the wait queue requests.push(req) } // Open 3 connections and start a request on each one sendNext(createService()) sendNext(createService()) sendNext(createService()) SoapService.wait(requests) logInfo("Done.")
```

## 방법

| 방법 | 설명 |
| --- | --- |
| [SoapService](m-soapservice-soapservice.md) | 웹 서비스의 함수를 호출하는 서비스를 만듭니다. |
| [addMethod](m-soapservice-addmethod.md) | 서비스에서 함수를 선언합니다. |
| [dispose](m-soapservice-dispose.md) | 개체에서 사용하는 리소스를 해제합니다. |
| [시작](m-soapservice-start.md) | 비동기 모드에서 쿼리를 실행합니다. |
| [대기](m-soapservice-wait.md) | 비동기 SOAP 쿼리 목록이 끝날 때까지 기다립니다. |

## 속성

| 속성 | 설명 |
| --- | --- |
| [완료](p-soapservice-complete.md) | 비동기 쿼리가 완료되면 호출할 함수입니다. |
| [헤더](p-soapservice-header.md) | SOAP 헤더에 복사된 문자열 버바텀입니다. |
| [시간 초과](p-soapservice-timeout.md) | 비동기 쿼리의 경우 최대 대기 시간(밀리초)입니다. 이 매개 변수가 정의되지 않으면 대기 시간은 5분입니다. |

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 게재 메시지
* 유형화 규칙
* 가져오기
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
