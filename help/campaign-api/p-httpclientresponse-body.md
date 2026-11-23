---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 12%
---
# 본문

MemoryBuffer 개체 형식의 HTTP 응답 본문입니다.

```text
body
```

## 비고

[codePage](p-httpclientresponse-codepage.md) 속성을 통해 응답 본문의 인코딩에 액세스할 수 있습니다. HTTP 응답의 본문은 [MemoryBuffer](c-memorybuffer.md) 개체 형식으로 제공됩니다. 따라서 [MemoryBuffer](c-memorybuffer.md)에 적용할 수 있는 모든 메서드는 HTTP 응답의 본문에 적용할 수 있습니다. 예:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
if( response.code != 200 )
  throw "HTTP request failed with " + response.message
var content = response.body.toString(response.codePage)
```

## 기능

**클래스의 속성:** [HttpClientResponse](c-httpclientresponse.md)

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
