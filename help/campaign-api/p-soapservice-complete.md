---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 6%
---
# 완료

비동기 쿼리가 완료되면 호출할 함수입니다.

```text
complete
```

## 비고

함수는 다음 네 가지 인수를 수락해야 합니다.

* 서비스
* 결과
* 컨텍스트: [start](m-soapservice-start.md) 함수에 전달된 매개 변수입니다.
* 상태

상태는 다음 값을 가질 수 있습니다.

* &quot;성공&quot;은 결과를 받았음을 의미합니다.
* &quot;오류&quot;는 통신이 중단되었거나, 응답이 잘못 구성되었거나, HTTP 오류가 발생했음을 의미할 수 있습니다.
* SOAP 오류가 반환되는 경우 &quot;fault&quot;. 이 경우 결과에는 오류를 설명하는 오브젝트가 포함됩니다.
* &quot;timeout&quot;은 연결을 설정할 수 없거나 구성된 기한 내에 응답을 받지 못했음을 의미합니다.

결과가 &quot;성공&quot;인 경우 결과는 반환되는 매개 변수의 수에 따라 달라집니다.

* 쿼리가 값을 반환하지 않으면 void
* 쿼리가 단일 매개 변수를 반환하는 경우 값
* 쿼리가 여러 매개 변수를 반환하는 경우 테이블

상태가 &quot;fault&quot;이면 결과는 다음 속성을 포함하는 객체입니다.

* message: 오류 설명 메시지입니다.
* 객체: 오류의 세부 정보가 포함된 XML 객체입니다.

예:

```javascript
http.complete = function(result, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + result[0])
}
```

## 기능

**클래스의 속성:** [SoapService](c-soapservice.md)

**읽기 전용:**

아니요

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 게재 메시지
* 유형화 규칙
* 가져오기
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
