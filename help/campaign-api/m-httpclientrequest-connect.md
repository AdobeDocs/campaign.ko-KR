---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 9%
---
# 연결

HTTP 연결을 열고 개체를 &quot;keep-alive&quot; 모드로 전달합니다.

```text
connect ( [hasProxy ] [, async ])
```

## 매개변수

프록시 HTTP를 사용해야 하는 경우 **hasProxy** 부울을 true로 설정합니다. 기본적으로 false로 설정됩니다.

연결이 비동기 쿼리를 실행하도록 지정된 경우 **async** 부울을 true로 설정합니다. 기본적으로 false로 설정됩니다.

## 반환 값

없음.

## 비고

HTTP 연결에 실패하면 예외가 발생합니다. 응답 속성은 execute 함수를 성공적으로 호출한 후에만 유효합니다. 연결 사용을 마친 후에는 disconnect()를 호출하는 것을 잊지 마십시오. 예:

```javascript
// Mistake with the hostname gogle instead of google
var badHttp = new HttpClientRequest("www.gogle.fr");
try {
  badHttp.connect();
} catch (e) {
  // Here an exception has been raised
}

var goodHttp = new HttpClientRequest("www.google.fr");
try {
  goodHttp.connect();
} catch (e) {
  // No exeception raised
}
...
goodHttp.disconnect();
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
