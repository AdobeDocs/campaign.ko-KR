---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 3%
---
# SetLogin

실행 계정을 변경합니다.

```text
SetLogin ( String workflowId, String login )
```

## 매개변수

**workflowId** 워크플로의 식별자 또는 내부 이름입니다.

**login** 이 워크플로와 연결된 연산자가 없는 경우 연산자의 로그인 또는 빈 문자열입니다.

## 반환 값

없음.

## 비고

워크플로우와 연결된 실행 계정을 사용하면 워크플로우를 시작한 연산자가 아닌 특정 연산자에게 실행 권한을 강제할 수 있습니다. 워크플로우가 복제되면 실행 계정이 전파되지 않습니다.

## 기능

**스키마:** [xtk:workflow](s-xtk-workflow.md)

**정적:**

예
