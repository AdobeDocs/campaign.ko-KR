---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 11%
---
# queryString

매개 변수와 일치하는 쿼리 URL 부분을 반환합니다.

```text
queryString
```

## 비고

예: 다음 URL의 queryString:

```javascript
      http://adobe.com/nms/test.jst?id=1234&param=dummy#aFragment
```

는 다음 문자열을 반환합니다.

```javascript
id=1234&param=dummy
```

## 기능

**클래스의 속성:** [HttpServletRequest](c-httpservletrequest.md)

**읽기 전용:**

예

**다음 위치에서 사용 가능:**

* JSSP
* 웹 앱
