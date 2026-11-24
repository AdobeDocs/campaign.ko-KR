---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%
---
# 본문

HTTP 쿼리의 본문.

```text
body
```

## 비고

쿼리 본문에 지정된 객체는 다음과 같이 처리됩니다.

* 정의되지 않음, null, 함수: 전송 가능한 요소로 간주되지 않으며 HTTP 쿼리의 본문이 비어 있습니다.
* number, boolean, string, XML, Object: toString 메서드를 기반으로 문자열로 변경되고 HTTP 헤더 Content-type을 기반으로 인코딩됩니다.
* [MemoryBuffer](c-memorybuffer.md): 콘텐츠가 변경 없이 쿼리 본문에 복사됩니다.

예:

```javascript
var query = "Select \"urn:schemas:calendar:uid\" " // etc...
var apptRequest =
  "<g:searchrequest xmlns:g="DAV:">\n" +
  "  <g:sql>\n" +
        query +
  "  </g:sql>\n" +
  "</g:searchrequest>"
http.body = apptRequest
    
```

## 기능

**클래스의 속성:** [HttpClientRequest](c-httpclientrequest.md)

**읽기 전용:**

아니요

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
