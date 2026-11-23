---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 19%
---
# 헤더

모든 HTTP 헤더를 포함하는 객체입니다.

```text
header
```

## 비고

속성 이름은 대/소문자를 구분하지 않습니다. 예:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
for(var i in response.header)
  logInfo("header[" + i + "] => " + response.header[i])
    
```

같은 이름의 여러 헤더를 복구하려면 헤더 속성 대신 [headers](p-httpclientresponse-headers.md) 속성을 사용하십시오.

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
