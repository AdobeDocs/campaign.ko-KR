---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 15%
---
# GetTrackingLogs

리디렉션 및 웹 추적 서비스에서 생성된 추적 로그를 수집할 수 있습니다.

```text
[ String pointer, Number logCount, String logs, Date srvDate ] = GetTrackingLogs ( String instance, String dbId, Number version, String pointer, Number logCount )
```

## 매개변수

**인스턴스** 짧은 식별자

게재를 수행하는 고객의 **dbId** 데이터베이스 식별자

**버전** 추적 로그 버전

로그를 검색해야 하는 로그의 **포인터** 식별자(serialized int64).

**logCount** 요청에 대해 검색할 로그 수(0은 기본값을 의미함), 응답이 반환한 로그 수입니다.

## 반환 값

로그를 검색해야 하는 로그의 **포인터** 식별자(serialized int64).

**logCount** 요청에 대해 검색할 로그 수(0은 기본값을 의미함), 응답이 반환한 로그 수입니다.

**로그**&#x200B;개 로그 검색됨

로그 검색 요청 시 서버의 **srvDate** GMT 시간

## 기능

**스키마:** [nms:remoteTracking](s-nms-remotetracking.md)

**정적:**

예
