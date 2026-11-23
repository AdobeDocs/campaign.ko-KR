---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 8%
---
# 헤더

이름별로 그룹화된 HTTP 응답에 대한 헤더 목록입니다.

```text
headers
```

## 비고

각 헤더 속성에는 헤더 이름과 이 이름과 일치하는 각 헤더와 테이블의 값이 전달되었습니다. 이 함수는 특정 이름에 대한 고유 값 대신 값 테이블을 반환하므로 [header](p-httpclientresponse-header.md)과(와) 다릅니다. 이 기능은 Accept-Language 또는 Set-Cookie와 같이 여러 번 나타날 수 있는 헤더에 유용합니다. HTTP 응답에 이 이름의 헤더가 없는 경우 함수는 빈 테이블을 반환합니다. 예:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = response
var cookies = response.headers["set-cookie"]
for each(var c in cookies)
{
  logInfo("Set-Cookie: " + c)
}
```

헤더 속성을 항목화할 수 없습니다. 속성 이름은 대소문자를 구분하지 않습니다.

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
