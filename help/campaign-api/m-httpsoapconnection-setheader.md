---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 16%
---
# setHeader

HTTP 헤더를 지정합니다.

```text
setHeader (headerName, headerValue)
```

## 매개변수

**headerName** HTTP 헤더의 이름인 문자열.

**headerValue** HTTP 헤더의 콘텐츠인 문자 문자열입니다.

## 반환 값

없음.

## 비고

Les en-têtes ainsi spécifiés prévalid sur les en-têtes par défaut lors des appels SOAP. 예 :

```javascript
      var cnx = new HttpSoapConnection("http://localhost/test/Service1.asmx");
var memBuf = new MemoryBuffer();
memBuf.fromString("rico:pass@word1")
cnx.setHeader("Authorization","Basic " + memBuf.toBase64());
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
