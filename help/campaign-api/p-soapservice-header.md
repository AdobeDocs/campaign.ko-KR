---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 28%
---
# 헤더

SOAP 헤더에 복사된 문자열 버바텀입니다.

```text
header
```

## 비고

Les chaînes de caractères sont recopiées in-extendso dans l&#39;en-tête SOAP sans vériification. 예:

```javascript
      var cnx = new HttpSoapConnection(result.serverURL, "utf-8", HttpSoapConnection.SOAP_11)
var service = new SoapService(cnx, "urn:partner.soap.sforce.com")
service.header = "<ns1:SessionHeader xmlns:ns1='urn:partner.soap.sforce.com'><ns1:sessionId>123456</ns1:sessionId></ns1:SessionHeader>"
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
