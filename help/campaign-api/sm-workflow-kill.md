---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 3%
---
# Kill

워크플로를 무조건 중지합니다.

```text
Kill ( String workflowId )
```

## 매개변수

**workflowId** 워크플로의 식별자 또는 내부 이름입니다.

## 반환 값

없음.

## 비고

이 메서드는 워크플로우를 정상적으로 중단할 수 없는 경우에 유용합니다. 이는 특히 워크플로 또는 작업에 선호도가 있거나 이 선호도를 처리하는 wfserver 모듈이 더 이상 실행되지 않는 경우 발생할 수 있습니다. 이 경우 워크플로우는 &#39;중지 요청됨&#39; 플래그가 지정된 상태로 유지되며 종료 명령에 의해서만 중지될 수 있습니다.

## 기능

**스키마:** [xtk:workflow](s-xtk-workflow.md)

**정적:**

예
