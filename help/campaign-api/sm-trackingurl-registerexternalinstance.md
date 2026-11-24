---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 37%
---
# RegisterExternalInstance

데이터베이스 식별자를 설정하여 리디렉션 서버에 대한 릴레이 서버의 추적 인스턴스를 승인합니다.

```text
RegisterExternalInstance ( String login, String instanceName, String dbId, Boolean saveParams )
```

## 매개변수

**로그인** 릴레이 서버 액세스 로그인

**instanceName** 승인할 인스턴스의 이름

게재를 수행하는 고객의 **dbId** 데이터베이스 식별자

성공하면 **saveParams** 저장 옵션

## 반환 값

없음.

## 기능

**스키마:** [nms:trackingUrl](s-nms-trackingurl.md)

**정적:**

예
