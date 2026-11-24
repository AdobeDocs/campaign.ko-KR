---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 33%
---
# GetTrackinginfo

원격 리디렉션 서버에서 게재 액션 관련 정보를 다운로드할 수 있습니다.

```text
XML document = GetTrackingInfo ( String instance, String dbId, String deliveryId )
```

## 매개변수

**인스턴스** 인스턴스 이름

게재를 수행하는 고객의 **dbId** 데이터베이스 식별자

**deliveryId** 배달 ID.

## 반환 값

**문서** 이 게재에 대한 추적 정보가 포함된 문서

## 기능

**스키마:** [nms:remoteTracking](s-nms-remotetracking.md)

**정적:**

예
