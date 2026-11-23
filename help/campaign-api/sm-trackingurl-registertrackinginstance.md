---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 28%
---
# 등록 추적 인스턴스

데이터베이스 식별자를 설정하여 리디렉션 서버에 대한 추적 인스턴스를 승인합니다.

```text
RegisterTrackingInstance ( String serverUrl, String secureServerUrl, String serverUrlList, String instanceName, String cryptedPassword )
```

## 매개변수

추적 서버의 **serverUrl** 외부 URL

추적 서버의 **secureServerUrl** 외부 보안 URL

추적 서버의 **serverUrlList** 내부 URL

**instanceName** 승인할 인스턴스의 이름

**cryptedPassword** 암호화된 암호

## 반환 값

없음.

## 기능

**스키마:** [nms:trackingUrl](s-nms-trackingurl.md)

**정적:**

예
