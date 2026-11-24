---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '33'
ht-degree: 15%
---
# 매개 변수

쿼리 매개 변수를 반환합니다.

```text
parameters
```

## 비고

parameters 속성은 쿼리의 매개 변수와 일치하는 속성이 있는 개체를 반환합니다. 예:

```javascript
var parameters = request.parameters
for(var name in parameters)
{
var value = parameters[name]
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
