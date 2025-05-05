---
title: Campaign FDA 배포 시작
description: Campaign FDA 배포 시작
feature: Architecture, Federated Data Access, Deployment
role: Admin, Developer
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
source-git-commit: 561e4b6d2c99e98e068132c80c2bebb756b60a44
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# [!DNL Campaign] FDA 배포{#gs-fda}

Campaign FDA(기본값) 배포에서 [!DNL Adobe Campaign] v8을(를) [!DNL Snowflake]에 연결하여 [페더레이션 데이터 액세스](../connect/fda.md) 기능을 통해 데이터에 액세스할 수 있습니다. 그런 다음 Adobe Campaign 데이터의 구조를 변경하지 않고 [!DNL Snowflake] 데이터베이스에 저장된 외부 데이터 및 정보에 액세스하고 처리할 수 있습니다.

>[!NOTE]
>
>이 배포 모델에서는 요청 시에만 [!DNL Snowflake] 보조 데이터베이스를 사용할 수 있습니다. [!DNL Snowflake] (으)로 배포를 업데이트하려면 Adobe 전환 관리자에게 문의하십시오.
>

## 이점{#fda-benefits}

이 배포 모델에는 다음과 같은 이점이 있습니다.

* **저장소 및 성능**
이전 데이터를 [!DNL Snowflake] (으)로 이동한 다음 Adobe Campaign ID 제한에 대한 종속성을 줄일 수 있습니다. 또한 이 아키텍처는 PostgreSQL 저장소 및 성능 제한에 대한 종속성을 줄입니다. Campaign 데이터베이스에 저장되는 데이터가 적을수록 성능이 향상되고 유지 관리 작업이 빨라집니다.

* **데이터 모델 확장 및 데이터 관리**
[!DNL Snowflake]에서 표를 만들어 Adobe Campaign에 연결할 수 있습니다. 예를 들어 보존 기간 동안 보관된 데이터를 사용하거나 우수한 성능으로 세분화 프로세스를 실행할 수 있습니다.

  이 아키텍처를 사용하면 [!DNL Snowflake]에서 데이터 관리 워크플로 기능을 사용할 수도 있습니다. 집계 및 임시 테이블만 개인화 및 게재를 위해 Campaign으로 이동됩니다.


## 아키텍처{#fda-archi}

이 배포 모델을 통해 Adobe Campaign 사용자는 데이터를 [!DNL Snowflake] (으)로 확장하고 통합된 단일 데이터 플랫폼의 이점을 활용하여 강력한 마케팅 캠페인 데이터 통찰력을 실시간으로 얻을 수 있습니다. 데이터 분석을 위한 통합되고 사용하기 쉬운 단일 플랫폼을 제공하여 사용자가 데이터에서 깊은 가치를 얻을 수 있는 기능을 제공합니다. 클라우드 데이터 플랫폼은 Adobe Campaign의 마케팅 데이터 볼륨을 지원하도록 무한히 확장되므로 관리가 필요하지 않습니다.

서버와 프로세스 간의 일반적인 통신은 다음 스키마에 따라 수행됩니다.

![](assets/fda-architecture.png)

PostgreSQL은 기본 데이터베이스이며 Snowflake을 보조 데이터베이스로 사용할 수 있습니다. 데이터 모델을 확장하고 Snowflake에 데이터를 저장할 수 있습니다. 그런 다음 ETL, 세그먼테이션 및 뛰어난 성능이 포함된 대규모 데이터 세트에 대한 보고서를 실행할 수 있습니다.
