---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 14%
---
# 헤더

헤더의 HTTP 헤더가 포함된 JavaScript 개체.

```text
header
```

## 비고

헤더 개체의 모든 속성은 읽기/쓰기 모드에서 액세스할 수 있으며 열거형입니다. 헤더 객체의 각 소유자는 쿼리의 HTTP 헤더에 있는 항목입니다. 속성 이름은 대소문자를 구분하지 않습니다(HTTP 헤더의 경우). 예:

```javascript
var http = new HttpClientRequest(url)

var buffer = new MemoryBuffer()
buffer.fromString(userName + ':' + password, "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"
http.header["Date"] = (new Date()).toGMTString()
//Note: http.header.Date == http.header.date

for( var i in http.header )
logInfo("header[" + i + "] => " + http.header[i])
```

## 기능

**클래스의 속성:** [HttpClientRequest](c-httpclientrequest.md)

**읽기 전용:**

예

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
