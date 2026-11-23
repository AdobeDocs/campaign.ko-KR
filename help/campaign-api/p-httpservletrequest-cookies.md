---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 13%
---
# 쿠키

쿼리의 쿠키를 반환합니다.

```text
cookies
```

## 비고

cookies 속성은 각 속성에 대해 일치하는 쿠키가 있는 개체를 반환합니다. 예:

```javascript
var cookies = request.cookies
for(var name in cookies)
{
var value = cookies[name].value
document.write(name + " : " + value + "<br>")
}
```

## 기능

**클래스의 속성:** [HttpServletRequest](c-httpservletrequest.md)

**읽기 전용:**

예

**다음 위치에서 사용 가능:**

* JSSP
* 웹 앱
