---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '29'
ht-degree: 17%
---
# setContentType

응답의 문서 유형을 변경합니다.

```text
setContentType (name)
```

## 매개변수

문서의 **이름** MIME 형식입니다.

## 반환 값

없음.

## 비고

예:

```javascript
      response.setContentType("text/html;charset=ISO-8859-1")
```

## 기능

**클래스의 메서드:** [HttpServletResponse](c-httpservletresponse.md)

**다음 위치에서 사용 가능:**

* JSSP
* 웹 앱
