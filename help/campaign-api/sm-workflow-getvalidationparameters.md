---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 2%
---
# GetValidationParameters

진행 중인 워크플로 작업의 매개 변수를 반환합니다.

```text
XML content = GetValidationParameters ( String workflowId, String taskIdentifier )
```

## 매개변수

**workflowId** 워크플로의 식별자 또는 내부 이름입니다.

**taskIdentifier** 승인 유형 작업의 식별자(@taskIdentifier 필드)입니다.

## 반환 값

**content** 매개 변수가 포함된 XML 문서입니다.

## 비고

반환된 문서에는 유효성 검사와 관련된 모든 정보, 응답한 사용자 및 응답한 사용자가 포함됩니다.

* title, creationDate, processingDate, timeout, status, abortReason 및 completionDate 속성은 유효성 검사 작업의 속성에 해당합니다.
* isAssignee: 현재 연산자가 이 작업에 할당된 그룹에 있습니다.
* hasResponded: 현재 연산자가 이미 응답했습니다.
* canReply: 현재 연산자가 응답할 수 있습니다(아직 아무도 응답하지 않거나 여러 개의 응답이 승인되었습니다.).

## 기능

**스키마:** [xtk:workflow](s-xtk-workflow.md)

**정적:**

예
