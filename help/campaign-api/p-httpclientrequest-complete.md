---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 9%
---
# 완료

비동기 쿼리가 완료되면 호출할 함수입니다.

```text
complete
```

## 비고

함수는 다음 세 가지 인수를 수락해야 합니다.

* 쿼리
* 컨텍스트
* 상태: &quot;success&quot;, &quot;error&quot; 또는 &quot;timeout&quot;

&quot;성공&quot; 상태는 응답이 수신되었지만 응답이 모든 코드(200, 404, 503 등)를 가질 수 있음을 의미합니다. 오류 상태는 잘못 구성된 응답의 통신 중단을 가리킬 수 있습니다. 시간 초과 상태는 연결을 설정할 수 없거나 구성된 기한 내에 응답을 받지 못했음을 의미합니다. 예:

```javascript
http.complete = function(req, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + req.response.code)
}
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
