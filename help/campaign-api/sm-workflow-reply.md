---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 5%
---
# 회신

진행 중인 유효성 검사 유형 작업에 응답합니다.

```text
Reply ( String workflowId, String taskIdentifier, String response, String choice )
```

## 매개변수

**workflowId** 워크플로의 식별자 또는 내부 이름입니다.

**taskIdentifier** 승인 유형 작업의 식별자(@taskIdentifier 필드)입니다.

**응답** 응답과 연결된 댓글입니다.

**선택** 응답을 선택합니다. 이 선택은 활성화하려는 전환 이름과 일치해야 합니다.

## 반환 값

없음.

## 비고

현재 연산자는 작업에 할당된 그룹에 있어야 합니다.

## 기능

**스키마:** [xtk:workflow](s-xtk-workflow.md)

**정적:**

예
