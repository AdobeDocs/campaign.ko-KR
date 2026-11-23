---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 5%
---
# decryptPassword

> 경고:
>
> 이 설명서는 업데이트되었습니다. 자세한 내용은 이 [페이지](https://experienceleague.adobe.com/en/docs/campaign-classic/using/technotes/gcm-functions#decryptpassword-headding-anchor-decryptpassword-javascript)를 참조하세요.

외부 계정에 저장된 암호를 해독합니다.

```text
decryptPassword (str)
```

## 매개변수

**str** 암호화된 문자열입니다.

## 반환 값

일반 텍스트 암호를 반환합니다.

## 비고

이 함수는 워크플로우, 웹 애플리케이션, 보고서 또는 게재에서 호출할 수 없습니다. JSSP 또는 SOAP 호출 구현에서 호출할 수 있습니다. 예:

```javascript
          function nms_extAccount_LogonToRemoteInstance(remoteInstanceUrl, login, encryptedPassword) {
          var cnx = null, sessionService = null;
          try
              {
                  var cnx = new HttpSoapConnection(remoteInstanceUrl + '/nl/jsp/soaprouter.jsp', 'utf-8', 0);
                  sessionService = new SoapService(cnx, 'xtk:session');
                  sessionService.addMethod("Logon", "xtk:session#Logon",
                      ["token", "string", "login", "string", "password", "string", "parameters", "NLElement"],
                      ["sessionToken", "string", "sessionInfo", "NLElement", "securityToken", "string"]);
                  return sessionService.Logon("", login, decryptPassword(encryptedPassword), <parameters/>);
              }
          catch( e ) {
          logError(e);
          }
          finally {
          if( sessionService ) sessionService.dispose();
          if( cnx ) cnx.dispose();
          }
          })
      
```

## 기능

**다음 위치에서 사용 가능:**

* SOAP 메서드
