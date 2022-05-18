---
title: Campaign FDA-Snowflake 배포 시작
description: Campaign FDA-Snowflake 배포 시작
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# [!DNL Campaign] FDA [!DNL Snowflake] 배포{#gs-fda-snowflake}

다음 [!DNL Snowflake] FDA(기본) 배포, [!DNL Adobe Campaign] v8이 [!DNL Snowflake] 를 통해 데이터에 액세스 [페더레이션 데이터 액세스](../connect/fda.md) 기능: 에 저장된 외부 데이터 및 정보에 액세스하여 처리할 수 있습니다 [!DNL Snowflake] Adobe Campaign 데이터 구조를 변경하지 않고 데이터베이스를 만듭니다.

## 이점{#fda-benefits}

이 배포 모델에는 다음과 같은 이점이 있습니다.

* **스토리지 및 성능**
이전 데이터를 [!DNL Snowflake] 그런 다음 Adobe Campaign ID 제한에 대한 종속성을 줄입니다. 또한 이 아키텍처는 PostgreSQL 스토리지 및 성능 제한에 대한 의존도를 줄입니다. Campaign 데이터베이스에 데이터가 적게 저장되므로 성능이 향상되고 유지 관리 작업이 더 빨리 수행됩니다.

* **데이터 모델 확장 및 데이터 관리**
에서 표를 만들 수 있습니다 [!DNL Snowflake] Adobe Campaign에 연결합니다. 예를 들어 보존 기간 동안 아카이브된 데이터를 사용하거나 성능이 뛰어난 세분화 프로세스를 실행할 수 있습니다.

   또한 이 아키텍처에서는 [!DNL Snowflake]. 개인화 및 게재 목적을 위해 집계 및 임시 테이블만 Campaign으로 이동합니다.


## 아키텍처{#fda-archi}

이 배포 모델을 사용하면 Adobe Campaign 사용자는 자신의 데이터를 [!DNL Snowflake] 통합된 단일 데이터 플랫폼의 이점을 활용하여 강력한 마케팅 캠페인 데이터 통찰력을 실시간으로 얻을 수 있습니다. 통합 및 사용하기 쉬운 단일 플랫폼을 제공하여 사용자가 데이터를 최대한 활용할 수 있도록 합니다. 클라우드 데이터 플랫폼은 Adobe Campaign의 모든 마케팅 데이터를 지원하기 위해 무한 확장되므로 관리 작업이 필요하지 않습니다.

서버와 프로세스 간의 일반 통신은 다음 스키마에 따라 수행됩니다.

![](assets/fda-architecture.png)

PostgreSQL은 기본 데이터베이스이고 Snowflake은 보조 데이터베이스입니다. 데이터 모델을 확장하고 데이터를 Snowflake에 저장할 수 있습니다. 그 후에 성능이 우수한 대용량 데이터 세트에 대해 ETL, 세그멘테이션 및 보고서를 실행할 수 있습니다.
