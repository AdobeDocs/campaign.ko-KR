---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 2%
---
# GetLogin

실행 계정에서 정보를 반환합니다.

```text
[ Number id, String login, String cs ] = GetLogin ( String workflowId )
```

## 매개변수

**workflowId** 워크플로의 식별자 또는 내부 이름입니다.

## 반환 값

**id** 연산자의 식별자 또는 이 워크플로와 연결된 연산자가 없는 경우 0입니다.

**login** 이 워크플로와 연결된 연산자가 없는 경우 연산자의 로그인 또는 빈 문자열입니다.

**cs** 연산자의 설명 문자열 또는 이 워크플로와 연결된 연산자가 없는 경우 빈 문자열입니다.

## 비고

워크플로우와 연결된 실행 계정을 사용하면 워크플로우를 시작한 연산자가 아닌 특정 연산자에게 실행 권한을 강제할 수 있습니다. 워크플로우가 복제되면 실행 계정이 전파되지 않습니다.

## 기능

**스키마:** [xtk:workflow](s-xtk-workflow.md)

**정적:**

예
