---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 4%
---
# WorkflowTask(클래스)

워크플로 작업의 상태입니다.

⌐`WorkflowTask`은(는) 인스턴스화할 수 없는 클래스이며, 워크플로 활동에서 액세스할 수 있는 인스턴스가 하나뿐인 `task`입니다.

## 방법

| 방법 | 설명 |
| --- | --- |
| [setCompleted](m-workflowtask-setcompleted.md) | 완료된 작업에 플래그를 지정합니다. |
| [postEvent](m-workflowtask-postevent.md) | 전환을 활성화합니다. |
| [setNextProcessingDate](m-workflowtask-setnextprocessingdate.md) | 작업의 다음 처리 날짜를 강제 적용합니다. |
| [완료](m-workflowtask-donetransition.md) | 활동의 &quot;완료&quot; 전환을 반환합니다. |
| [errorTransition](m-workflowtask-errortransition.md) | 활동의 &quot;오류&quot; 전환을 반환합니다. |
| [transitionByType](m-workflowtask-transitionbytype.md) | 지정된 유형에 해당하는 전환을 반환합니다. |
| [transitionByName](m-workflowtask-transitionbyname.md) | 지정된 이름에 해당하는 전환을 반환합니다. |
| [전환](m-workflowtask-transitions.md) | 활동의 전환 목록을 반환합니다. |
| [대기](m-workflowtask-wait.md) | 신호를 기다립니다. |

## 기능

**다음 위치에서 사용 가능:**

* 워크플로
