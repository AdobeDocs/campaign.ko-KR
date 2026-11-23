---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 1%
---
# PostEvent

모든 종류의 활동에서 이벤트를 생성합니다.

```text
PostEvent ( String workflowId, String activity, String transition, XML parameters, Boolean complete )
```

## 매개변수

**workflowId** 워크플로의 식별자 또는 내부 이름입니다.

**활동** 이벤트가 시작되는 활동의 이름

**transition** 활성화할 전환의 이름입니다. 이 이름이 비어 있으면 첫 번째 유효한 전환 시 이벤트가 발행됩니다(만료 유형 이벤트는 무시됨).

**매개 변수** XML 요소 형식의 이벤트 매개 변수입니다. 요소의 이름은 변수여야 합니다. 변수를 전달하지 않으려면 빈 요소 &lt;variables/> 또는 빈 문자열 &quot;&quot;을 사용할 수 있습니다.

**완료** 지정된 활동의 보류 중인 모든 작업이 완료되었습니다.

## 반환 값

없음.

## 비고

* 명령은 비동기 모드에서 실행되고 메서드 반환 후 즉각적인 영향을 주지 않습니다.
* 이 메서드가 호출될 때 대상 워크플로우를 시작해야 합니다. 시작되지 않으면 해당 로그 파일에 오류가 기록됩니다.
* 메서드가 호출될 때 대상 워크플로우가 일시 중지되면 워크플로우가 다시 시작될 때까지 명령이 대기열에 남아 있습니다.
* 활동에는 제한이 없습니다. 작업이 진행 중이거나 완료되었을 필요는 없습니다.

## 기능

**스키마:** [xtk:workflow](s-xtk-workflow.md)

**정적:**

예
