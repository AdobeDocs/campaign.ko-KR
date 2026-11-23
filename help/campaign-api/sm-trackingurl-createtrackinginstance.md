---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 20%
---
# CreateTrackinginstance

리디렉션 서버에서 추적 인스턴스 만들기 또는 구성

```text
CreateTrackingInstance ( String internalPwd, String serverUrl, String secureServerUrl, String serverUrlList, String instanceName, String cryptedPassword, String host )
```

## 매개변수

**internalPwd** 내부 암호

추적 서버의 **serverUrl** 외부 URL

추적 서버의 **secureServerUrl** 외부 보안 URL

추적 서버의 **serverUrlList** 내부 URL

**instanceName** 만들 인스턴스의 이름

**cryptedPassword** 암호화된 암호

인스턴스와 연결된 **호스트** DNS 마스크

## 반환 값

없음.

## 기능

**스키마:** [nms:trackingUrl](s-nms-trackingurl.md)

**정적:**

예
