---
title: 이벤트 수집 및 처리
description: Campaign 트랜잭션 메시징이 이벤트를 수집하고 처리하는 방법을 알아봅니다
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 1%

---


# 이벤트 처리 {#event-processing}

트랜잭션 메시지 컨텍스트에서 이벤트는 외부 정보 시스템에 의해 생성되고, 를 통해 Adobe Campaign으로 전송됩니다 **[!UICONTROL PushEvent]** 및 **[!UICONTROL PushEvents]** 메서드를 사용합니다. 이러한 메서드는 [이 섹션](event-description.md).

이 이벤트에는 다음과 같이 이벤트에 연결된 데이터가 포함되어 있습니다.

* it [유형](transactional.md#create-event-types): 주문 확인, 웹 사이트에서의 계정 생성,
* 이메일 주소나 전화번호
* 게재 전에 트랜잭션 메시지를 보강하고 개인화하기 위한 다른 모든 정보: 고객 연락처 정보, 메시지 언어, 이메일 형식 등

이벤트 데이터의 예:

![](assets/mc-event-request.png)

트랜잭션 메시지 이벤트를 처리하려면 실행 인스턴스에 다음 단계가 적용됩니다.

1. [이벤트 컬렉션](#event-collection)
1. [메시지 템플릿으로 이벤트 전송](#routing-towards-a-template)
1. 개인화 데이터를 통한 이벤트 강화
1. [게재 실행](delivery-execution.md)
1. [이벤트 재활용](#event-recycling) (Adobe Campaign 워크플로우를 통해) 연결된 게재에 실패한 사용자

모든 단계가 완료되면 타깃팅된 각 수신자는 개인화된 메시지를 수신합니다.

## 이벤트 수집 {#event-collection}

정보 시스템에서 생성된 이벤트는 두 가지 모드를 사용하여 수집할 수 있다.

* SOAP 메서드 호출을 통해 Adobe Campaign에서 이벤트를 푸시할 수 있습니다. pushEvent 메서드를 사용하면 한 번에 하나의 이벤트를 전송할 수 있습니다. PushEvents 메서드를 사용하면 여러 이벤트를 한 번에 전송할 수 있습니다. [자세히 알아보기](event-description.md)

* 워크플로우를 만들면 파일을 가져오거나 SQL 게이트웨이를 통해 [페더레이션 데이터 액세스](../connect/fda.md) 모듈.

이벤트가 수집되면 페이지에 연결되기를 기다리는 동안 실행 인스턴스의 실시간 및 배치 큐 간의 기술 워크플로우별로 이벤트가 분류됩니다 [메시지 템플릿](transactional-template.md).

![](assets/mc-event-queues.png)

>[!NOTE]
>
>실행 인스턴스에서 **[!UICONTROL Real time events]** 또는 **[!UICONTROL Batch events]** 올바른 액세스 문제가 발생할 수 있으므로 폴더를 보기로 설정하면 안 됩니다. 폴더를 보기로 설정하는 방법에 대한 자세한 내용은 [이 섹션](../audiences/folders-and-views.md#turn-a-folder-to-a-view).

## 템플릿에 이벤트 전송 {#event-to-template}

메시지 템플릿이 실행 인스턴스에 게시되면 두 개의 템플릿이 자동으로 생성됩니다. 하나는 실시간 이벤트에 연결되고 다른 하나는 배치 이벤트에 연결됩니다.

라우팅 단계는 다음을 기반으로 이벤트를 적절한 메시지 템플릿에 연결하는 데 구성됩니다.

* 이벤트 자체의 속성에 지정된 이벤트 유형:

   ![](assets/event-type-sample.png)

* 메시지 템플릿 속성에 지정된 이벤트 유형:

   ![](assets/event-type-select.png)

기본적으로 공정순서는 다음 정보에 의존합니다.

* 이벤트 유형
* 사용할 채널(기본적으로: email)
* 게시 날짜를 기반으로 하는 가장 최근 게재 템플릿

## 이벤트 상태 확인 {#event-statuses}

처리된 모든 이벤트는 **이벤트 내역** 폴더 또는 탐색기 를 클릭합니다. 이벤트 유형별로 또는 **상태**.

가능한 상태는 다음과 같습니다.

* **보류 중**

   * 보류 중인 이벤트는 방금 수집되었으며 아직 처리되지 않은 이벤트입니다. 다음 **[!UICONTROL Number of errors]** 열에는 값 0이 표시됩니다. 전자 메일 템플릿이 아직 연결되어 있지 않습니다.
   * 보류 중인 이벤트는 처리된 이벤트일 수도 있지만 확인이 잘못된 이벤트입니다. 다음 **[!UICONTROL Number of errors]** 열에는 0이 아닌 값이 표시됩니다. 이 이벤트가 다시 처리되는 시기를 확인하려면 **[!UICONTROL Process requested on]** 열.

* **게재 보류 중**
이벤트가 처리되고 게재 템플릿이 연결됩니다. 이메일이 게재 대기 중이며 클래식 게재 프로세스가 적용됩니다. 자세한 내용은 게재를 열 수 있습니다.
* **전송**, **무시됨** 및 **게재 오류**
이러한 게재 상태는 
**updateEventsStatus** 워크플로우. 자세한 내용은 관련 게재를 열 수 있습니다.
* **이벤트가 포함되지 않음**
트랜잭션 메시지 라우팅 단계가 실패했습니다. 예를 들어 Adobe Campaign이 이벤트의 템플릿으로 작동하는 이메일을 찾지 못했습니다.
* **이벤트 만료**
최대 전송 시도 수에 도달했습니다. 이벤트는 null로 간주됩니다.

## 이벤트 재활용 {#event-recycling}

특정 채널에 메시지 게재가 실패하면 Adobe Campaign은 다른 채널을 사용하여 메시지를 다시 전송할 수 있습니다. 예를 들어 SMS 채널을 통한 게재가 실패하면 이메일 채널을 사용하여 메시지가 다시 전송됩니다.

이렇게 하려면 을(를) 사용하여 모든 이벤트를 다시 만드는 워크플로우를 구성해야 합니다. **게재 오류** 상태를 확인하고 다른 채널을 지정합니다.

>[!CAUTION]
>
>이 단계는 워크플로우를 사용해야만 수행할 수 있으며, 따라서 전문가 사용자를 위해 예약되어 있습니다. 자세한 내용은 Adobe 계정 담당자에게 문의하십시오.



