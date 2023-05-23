---
title: Campaign FDA-Snowflake 배포 시작
description: Campaign FDA-Snowflake 배포 시작
feature: Overview
role: Admin, Developer, User
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# [!DNL Campaign] FDA [!DNL Snowflake] 배포{#gs-fda-snowflake}

다음 기간 [!DNL Snowflake] FDA(기본값) 배포, [!DNL Adobe Campaign] v8이 (으)로 연결되어 있습니다. [!DNL Snowflake] 을 통해 데이터에 액세스 [페더레이션 데이터 액세스](../connect/fda.md) 기능: 에 저장된 외부 데이터 및 정보에 액세스하고 이를 처리할 수 있습니다. [!DNL Snowflake] Adobe Campaign 데이터의 구조를 변경하지 않고 데이터베이스를 구축할 수 있습니다.

## 이점{#fda-benefits}

이 배포 모델에는 다음과 같은 이점이 있습니다.

* **스토리지 및 성능**
이전 데이터를 다음 위치로 이동할 수 있습니다. [!DNL Snowflake] Adobe Campaign ID 제한에 대한 종속성을 줄입니다. 또한 이 아키텍처는 PostgreSQL 저장소 및 성능 제한에 대한 종속성을 줄입니다. Campaign 데이터베이스에 저장되는 데이터가 적을수록 성능이 향상되고 유지 관리 작업이 빨라집니다.

* **데이터 모델 확장 및 데이터 관리**
다음에서 표를 만들 수 있습니다. [!DNL Snowflake] 예를 들어, 보존 기간 동안 보관된 데이터를 사용하거나 우수한 성능으로 세분화 프로세스를 실행하기 위해 Adobe Campaign에 연결합니다.

   또한 이 아키텍처는에서 데이터 관리 워크플로 기능을 사용할 수 있습니다. [!DNL Snowflake]. 집계 및 임시 테이블만 개인화 및 게재를 위해 Campaign으로 이동됩니다.


## 아키텍처{#fda-archi}

이 배포 모델을 사용하면 Adobe Campaign 사용자는 데이터를 로 확장할 수 있습니다 [!DNL Snowflake] 또한 통합된 단일 데이터 플랫폼의 이점을 활용하여 강력한 마케팅 캠페인 데이터 통찰력을 실시간으로 얻을 수 있습니다. 데이터 분석을 위한 통합되고 사용하기 쉬운 단일 플랫폼을 제공하여 사용자가 데이터에서 깊은 가치를 얻을 수 있는 기능을 제공합니다. 클라우드 데이터 플랫폼은 Adobe Campaign의 마케팅 데이터 볼륨을 지원하도록 무한히 확장되므로 관리가 필요하지 않습니다.

서버와 프로세스 간의 일반적인 통신은 다음 스키마에 따라 수행됩니다.

![](assets/fda-architecture.png)

PostgreSQL은 기본 데이터베이스이고 Snowflake은 보조 데이터베이스입니다. 데이터 모델을 확장하고 Snowflake에 데이터를 저장할 수 있습니다. 그런 다음 ETL, 세그먼테이션 및 뛰어난 성능이 포함된 대규모 데이터 세트에 대한 보고서를 실행할 수 있습니다.
