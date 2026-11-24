---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 6%
---
# 실행

HTTP 쿼리를 실행합니다.

```text
execute ( [hasProxy ] [, async ] [, reuseaddr ] [, context ] [, timeout ])
```

## 매개변수

HTTP 프록시를 사용해야 하는 경우 **hasProxy** 부울을 true로 설정합니다. 기본적으로 false로 설정됩니다.

쿼리가 비동기이면 **async** 부울을 true로 설정합니다. 기본적으로 false로 설정됩니다.

기본 소켓에서 로컬 주소를 다시 사용할 수 있도록 허용해야 하는 경우 **reuseaddr** 부울을 true로 설정합니다. 기본적으로 false로 설정됩니다.

**context** 컨텍스트는 비동기 쿼리의 경우 [complete](p-httpclientrequest-complete.md) 함수의 두 번째 인수로 전달되는 모든 개체입니다.기본적으로 null로 설정됩니다.

비동기 쿼리의 경우 **시간 초과** 최대 대기 시간(밀리초)입니다. 이 매개 변수가 정의되지 않으면 대기 시간은 5분입니다.

## 반환 값

없음.

## 비고

HTTP 연결에 실패하면 예외가 발생합니다. [response](p-httpclientrequest-response.md) 속성은 execute 함수를 성공적으로 호출한 후에만 유효합니다. 예:

```javascript
          
        var http = new HttpClientRequest("http://www.google.com")
        http.method = "GET"
        // Note: Here, http.response == undefined
        http.execute()
        var response = http.response
      
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
