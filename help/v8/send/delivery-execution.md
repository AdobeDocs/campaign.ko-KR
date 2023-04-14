---
title: 트랜잭션 메시지 게재 실행
description: 트랜잭션 메시지 게재 실행 및 모니터링에 대해 자세히 알아보십시오
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 1%

---


# 게재 실행 {#delivery-execution}

데이터 보강이 완료되고 게재 템플릿이 이벤트에 연결되면 게재가 실행 인스턴스에서 전송됩니다.

>[!NOTE]
>
>트랜잭션 메시지는 다른 게재보다 우선 순위가 지정됩니다.

모든 게재는 **[!UICONTROL Administration > Production > Message Center > Default > Deliveries]** 폴더를 입력합니다.

기본적으로 배달 월별로 하위 폴더로 정렬됩니다. 이 정렬은 메시지 템플릿 속성에서 변경할 수 있습니다.

## 트랜잭션 메시지 모니터링 {#transactional-message-monitoring}

트랜잭션 메시지를 모니터링하려면 [게재 로그](send.md).

실행 인스턴스에서 전송된 트랜잭션 게재는 기술 워크플로우( )를 통해 제어 인스턴스로 다시 동기화됩니다.**[!UICONTROL Message Center execution instance]**)을 클릭하여 제품에서 사용할 수 있습니다.

>[!NOTE]
>
>게재 주마다 이벤트 생성 날짜가 아니라 최신 이벤트 업데이트를 기반으로 이벤트를 누적합니다. 따라서 제어 인스턴스에서 트랜잭션 메시지 게재 로그를 추출할 때 로그가 업데이트되면(예를 들어, 이벤트에 대해 인바운드 바운스가 수신될 때) 각 게재 로그 ID와 연관된 게재 ID가 시간에 따라 변경될 수 있습니다.

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->
