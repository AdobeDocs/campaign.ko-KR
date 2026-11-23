---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 26%
---
# Soap 서비스

웹 서비스의 함수를 호출하는 서비스를 만듭니다.

```text
SoapService (cnx, namespace)
```

## 매개변수

**cnx** ([HttpSoapConnection](c-httpsoapconnection.md)) HTTP 연결입니다.

서비스의 **네임스페이스** 네임스페이스입니다.

## 반환 값

없음.

## 비고

예:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
```

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
