---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 35%
---
# GetNewIdsEx

시퀀스 이름이 지정된 데이터베이스에서 고유 식별자 목록을 가져옵니다.

```text
String idList = GetNewIdsEx ( Number count, String sequence )
```

## 매개변수

**count** 이 메서드가 반환해야 하는 식별자 수

**시퀀스** 증가시킬 시퀀스의 이름

## 반환 값

**idList** 쉼표로 구분된 식별자 목록

## 기능

**스키마:** [xtk:session](s-xtk-session.md)

**정적:**

예
