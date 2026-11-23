---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 2%
---
# 워크플로우

워크플로 정의

## 방법

| 방법 | 설명 |
| --- | --- |
| [정리](sm-workflow-cleanup.md) | 워크플로우 내역을 삭제합니다. |
| [DeleteResult](sm-workflow-deleteresult.md) | 하나 이상의 활동 결과를 지웁니다. |
| [실행](sm-workflow-execute.md) | 워크플로를 즉시 실행하고 완료될 때까지 기다립니다. |
| [ExecuteInstance](sm-workflow-executeinstance.md) | 워크플로를 즉시 실행하고 완료될 때까지 기다립니다. |
| [GetLogin](sm-workflow-getlogin.md) | 실행 계정에서 정보를 반환합니다. |
| [GetValidationParameters](sm-workflow-getvalidationparameters.md) | 진행 중인 워크플로 작업의 매개 변수를 반환합니다. |
| [종료](sm-workflow-kill.md) | 워크플로를 무조건 중지합니다. |
| [일시 중지](sm-workflow-pause.md) | 진행 중인 워크플로우의 실행을 일시 중단합니다. |
| [PostEvent](sm-workflow-postevent.md) | 모든 종류의 활동에서 이벤트를 생성합니다. |
| [회신](sm-workflow-reply.md) | 진행 중인 유효성 검사 유형 작업에 응답합니다. |
| [다시 시작](sm-workflow-restart.md) | 워크플로 중단 및 워크플로 시작을 함께 연결합니다. |
| [다시 시작 작업](sm-workflow-restarttask.md) | 하나 이상의 완료된 작업을 강제로 다시 시작합니다. |
| [SetLogin](sm-workflow-setlogin.md) | 실행 계정을 변경합니다. |
| [시뮬레이션](sm-workflow-simulate.md) | 시뮬레이션 모드에서 워크플로우를 시작합니다. |
| [SimulateWithParameters](sm-workflow-simulatewithparameters.md) | 시뮬레이션 모드에서 워크플로우를 시작하고 매개변수를 제공합니다. |
| [실행](sm-workflow-spawn.md) | 템플릿에서 워크플로 인스턴스를 만들고 패치를 적용한 다음 이 워크플로를 시작합니다. |
| [SpawnWithParameters](sm-workflow-spawnwithparameters.md) | 템플릿에서 워크플로 인스턴스를 만든 다음 이 인스턴스에서 [StartWithParameters](sm-workflow-startwithparameters.md) 메서드를 호출합니다. |
| [SpawnWithParametersEx](sm-workflow-spawnwithparametersex.md) | 모델에서 워크플로 인스턴스를 만들고 이 인스턴스에서 [StartWithParameters](sm-workflow-startwithparameters.md) 또는 [SimulateWithParameters](sm-workflow-simulatewithparameters.md) 메서드를 호출합니다. |
| [시작](sm-workflow-start.md) | 워크플로우 실행을 시작하거나 다시 시작합니다. |
| [StartWithParameters](sm-workflow-startwithparameters.md) | 워크플로우를 시작하고 매개변수를 제공합니다. |
| [중지](sm-workflow-stop.md) | 진행 중인 워크플로우를 중지합니다. |
| [절전 모드 해제](sm-workflow-wakeup.md) | 보류 중인 모든 작업의 사전 처리를 강제합니다. |
| [WakeupTask](sm-workflow-wakeuptask.md) | 하나 이상의 보류 중인 작업의 사전 처리를 강제합니다. |

## 제네릭 메서드

| 방법 | 설명 |
| --- | --- |
| [만들기](f-create.md) | 지정된 스키마에 해당하는 새 엔티티를 만듭니다. |
| [로드](f-load.md) | 주어진 스키마 및 키에 해당하는 엔티티를 로드하고 반환합니다. |
| [저장](m-entity-save.md) | 데이터베이스에 엔티티를 저장합니다. |
