---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 15%
---
# CreateInstance

> 경고: 이 함수는 온-프레미스 환경에서 사용할 수 있습니다.

추적 인스턴스 생성에 사용됨

```text
CreateInstance ( String instanceName, String hosts, String dbId, String cryptedPwd, String lang )
```

## 매개변수

**instanceName** 만들 인스턴스의 이름

인스턴스와 연결된 **호스트** DNS 마스크

게재를 수행하는 고객의 **dbId** 데이터베이스 식별자

추적에 사용되는 **cryptedPwd** 암호화된 암호

**lang** 인스턴스 언어

## 반환 값

없음.

## 기능

**스키마:** [nms:remoteTracking](s-nms-remotetracking.md)

**정적:**

예
