---
product: Adobe Campaign
title: Campaign v8의 새로운 기능
description: 주요 기능 자세히 알아보기
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 52%

---

# Adobe Campaign v8의 새로운 기능 {#ac-gs-what-is-new}

Adobe Campaign v8은 인프라, 보안, 제공 및 모니터링 기능이 상당히 개선되었습니다. Adobe Campaign은 클라우드 데이터베이스 기술인 [[!DNL Snowflake]](https://www.snowflake.com/)을 활용하여 크기와 속도를 크게 향상하고, 더 많은 수의 고객 프로필을 관리할 수 있을 뿐만 아니라 시간당 훨씬 더 높은 전송률 및 트랜잭션을 관리할 수 있습니다.

주요 기능은 다음과 같습니다.

* **속도 및 크기 조절**. Adobe Campaign v8은 Cloud Database Manager를 활용하여 최대 200배 더 빠른 멀티페타바이트 규모의 쿼리, 시간당 최대 20M/시간 또는 1M/시간 트랜잭션 메시지를 통해 메시지 수를 증가시키는 쿼리, 최대 2억 개의 활성 프로필을 관리할 수 있으며, 최대 2억 개의 활성 프로필을 관리할 수 있습니다.

* **Adobe Experience Platform 연결**. Adobe Campaign v8은 Adobe Experience Platform/RT-CDP 데이터 커넥터, 통합 고객 프로필, Journey Orchestration과의 기본 통합을 지원합니다. 이러한 투자를 통해 Adobe Campaign 고객 경험을 최적화하고 개별 실시간 고객 여정을 캠페인에 추가하는 기능과 같은 새로운 활용 사례를 확보할 수 있습니다.

* **관리 Cloud Services**. Adobe Campaign v8은 최고의 관리 Cloud Services로 제공되며, 사전 관리 감독, 신속한 경고 및 서비스 거버넌스를 제공합니다. 마케팅 담당자의 가치는 보다 민첩하고 확장 가능한 크로스 채널 캠페인 관리입니다.

>[!CAUTION]
>
>현재 Campaign v8은 **만 관리 Cloud Service으로 사용할 수 있으며, 온-프레미스 또는 하이브리드 환경에 배포할 수 없습니다.**
>
>기존 Campaign Classic v7 환경에서 마이그레이션을 아직 사용할 수 없습니다.
>
>배포 모델을 잘 모르거나 질문이 있는 경우 계정 팀에 문의하십시오.


## 크기 조절

Campaign v8은 타깃팅에서 최종 보고에 이르기까지 프로세스의 모든 단계에서 종단 간 확장을 제공합니다.

* 처리할 수 있는 데이터 볼륨의 크기 조절(8TB까지)
* 세분화 및 타겟팅 외에도 데이터 수집 및 가져오기를 위한 쿼리 성능의 크기 조절
* 게재 준비 비율 조정(시간 ~ 분)

## 간소화 및 성능 향상

Campaign v8은 **FFDA**(Full Federated Data Access) 개념을 도입했습니다. 이제 모든 데이터는 멀리 떨어진 클라우드 데이터베이스에 있습니다.

이 새로운 아키텍처를 통해 Campaign v8은 데이터 관리를 단순화합니다.클라우드 데이터베이스에 색인이 필요하지 않습니다. 표를 만들고 데이터를 복사하기만 하면 바로 시작할 수 있습니다.

[!DNL Snowflake] 는 Campaign Cloud 데이터베이스이므로 빠르고 인내할 수 있습니다.시스템 활동에 과부하가 없습니다.

클라우드 데이터베이스 기술은 성능 수준을 보장하기 위해 특정한 유지 관리가 필요 없습니다.

## 통합 에코시스템

Adobe Analytics, 워크플로우, Journey Orchestration, 실시간 CDP와 같은 강력한 Adobe 솔루션 세트와 Campaign을 통합할 수 있습니다. 

또한 고객 여정 AI를 통해 예측 전송 시간 최적화 및 예측 참여 점수를 구성할 수 있고 열람률, 클릭 수 및 매출을 높일 수 있습니다.

[!DNL :bulb:] [Campaign 통합에 대해 자세히 알아보기](../connect/integration.md)

