---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 11%
---
# wait

비동기 SOAP 쿼리 목록이 끝날 때까지 기다립니다.

```text
wait (requests)
```

## 매개변수

쿼리 표를 **요청**&#x200B;합니다.

## 반환 값

없음.

## 비고

이 함수는 서비스에는 적용되지 않지만 SoapService bin의 함수입니다. 예:

```javascript
...
var req = service.start(1234, "GetOption", sessionToken, "XtkDatabaseId")

// Do some stuff here

// Wait until the end of the request
SoapService.wait( [req] )
```

쿼리가 완료되면 목록에서 자동으로 삭제됩니다. 즉, 함수가 컨트롤을 반환할 때 매개 변수로 전달된 테이블이 비어 있습니다. [complete](p-soapservice-complete.md) 함수에 의해 목록을 수정할 수 있습니다. 예를 들어 새 쿼리를 시작하고 목록에 추가할 수 있습니다.

## 기능

**클래스의 메서드:** [SoapService](c-soapservice.md)

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
