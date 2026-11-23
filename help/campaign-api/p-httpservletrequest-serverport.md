---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%
---
# serverPort

서버 연결에 사용되는 포트 번호를 반환합니다.

```text
serverPort
```

## 비고

예: 다음 URL의 serverPort:

```javascript
http://adobe.com:8080/nms/test.jst
```

는 다음 문자열을 반환합니다.

```javascript
8080
```

다음 URL의 serverPort:

```javascript
http://adobe.com/nms/test.jst
```

는 다음 문자열을 반환합니다.

```javascript
80
```

## 기능

**클래스의 속성:** [HttpServletRequest](c-httpservletrequest.md)

**읽기 전용:**

예

**다음 위치에서 사용 가능:**

* JSSP
* 웹 앱
