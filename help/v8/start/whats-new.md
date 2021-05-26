---
solution: Campaign v8
product: Adobe Campaign
title: Campaign v8의 새로운 기능
description: 주요 기능 추가
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 0%

---

# Adobe Campaign v8의 새로운 기능{#ac-gs-what-is-new}

Adobe Campaign v8은 중요한 인프라, 보안, 게재 기능 및 모니터링 개선 사항을 제공합니다. Adobe Campaign은 클라우드 데이터베이스 기술인 [[!DNL Snowflake]](https://www.snowflake.com/)을 활용하여 크기와 속도를 크게 향상하고, 더 많은 수의 고객 프로필을 관리할 수 있을 뿐만 아니라 시간당 훨씬 더 높은 전송률 및 트랜잭션을 관리할 수 있습니다.

주요 기능은 다음과 같습니다.

* **속도 및 크기 조절**. Adobe Campaign v8은 Cloud Database Manager를 활용하여 최대 200배 더 빠른 멀티페타바이트 규모의 쿼리, 시간당 최대 20M/시간 또는 1.5M/시간 트랜잭션 메시지를 통해 메시지 수를 증가시키고, 최대 200M의 활성 프로필을 관리하여 1B에 도달할 수 있습니다.

* **Adobe Experience Platform에 연결**. Adobe Campaign v8은 Adobe Experience Platform/RT-CDP를 사용하는 Data Connectors, 통합 고객 프로필 및 Journey Orchestration와의 기본 통합을 지원합니다. 이러한 투자를 통해 Adobe Campaign 고객 경험을 최적화하고 개별 실시간 고객 여정을 캠페인에 추가하는 기능과 같은 새로운 사용 사례를 잠금 해제할 수 있습니다.

* **관리 Cloud Services**. Adobe Campaign v8은 동급 최강의 관리 Cloud Services으로 제공되므로 사전 관리, 적시 경고 및 서비스 거버넌스를 제공합니다. 마케팅 담당자의 가치는 보다 민첩하고 확장 가능한 크로스 채널 캠페인 관리입니다.

>[!CAUTION]
>
>현재 Campaign v8은 **만 관리 Cloud Service으로 사용할 수 있으며, 온-프레미스 또는 하이브리드 환경에 배포할 수 없습니다.**
>
>기존 Campaign Classic v7 환경에서 마이그레이션을 아직 사용할 수 없습니다.


## 크기 조정

Campaign v8은 타깃팅에서 최종 보고에 이르기까지 프로세스의 모든 단계에서 종단 간 확장을 제공합니다.

* 처리할 수 있는 데이터 볼륨(8TB까지) 확장
* 세그먼테이션 및 타겟팅을 위한 쿼리의 성능 및 데이터 수집 및 수신
* 게재 준비 비율 조정(시간 ~ 분)

## 단순화 및 성능 향상

Campaign v8은 **전체 Federated Data Access** (FDA)의 개념을 가져옵니다.이제 모든 데이터가 클라우드 데이터베이스에서 원격입니다.

이 새로운 아키텍처를 통해 Campaign v8은 데이터 관리를 단순화합니다.클라우드 데이터베이스에 색인이 필요하지 않습니다. 표를 만들고 데이터를 복사하기만 하면 됩니다.

[!DNL Snowflake] 는 Campaign Cloud 데이터베이스이므로 빠르고 인내할 수 있습니다.시스템 활동에 과부하가 없습니다.

클라우드 데이터베이스 기술은 성능 수준을 보장하기 위해 특정 유지 관리가 필요하지 않습니다.

## 통합 에코시스템

Campaign을 다음과 같은 강력한 Adobe 솔루션 세트와 통합할 수 있습니다.Adobe Analytics, Workfront, Journey Orchestration, 실시간 CDP 등

또한 여정 AI를 통해 예측 전송 시간 최적화 및 예측 참여 점수를 구성하고 오픈율, 클릭 수 및 매출을 높일 수 있습니다.

[!DNL :bulb:] [Campaign 통합에 대해 자세히 알아보기](../connect/integration.md)

