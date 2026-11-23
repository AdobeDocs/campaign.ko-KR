---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 20%
---
# HttpClientRequest

HTTP 클라이언트 쿼리를 실행할 새 개체를 만듭니다.

```text
HttpClientRequest ( [URL ])
```

## 매개변수

쿼리 수신자의 **URL** URL입니다.

## 반환 값

없음.

## 비고

FTP 명령이 실패하면 예외가 발생합니다. 예:

```javascript
var http = new HttpClientRequest("http://www.somewhere.com/login")

var buffer = new MemoryBuffer()
buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"

http.method = "SEARCH"
http.body = "<xml>any content</xml>"

http.execute()
       
```

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
