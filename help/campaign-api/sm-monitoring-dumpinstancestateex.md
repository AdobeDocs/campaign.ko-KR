---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 19%
---
# 덤프 인스턴스 상태 표현식

서버 프로세스의 상태 반환

```text
XML monitoring = DumpInstanceStateEx ( String mask, Boolean includeDead, Boolean noDatabaseCheck, Number criticalLevel )
```

## 매개변수

인스턴스가 고려할 **마스크** 마스크

**includeDead** 중단된 프로세스 목록 추가

**noDatabaseCheck** 데이터베이스 개체에서 경고를 확인하지 않습니다.

**criticalLevel** 반환된 경고의 심각도를 필터링합니다.

## 반환 값

**모니터링**

## 기능

**스키마:** [nl:monitoring](s-nl-monitoring.md)

**정적:**

예
