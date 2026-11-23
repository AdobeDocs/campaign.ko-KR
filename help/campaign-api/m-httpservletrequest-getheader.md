---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '30'
ht-degree: 16%
---
# getHeader

쿼리 헤더에 정의된 속성을 반환합니다.

```text
getHeader (name)
```

## 매개변수

**이름** 헤더의 특성 이름입니다.

## 반환 값

없음.

## 비고

예:

```javascript
Host: <%= request.getHeader("host") %>
```

## 기능

**클래스의 메서드:** [HttpServletRequest](c-httpservletrequest.md)

**다음 위치에서 사용 가능:**

* JSSP
* 웹 앱
