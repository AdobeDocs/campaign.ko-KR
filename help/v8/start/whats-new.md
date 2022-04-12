---
title: Campaign v8의 새로운 기능
description: Campaign v8의 주요 기능 살펴보기
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: def9714448ef5fdde39cee070088615e8f50e522
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 100%

---

# Adobe Campaign v8의 새로운 기능은 무엇입니까? {#ac-gs-what-is-new}

Adobe Campaign v8은 인프라, 보안, 전달성 및 모니터링 기능이 상당히 개선되었습니다. Adobe Campaign은 클라우드 데이터베이스 기술인 [[!DNL Snowflake]](https://www.snowflake.com/)를 활용함으로써 그 규모와 속도를 크게 향상시켜 훨씬 더 많은 수의 고객 프로필을 관리할 수 있을 뿐만 아니라 시간 당 훨씬 더 높은 게재율과 트랜잭션 처리량을 제공합니다.

## 주요 기능{#key-capabilities}

주요 기능은 다음과 같습니다.

* **속도 및 크기 조절**. Adobe Campaign v8은 Cloud Database Manager를 활용하므로 시간당 최대 200배 더 빠른 속도로, 수 페타바이트급 용량에 더 많아진 수의 메시지(시간 당 최대 2천만 건, 트랜잭션 메시지는 최대 100만 건)를 처리하는 쿼리가 가능하며 최대 2억 건(잠재적으로는 최대 10억 건)의 활성 프로필을 관리할 수 있습니다.

* **Adobe Experience Platform 연결**. Adobe Campaign v8은 Adobe Experience Platform/RT-CDP 데이터 커넥터, 통합 고객 프로필, Journey Orchestration과의 기본 통합을 지원합니다. 이러한 투자를 통해 Adobe Campaign 고객 경험을 최적화하고 개별 실시간 고객 여정을 캠페인에 추가하는 기능과 같은 새로운 활용 사례를 확보할 수 있습니다.

* **관리 Cloud Services**. Adobe Campaign v8은 최고의 관리 Cloud Services로 제공되며, 사전 관리 감독, 신속한 경고 및 서비스 거버넌스를 제공합니다. 마케터는 더 애자일하고 확장 가능한 크로스 채널 캠페인 관리라는 이점을 누리게 됩니다.

>[!CAUTION]
>
>현재 Campaign v8은 관리 클라우드 서비스로&#x200B;**만** 사용할 수 있으며, 온-프레미스 또는 하이브리드 환경에 배포할 수 없습니다.
>
>기존 Campaign Classic v7 환경에서의 마이그레이션은 아직 불가능합니다.
>
>가지고 있는 배포 모델을 잘 모르거나 질문이 있는 경우 계정 팀에 문의해 주세요.

![](assets/home-page.png)

## 크기 조절{#scale}

Campaign v8은 타기팅에서 최종 보고에 이르기까지 프로세스의 모든 단계에서 엔드 투 엔드 크기 조절을 제공합니다.

* 처리할 수 있는 데이터 볼륨의 크기 조절(8TB까지)
* 세분화 및 타겟팅 외에도 데이터 수집 및 가져오기를 위한 쿼리 성능의 크기 조절
* 게재 준비 단위 조절(시간 ~ 분)

## 셀프서비스 관리 인터페이스{#self-service-admin}

제품 관리자는 **Campaign 컨트롤 패널**&#x200B;로 설정을 관리하고 각 Campaign v8 인스턴스 사용량을 추적할 수 있습니다.

관리자는 직관적인 사용자 인터페이스를 통해 주요 자산의 사용량을 모니터링하고, IP 주소 허용 목록, SFTP 스토리지 모니터링, 키 관리 등의 고급 작업을 수행할 수 있습니다. 이 셀프 서비스 인터페이스는 보다 유연하고 다음과 같은 이점이 있습니다.

* Adobe 고객 지원 센터에 문의하지 않고도 직접 설정을 빠르게 변경할 수 있습니다.
* 상황별로 다양한 비즈니스 요구 사항에 따라 설정을 구성할 수 있습니다
* 필요에 따라 액세스 설정을 제어하여 보안을 강화할 수 있습니다

![](assets/subdomain1.png)

![](../assets/do-not-localize/glass.png) [Campaign 컨트롤 패널에 대해 자세히 알아보기](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=ko){target=&quot;_blank&quot;}



## 간소화 및 성능 향상{#simplification-and-perf-increase}

Campaign v8은 **FFDA(Full Federated Data Access)** 개념을 도입했습니다. 이제 모든 데이터는 클라우드 데이터베이스에서 원격으로 사용할 수 있습니다.

Campaign v8은 이 새로운 아키텍처를 통해 데이터 관리를 간소화하므로 클라우드 데이터베이스에 인덱스를 작성할 필요가 없습니다. 표를 만들고 데이터를 복사하기만 하면 바로 시작할 수 있습니다.

[!DNL Snowflake]는 Campaign 클라우드 데이터베이스로 시스템 활동이 정점에 달해도 과부하가 걸리지 않는 속도와 지구력을 제공합니다.

클라우드 데이터베이스 기술은 성능 수준을 보장하기 위해 특정한 유지 관리가 필요 없습니다.

## 통합 에코시스템

Adobe Analytics, Adobe Journey Orchestration, Real-Time CDP와 같은 강력한 Adobe 솔루션 세트와 Campaign을 통합할 수 있습니다. 

또한 고객 여정 AI를 통해 예측 전송 시간 최적화 및 예측 참여 점수를 구성할 수 있고 열람률, 클릭 수 및 매출을 높일 수 있습니다.

![](../assets/do-not-localize/glass.png) [Campaign 통합에 대해 자세히 알아보기](../connect/integration.md)

