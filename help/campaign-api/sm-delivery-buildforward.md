---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 19%
---
# BuildForward

HTML 페이지를 작성합니다.

```text
[ String content, Number responseCode ] = BuildForward ( String crypted, XML parameters )
```

## 매개변수

**암호화됨** 메시지 및 게재 부분 식별자의 해독 가능한 암호화

**매개 변수** URL 매개 변수

## 반환 값

**콘텐츠** 페이지 콘텐츠

오류 발생 시 **responseCode** HTTP 응답

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

예
