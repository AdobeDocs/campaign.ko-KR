---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 35%
---
# 실행

작업을 동기식으로 실행합니다(이 모드에서는 진행 정보 및 취소를 사용할 수 없음).

```text
String id = job.Execute ( String methodName ) const
```

## 매개변수

엔터티에 대해 호출할 메서드의 **methodName** 이름

## 반환 값

**id** 생성된 작업의 식별자(데이터베이스에서 만든 경우 작업이 실패한 경우에도 반환됨)

## 기능

**스키마:** [xtk:job](s-xtk-job.md)

**정적:**

아니요

**Const:**

예

**키만:**

아니요
