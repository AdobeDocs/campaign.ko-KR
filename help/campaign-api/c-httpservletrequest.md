---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%
---
# HttpServletRequest (클래스)

서블릿에 전달되는 클라이언트의 쿼리를 나타냅니다.

`request`을(를) 통해 액세스할 수 있는 이 주소의 인스턴스는 하나만 있습니다. 변수를 채우는 방법에 따라 페이지를 순서대로 표시합니다.

## 방법

| 방법 | 설명 |
| --- | --- |
| [getHeader](m-httpservletrequest-getheader.md) | 쿼리 헤더에 정의된 속성을 반환합니다. |
| [getParameter](m-httpservletrequest-getparameter.md) | 쿼리 매개 변수의 값을 반환합니다. |
| [getRemoteAddr](m-httpservletrequest-getremoteaddr.md) | 요청을 보낸 클라이언트 또는 마지막 프록시의 IP 주소를 반환합니다. |
| [getUTF8Parameter](m-httpservletrequest-getutf8parameter.md) | 쿼리 매개변수의 값(UTF-8로 코딩됨)을 반환합니다. |
| [getBodyAsString](m-httpservletrequest-getbodyasstring.md) | 쿼리 코딩을 사용하여 쿼리의 본문을 문자열 형태로 반환합니다. |
| [앞으로](m-httpservletrequest-forward.md) | 클라이언트를 통하지 않고 쿼리를 다른 페이지로 리디렉션합니다. |

## 속성

| 속성 | 설명 |
| --- | --- |
| [매개 변수](p-httpservletrequest-parameters.md) | 쿼리 매개 변수를 반환합니다. |
| [쿠키](p-httpservletrequest-cookies.md) | 쿼리의 쿠키를 반환합니다. |
| [requestURI](p-httpservletrequest-requesturi.md) | 쿼리의 URL을 반환합니다. |
| [queryString](p-httpservletrequest-querystring.md) | 매개 변수와 일치하는 쿼리 URL 부분을 반환합니다. |
| [구성표](p-httpservletrequest-scheme.md) | 사용된 프로토콜 이름(HTTP, HTTPS 등)을 반환합니다. 을 클릭하여 이 페이지에 액세스합니다. |
| [serverName](p-httpservletrequest-servername.md) | 쿼리 서버의 이름을 반환합니다. |
| [serverPort](p-httpservletrequest-serverport.md) | 서버 연결에 사용되는 포트 번호를 반환합니다. |
| [serverURL](p-httpservletrequest-serverurl.md) | 서버에 액세스하기 위한 URL을 반환합니다. |
| [servletPath](p-httpservletrequest-servletpath.md) | 서블릿과 일치하는 쿼리 URL 섹션을 반환합니다. |
| [contextPath](p-httpservletrequest-contextpath.md) | 컨텍스트와 일치하는 쿼리 URL 섹션을 반환합니다. |
| [경로 정보](p-httpservletrequest-pathinfo.md) | 쿼리 URL의 추가 정보를 반환합니다. |
| [메서드](p-httpservletrequest-method.md) | 이 쿼리를 호출하는 데 사용된 HTTP 메서드(GET, HEAD, POST 등)가 포함된 문자 문자열을 반환합니다. |

## 기능

**다음 위치에서 사용 가능:**

* JSSP
* 웹 앱
