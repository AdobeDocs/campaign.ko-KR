---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 9%
---
# HttpSoapConnection

SOAP 서버에 대한 HTTP 연결을 만듭니다.

```text
HttpSoapConnection (url [, codepage ] [, protocol ] [, async ])
```

## 매개변수

경로를 포함하는 서버의 **url** URL입니다.

**codepage** SOAP 호출 직렬화를 위한 인코딩입니다. 이 선택적 매개 변수를 사용하여 문자 인코딩을 지정할 수 있습니다. 기본적으로 인코딩은 UTF-8입니다. 예:

* iso-8859-1
* utf-8
* utf-16

**프로토콜** 사용된 SOAP 프로토콜의 유형입니다. 이 선택적 매개 변수를 사용하면 사용된 SOAP 프로토콜(기본적으로 SOAP\_11)을 지정할 수 있습니다. 가능한 값은 다음과 같습니다.

* SOAP\_11: SOAP 프로토콜 1.1.
* SOAP\_12: SOAP 프로토콜 1.2.
* 0: Adobe Campaign 내부의 SOAP 프로토콜.

연결이 비동기 쿼리를 실행하도록 지정된 경우 **async** 부울을 true로 설정합니다. 기본적으로 false로 설정됩니다.

## 반환 값

없음.

## 비고

예:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp")
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-16", HttpSoapConnection.SOAP_11)
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-8", 0)
```

## 기능

**클래스의 메서드:** [HttpSoapConnection](c-httpsoapconnection.md)

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
