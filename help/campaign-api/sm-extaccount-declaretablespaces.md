---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 39%
---
# DeclareTableSpaces

Adobe Campaign 데이터베이스에서 외부 계정을 통해 액세스할 수 있는 원격 데이터베이스의 특정 테이블스페이스를 사용하는 데 필요한 옵션을 선언합니다.

```text
DeclareTableSpaces ( String extAccountId, String tableSpace, String tableSpaceIndex )
```

## 매개변수

**extAccountId** 외부 계정의 내부 이름 또는 기본 키

**tableSpace** 원격 작업 테이블에 사용할 테이블스페이스의 이름입니다.

**tableSpaceIndex** 인덱스에 사용할 테이블스페이스의 이름

## 반환 값

없음.

## 기능

**스키마:** [nms:extAccount](s-nms-extaccount.md)

**정적:**

예
