---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 5%
---
# 앞으로

클라이언트를 통하지 않고 쿼리를 다른 페이지로 리디렉션합니다.

```text
forward (location)
```

## 매개변수

**위치** 리디렉션 URL.

## 반환 값

없음.

## 비고

앞으로 를 사용하면 쿼리를 응답의 콘텐츠를 생성할 다른 리소스로 전송하기 전에 사전 프로세스를 수행할 수 있습니다. 순방향 호출 전에 응답으로 데이터가 클라이언트에 반환되지 않아야 합니다. 그렇지 않으면 오류가 발생합니다.

## 기능

**클래스의 메서드:** [HttpServletRequest](c-httpservletrequest.md)

**다음 위치에서 사용 가능:**

* JSSP
* 웹 앱
