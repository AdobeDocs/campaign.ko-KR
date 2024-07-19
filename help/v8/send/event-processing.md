---
title: 이벤트 수집 및 처리
description: Campaign 트랜잭션 메시지에서 이벤트를 수집하고 처리하는 방법 알아보기
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: c1deb0a1-aeba-4813-b674-a6a164b98b02
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 1%

---

# 이벤트 처리 {#event-processing}

트랜잭션 메시지의 컨텍스트에서는 외부 정보 시스템에서 이벤트를 생성하여 **[!UICONTROL PushEvent]** 및 **[!UICONTROL PushEvents]** 메서드를 통해 Adobe Campaign으로 전송됩니다. 이러한 메서드는 [이 섹션](event-description.md)에 설명되어 있습니다.

이 이벤트에는 다음과 같이 이벤트에 연결된 데이터가 포함되어 있습니다.

* [type](transactional.md#create-event-types): 주문 확인, 웹 사이트에 계정 만들기 등,
* 이메일 주소 또는 전화번호,
* 게재하기 전에 트랜잭션 메시지를 보강하고 개인화하는 기타 모든 정보: 고객 연락처 정보, 메시지 언어, 이메일 포맷 등.

이벤트 데이터의 예:

![](assets/mc-event-request.png)

트랜잭션 메시지 이벤트를 처리하기 위해 실행 인스턴스에 다음 단계가 적용됩니다.

1. [이벤트 컬렉션](#event-collection)
1. [메시지 템플릿으로 이벤트 전송](#routing-towards-a-template)
1. 개인화 데이터를 통한 이벤트 보강
1. [게재 실행](delivery-execution.md)
1. 연결된 게재가 실패한 [이벤트 재활용](#event-recycling)(Adobe Campaign 워크플로를 통해)

모든 단계가 달성되면 타겟팅된 각 수신자는 개인화된 메시지를 받게 됩니다.

## 이벤트 수집 {#event-collection}

정보 시스템에 의해 생성된 이벤트는 다음 두 가지 모드를 사용하여 수집할 수 있습니다.

* SOAP 메서드를 호출하면 Adobe Campaign에서 이벤트를 푸시할 수 있습니다. PushEvent 메서드를 사용하면 한 번에 하나의 이벤트를 보낼 수 있고 PushEvents 메서드를 사용하면 한 번에 여러 이벤트를 보낼 수 있습니다. [자세히 알아보기](event-description.md).

* 워크플로우를 만들면 [Federated Data Access](../connect/fda.md) 모듈을 사용하여 파일을 가져오거나 SQL 게이트웨이를 통해 이벤트를 복구할 수 있습니다.

이벤트가 수집되면 [메시지 템플릿](transactional-template.md)에 연결되기를 기다리는 동안 실행 인스턴스의 실시간 큐와 일괄 처리 큐 사이의 기술 워크플로우로 이벤트가 분류됩니다.

![](assets/mc-event-queues.png)

>[!NOTE]
>
>실행 인스턴스에서는 액세스 권한 문제가 발생할 수 있으므로 **[!UICONTROL Real time events]** 또는 **[!UICONTROL Batch events]** 폴더를 보기로 설정하지 않아야 합니다. 폴더를 보기로 설정하는 방법에 대한 자세한 내용은 [이 섹션](../audiences/folders-and-views.md#turn-a-folder-to-a-view)을 참조하세요.

## 템플릿에 이벤트 전송 {#event-to-template}

메시지 템플릿이 실행 인스턴스에 게시되면 두 개의 템플릿이 자동으로 생성됩니다. 하나는 실시간 이벤트에 연결되고 다른 하나는 일괄 처리 이벤트에 연결됩니다.

라우팅 단계는 다음 기준에 따라 이벤트를 적절한 메시지 템플릿에 연결하는 단계로 구성됩니다.

* 이벤트 자체의 속성에 지정된 이벤트 유형:

  ![](assets/event-type-sample.png)

* 메시지 템플릿 속성에 지정된 이벤트 유형:

  ![](assets/event-type-select.png)

기본적으로 라우팅은 다음 정보를 사용합니다.

* 이벤트 유형
* 사용할 채널(기본값: 이메일)
* 게시 날짜를 기반으로 한 가장 최근 게재 템플릿

## 이벤트 상태 확인 {#event-statuses}

처리된 모든 이벤트는 **이벤트 기록** 폴더 또는 탐색기에서 단일 보기로 그룹화됩니다. 이벤트 유형이나 **상태**&#x200B;별로 분류할 수 있습니다.

가능한 상태는 다음과 같습니다.

* **보류 중**

   * 보류 중인 이벤트는 방금 수집되었으며 아직 처리되지 않은 이벤트일 수 있습니다. **[!UICONTROL Number of errors]** 열에 값 0이 표시됩니다. 이메일 템플릿이 아직 연결되지 않았습니다.
   * 보류 중인 이벤트는 처리된 이벤트일 수도 있지만 확인 오류가 있는 이벤트입니다. **[!UICONTROL Number of errors]** 열에 0이 아닌 값이 표시됩니다. 이 이벤트가 다시 처리되는 시기를 확인하려면 **[!UICONTROL Process requested on]** 열을 참조하십시오.

* **게재 보류 중**
이벤트가 처리되고 게재 템플릿이 연결됩니다. 이메일이 게재 보류 중이며 클래식 게재 프로세스가 적용됩니다. 자세한 내용은 게재를 열 수 있습니다.
* **전송됨**, **무시됨** 및 **게재 오류**
이러한 게재 상태는 **updateEventsStatus** 워크플로우를 통해 복구됩니다. 자세한 내용은 관련 게재를 열 수 있습니다.
* **이벤트가 포함되지 않음**
트랜잭션 메시지 라우팅 단계 실패. 예를 들어 Adobe Campaign에서 이벤트의 템플릿 역할을 하는 이메일을 찾지 못했습니다.
* **이벤트 만료됨**
최대 전송 시도 횟수에 도달했습니다. 이 이벤트는 null로 간주됩니다.

## 이벤트 재활용 {#event-recycling}

특정 채널에서 메시지를 배달하지 못하는 경우 Adobe Campaign에서 다른 채널을 사용하여 메시지를 다시 보낼 수 있습니다. 예를 들어 SMS 채널에서의 게재가 실패할 경우 이메일 채널을 사용하여 메시지가 다시 전송됩니다.

이렇게 하려면 **게재 오류** 상태로 모든 이벤트를 다시 만들고 다른 채널을 할당하는 워크플로우를 구성해야 합니다.

>[!CAUTION]
>
>이 단계는 워크플로우를 통해서만 수행할 수 있으므로 전문가 사용자용으로 예약되어 있습니다. 자세한 내용은 Adobe 계정 담당자에게 문의하십시오.
