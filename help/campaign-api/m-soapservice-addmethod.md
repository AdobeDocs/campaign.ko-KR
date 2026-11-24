---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 6%
---
# addMethod

서비스에서 함수를 선언합니다.

```text
addMethod (name, action, arguments, responses, requestNodeName, responseNodeName)
```

## 매개변수

**name** 메서드 이름입니다. JavaScript에 노출된 이름과 SOAP 메서드의 이름입니다.

**action** SOAP-Action 매개 변수.

**인수** 쌍으로 그룹화된 문자열 목록이 포함된 표 형식의 인수 선언입니다. 첫 번째 문자열은 인수의 이름이고 두 번째 문자열은 \[&quot;name1&quot;, &quot;type1&quot;, &quot;name2&quot;, &quot;type2&quot;, ...\] 유형에 해당합니다.

**응답** 쌍으로 그룹화된 문자열 목록을 포함하는 테이블 형식의 반환 값 선언: 첫 번째 문자열은 인수의 이름이고 두 번째 문자열은 \[&quot;name1&quot;, &quot;type1&quot;, &quot;name2&quot;, &quot;type2&quot;, ...\] 유형에 해당합니다.

**requestNodeName** 메서드 이름 대신 SOAP 쿼리의 XML 노드 이름을 지정하는 문자열로 구성됩니다.

**responseNodeName** 메서드 이름 대신 SOAP 응답의 XML 노드 이름을 지정한 문자열 뒤에 응답이 옵니다.

## 반환 값

없음.

## 비고

지원되는 유형은 다음과 같습니다.

* 문자열
* 부울
* 롱
* short
* 바이트
* 부동
* 중복
* 날짜
* 시간
* datetime
* NLDodocument
* 넬레멘트
* NLRawXML
* NLCollection

서비스에서 메서드가 선언되면 서비스의 메서드가 되며 해당 이름으로 메서드를 호출하여 직접 호출할 수 있습니다. 들어오는 매개 변수에 사용되는 NLRawXML 형식은 전체 XML 노드를 복사하여 인수를 바꿉니다. 반환 유형으로 사용되며 SOAP 응답의 전체 첫 번째 하위 요소를 포함합니다. 이 변수는 SOAP 응답에 하나의 하위 요소만 있음을 의미합니다. 들어오는 매개 변수에 사용된 NLCollection 유형은 인수를 대체할 모든 하위 요소를 복사합니다. 이 메서드는 들어오는 인수가 변수 매개 변수인 경우 유용합니다. 반환 값의 루트이므로 반환 유형으로 사용되며 전체 SOAP 응답을 포함합니다. 오류가 발생한 경우 예외가 발생합니다. 이 오류가 올바른 형식의 SOAP 오류인 경우 발생한 예외에는 soapFault 속성이 있으며 SOAP 오류의 XML 노드가 포함됩니다. 예:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
session.addMethod("GetOption", "xtk:session#GetOption",
  ["token", "string", "name", "string"],
  ["value", "string", "type", "byte"])
try
{
var result  = session.GetOption("admin/", "NmsBroadcast_DefaultProvider")
var value   = result[0]
var type    = result[1]
logInfo("Value = " + value)
logInfo("Type = " + type)
}
catch( e )
{
  if( e.soapFault )
    logInfo("A SOAP Fault occured : " + e.soapFault.toXMLString());
  else
    logInfo("An error occured : " + e);
}
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
