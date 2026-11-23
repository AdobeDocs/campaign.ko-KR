---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 4%
---
# HttpClientRequest(클래스)

HttpClientRequest 개체를 사용하면 특정 작업을 HTTP 클라이언트로 수행할 수 있습니다.

예 :

```text
var req = new HttpClientRequest("http://www.somewhere.com/login") var buffer = new MemoryBuffer() buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1") req.header["Authorization"] = "Basic " + buffer.toBase64() req.header["Content-Type"] = "text/xml; charset=utf-8" req.method = "SEARCH" req.body = "<xml>any content</xml>" req.execute()
```

## &quot;Keep Alive&quot;

객체는 표준 또는 keep alive의 두 가지 모드로 사용할 수 있습니다. 표준 모드에서는 단일 쿼리를 보낼 수 있고, keep alive 모드에서는 연결을 열어 둔 채로 여러 쿼리를 보낼 수 있습니다. 개체의 상태는 메서드 사용 시퀀스에 따라 다릅니다. connect() 메서드가 호출되면 개체가 &quot;keep alive&quot; 모드로 전환됩니다. 예제

```text
var req = new HttpClientRequest("http://evc-cit.info/cgi-bin/cit042/timeofday.cgi") req.connect() // Now the object is in keep-alive mode, we can sand many requests using // the same connection // Request ten times the time of the cgi var i = 0 while ( i < 10 ) { req.execute() var response = req.reponse i++ } req.disconnect()
```

## 비동기 쿼리

쿼리는 기본적으로 차단 모드에서 실행됩니다. 즉,

[실행](m-httpclientrequest-execute.md)

함수는 쿼리가 전송되고 응답이 수신된 경우에만 제어를 반환합니다. 비동기 모드에서 쿼리를 실행할 수도 있습니다. 이 경우

[실행](m-httpclientrequest-execute.md)

함수는 제어를 즉시 반환하며, 응답이 수신되면 함수가 호출됩니다. 이렇게 하면 여러 쿼리를 동시에 실행할 수 있습니다. 다음 프로그램은 3개의 연결을 여는 동시에 일련의 HTTP 업로드를 실행하는 방법을 보여 주는 전체 예입니다. 각 업로드는 마지막 업로드가 완료되면 시작됩니다.

```text
var list = [ "http://www.adobe.com/", "http://www.google.com/", "http://www.mozilla.org/", "http://www.linux.org/", "http://www.postgresql.org/"] var requests = [] var complete = function(req, context, status) { if( status == "success" ) logInfo("Receiving " + context + ": " + req.url + ": code = " + req.response.code) else logWarning("Error " + context + ": " + req.url + ": " + status) sendNext(context) } function sendNext(context) { // Repeat until the first execute() passes while( list.length != 0 ) { // Pick one URL from the list var url = list.shift() var req = new HttpClientRequest(url) req.complete = complete try { req.execute(false, true, context, 5000) logInfo("Sending " + url) requests.push(req) return } catch(e) { // Log a message and pick up next item from list logWarning("Failed to send " + url) } } } // Start 3 requests sendNext(1) sendNext(2) sendNext(3) // Wait until all requests are completed HttpClientRequest.wait(requests) logInfo("Finished.")
```

## 방법

| 방법 | 설명 |
| --- | --- |
| [HttpClientRequest](m-httpclientrequest-httpclientrequest.md) | HTTP 클라이언트 쿼리를 실행할 새 개체를 만듭니다. |
| [연결](m-httpclientrequest-connect.md) | HTTP 연결을 열고 개체를 &quot;keep-alive&quot; 모드로 전달합니다. |
| [연결 끊기](m-httpclientrequest-disconnect.md) | &quot;keep-alive&quot; 모드에서 개체의 HTTP 연결을 닫습니다. |
| [실행](m-httpclientrequest-execute.md) | HTTP 쿼리를 실행합니다. |
| [대기](m-httpclientrequest-wait.md) | 비동기 쿼리 목록이 끝날 때까지 기다립니다. |

## 속성

| 속성 | 설명 |
| --- | --- |
| [본문](p-httpclientrequest-body.md) | HTTP 쿼리의 본문. |
| [완료](p-httpclientrequest-complete.md) | 비동기 쿼리가 완료되면 호출할 함수입니다. |
| [헤더](p-httpclientrequest-header.md) | 헤더의 HTTP 헤더가 포함된 JavaScript 개체. |
| [메서드](p-httpclientrequest-method.md) | 문자열 형식의 HTTP 메서드 |
| [응답](p-httpclientrequest-response.md) | HTTP 쿼리의 응답입니다. HttpClientResponse 유형 개체입니다. |
| [url](p-httpclientrequest-url.md) | 원격 서버의 주소입니다. |

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
