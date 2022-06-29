---
title: Campaign 상호 작용 아키텍처 이해
description: Campaign Interaction Architecture 기본 사항
feature: Interaction
role: Data Engineer
level: Beginner
exl-id: 7a710960-7e41-4462-bd5e-18e874aa46f8
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '1314'
ht-degree: 0%

---

# Campaign 상호 작용 환경 및 아키텍처 이해

## 환경 {#environments}

오퍼를 관리할 때 사용되는 각 타깃팅 차원에 대해 두 개의 환경이 있습니다.

* A **디자인** 오퍼 관리자가 오퍼를 생성 및 분류하고, 편집하고, 오퍼를 사용할 수 있도록 승인 프로세스를 시작하는 문제가 되는 환경입니다. 각 카테고리에 대한 규칙, 오퍼를 표시할 수 있는 오퍼 공간, 오퍼의 자격을 정의하는 데 사용되는 사전 정의된 필터 도 이 환경에서 정의됩니다.

   카테고리를 온라인 환경에서 수동으로 게시할 수도 있습니다.

   오퍼 승인 프로세스는 자세히 설명되어 있습니다 [이 섹션](interaction-offer.md#approve-offers).

* A **live** 디자인 환경에서 승인된 오퍼와 디자인 환경에 구성된 다양한 오퍼 공간, 필터, 카테고리 및 규칙을 모두 찾을 수 있는 환경입니다. 오퍼 엔진에 대한 호출 동안 엔진은 항상 라이브 환경의 오퍼를 사용합니다.

오퍼는 승인 프로세스 중에 선택한 오퍼 공간에만 배포됩니다. 따라서 오퍼는 라이브될 수 있지만 라이브이기도 한 오퍼 공간에서 사용할 수 없습니다.

## 인바운드 및 아웃바운드 상호 작용 {#interaction-types}

Adobe Campaign 상호 작용 모듈은 두 가지 유형의 상호 작용을 제안합니다.

* **인바운드** 연락처가 시작한 상호 작용 [자세히 알아보기](interaction-present-offers.md)
* **아웃바운드** 캠페인 게재 관리자가 시작한 상호 작용. [자세히 알아보기](interaction-send-offers.md)

이러한 두 가지 유형의 상호 작용은 다음 중 하나에서 수행할 수 있습니다 **단일 모드** (오퍼가 단일 연락처에 대해 계산됨) 또는 **일괄 처리 모드** (연락처 세트에 대해 오퍼가 계산됩니다.) 일반적으로 인바운드 상호 작용은 단일 모드에서 수행되고 아웃바운드 상호 작용은 배치 모드에서 수행됩니다. 하지만, [트랜잭션 메시지](../send/transactional.md) 예를 들어 아웃바운드 상호 작용이 단일 모드로 수행되는 경우입니다.

오퍼를 제공할 수 있거나 제공해야 하는 즉시(수행된 구성에 따라) 오퍼 엔진이 중간 역할을 합니다. 연락처에 대해 수신한 데이터와 애플리케이션에 지정된 대로 적용할 수 있는 다양한 규칙을 결합하여 사용할 수 있는 연락 중 가장 적합한 오퍼를 자동으로 계산합니다.

![](assets/architecture_interaction2.png)

## 분산 아키텍처

확장을 지원하고 인바운드 채널에 24/7 서비스를 제공하려면 **상호 작용** 모듈은 분산 아키텍처에서 구현됩니다. 이 유형의 아키텍처는 이미 과 함께 사용됩니다 [메시지 센터](../architecture/architecture.md#transac-msg-archi) 및 는 여러 인스턴스로 구성됩니다.

* 아웃바운드 채널에 전용되며 마케팅 및 환경 디자인 베이스를 포함하는 하나 또는 여러 개의 제어 인스턴스
* 인바운드 채널을 위한 하나 또는 여러 개의 실행 인스턴스

![](assets/interaction_powerbooster_schema.png)

제어 인스턴스는 인바운드 채널 전용이며 카탈로그의 온라인 버전을 포함합니다. 모든 실행 인스턴스는 독립적이며 하나의 연락처 세그먼트(예: 국가당 하나의 실행 인스턴스)에 전용으로 사용됩니다. 오퍼 엔진 호출은 실행(실행 인스턴스당 하나의 특정 URL)에서 직접 수행해야 합니다. 인스턴스 간의 동기화가 자동으로 수행되지 않으므로 동일한 연락처의 상호 작용은 동일한 인스턴스를 통해 전송해야 합니다.

### 동기화 {#synchronization}

오퍼 동기화는 패키지를 통해 수행됩니다. 실행 인스턴스에서 모든 카탈로그 개체의 접두사가 외부 계정 이름으로 붙습니다. 즉, 동일한 실행 인스턴스에서 여러 제어 인스턴스(예: 개발 및 프로덕션 인스턴스)를 지원할 수 있습니다.

>[!CAUTION]
>
>짧고 명시적 내부 이름을 사용합니다.

오퍼가 자동으로 배포되고 실행 및 제어 인스턴스에 게시됩니다.

디자인 환경에서 삭제된 오퍼는 모든 온라인 인스턴스에서 비활성화됩니다. 사용되지 않는 proposition 및 오퍼는 제거 기간(각 인스턴스의 배포 어시스턴트에 지정됨) 및 슬라이딩 기간(들어오는 프로포지션의 유형화 규칙에 지정됨) 이후 모든 인스턴스에서 자동으로 삭제됩니다.

![](assets/interaction_powerbooster_schema2.png)

제안 동기화를 위한 각 환경 및 외부 계정에 대해 워크플로우가 만들어집니다. 동기화 빈도는 각 환경 및 외부 계정에 대해 조정할 수 있습니다.

다음 동기화 메커니즘은 알고 있어야 합니다.

* 익명 환경에서 식별된 환경으로 폴백 기능을 사용하는 경우 이러한 두 환경은 동일한 실행 인스턴스에 있어야 합니다.
* 여러 실행 인스턴스 간의 동기화가 실시간으로 수행되지 않습니다. 동일한 연락처의 상호 작용은 동일한 인스턴스로 전송해야 합니다. 컨트롤 인스턴스는 아웃바운드 채널 전용(실시간 없음)이어야 합니다.
* 마케팅 데이터베이스는 자동으로 동기화되지 않습니다. 가중치 및 자격 규칙에 사용된 마케팅 데이터는 실행 인스턴스에 복제되어야 합니다. 이 프로세스는 표준이 아니므로 통합 기간 동안 개발해야 합니다.
* 제안 동기화는 FDA 연결에서만 수행됩니다.
* 동일한 인스턴스에서 상호 작용 및 메시지 센터를 사용하는 경우 두 경우 모두 FDA 프로토콜을 통해 동기화가 발생합니다.

### 패키지 구성 {#packages-configuration}

에 직접 연결된 모든 스키마 확장 **상호 작용** (오퍼, 제안, 수신자 등) 를 실행 인스턴스에 배포해야 합니다.

다음 **상호 작용** 패키지는 모든 인스턴스(제어 및 실행)에 설치됩니다. 두 개의 추가 패키지를 사용할 수 있습니다. 각 실행 인스턴스에 대해 하나의 패키지, 각 실행 인스턴스에 대해 하나의 패키지

>[!NOTE]
>
>패키지를 설치할 때 **장기간** 의 유형 필드 **nms:제안** 제안 ID와 같은 표는 다음과 같습니다. **int64** 유형 필드. 이 유형의 데이터는 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/schema-structure.html?lang=en#mapping-the-types-of-adobe-campaign-dbms-data){target=&quot;_blank&quot;}.

데이터 보존 기간은 를 통해 각 인스턴스에 구성됩니다 **[!UICONTROL Data purge]** 창을 클릭합니다(배포 마법사의 창). 실행 인스턴스에서 이 기간은 유형화 규칙(슬라이딩 기간) 및 자격 규칙을 계산하는 데 필요한 이전 깊이에 해당해야 합니다.

컨트롤 인스턴스에서 다음을 수행합니다.

1. 실행 인스턴스당 하나의 외부 계정을 만듭니다.

   ![](assets/interaction_powerbooster1.png)

   * 레이블을 완성하고 짧고 명시적 내부 이름을 추가합니다.
   * **[!UICONTROL Execution instance]**&#x200B;을(를) 선택합니다.
   * **[!UICONTROL Enabled]** 옵션을 선택합니다.
   * 실행 인스턴스에 대한 연결 매개 변수를 완료합니다.
   * 모든 실행 인스턴스는 ID에 연결되어 있어야 합니다. 이 ID는 **[!UICONTROL Initialize connection]** 버튼을 클릭합니다.
   * 사용된 응용 프로그램 유형을 확인합니다. **[!UICONTROL Message Center]**, **[!UICONTROL Interaction]**&#x200B;또는 둘 다 사용할 수 있습니다.
   * 사용된 FDA 계정을 입력합니다. 연산자는 실행 인스턴스에 만들어야 하며 해당 인스턴스의 데이터베이스에 대해 다음 읽기 및 쓰기 권한이 있어야 합니다.

      ```
      grant SELECT ON nmspropositionrcp, nmsoffer, nmsofferspace, xtkoption, xtkfolder TO user;
      grant DELETE, INSERT, UPDATE ON nmspropositionrcp TO user;
      ```
   >[!NOTE]
   >
   >실행 인스턴스에서 컨트롤 인스턴스의 IP 주소를 인증해야 합니다.

1. 환경 구성:

   ![](assets/interaction_powerbooster2.png)

   * 실행 인스턴스 목록을 추가합니다.
   * 각 항목에 대해 동기화 기간 및 필터 기준(예: 국가별)을 지정합니다.

      >[!NOTE]
      >
      >오류가 발생하면 동기화 워크플로우 및 오퍼 알림을 참조할 수 있습니다. 애플리케이션의 기술 워크플로우에서 찾을 수 있습니다.

최적화를 위해 마케팅 데이터베이스의 일부만 실행 인스턴스에 복제되는 경우, 환경에 연결된 제한된 스키마를 지정하여 사용자가 실행 인스턴스에서 사용할 수 있는 데이터만 사용할 수 있도록 할 수 있습니다. 실행 인스턴스에서 사용할 수 없는 데이터를 사용하여 오퍼를 만들 수 있습니다. 이렇게 하려면 아웃바운드 채널(**[!UICONTROL Taken into account if]** 필드)만 로드하는 것입니다.

![](assets/ita_filtering.png)

### 유지 관리 옵션 {#maintenance-options}

다음은 제어 인스턴스에서 사용할 수 있는 유지 관리 옵션 목록입니다.

>[!CAUTION]
>
>이러한 옵션은 특정 유지 관리 사례에만 사용해야 합니다.

* **`NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>`**: 지정된 인스턴스에서 환경이 동기화된 마지막 날짜입니다.
* **`NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>`**: 주어진 스키마에서 다른 인스턴스로 프로모션하는 마지막 날짜입니다.
* **`NmsInteraction_MapWorkflowId`**: 생성된 모든 동기화 워크플로우 목록이 포함된 옵션입니다.

실행 인스턴스에서 다음 옵션을 사용할 수 있습니다.

**NmsExecutionInstanceId**: 인스턴스 ID가 포함된 옵션.

### 패키지 설치 {#packages-installation}

이전에 인스턴스에 **상호 작용** 패키지, 마이그레이션이 필요하지 않습니다. 기본적으로, 제안 테이블은 패키지가 설치된 후 64비트 이내입니다.

>[!CAUTION]
>
>인스턴스에 있는 기존 proposition의 볼륨에 따라 이 작업은 시간이 걸릴 수 있습니다.

* 인스턴스에 제안이 거의 없거나 없는 경우 제안 테이블을 수동으로 수정할 필요가 없습니다. 수정 작업은 패키지가 설치될 때 수행됩니다.
* 인스턴스에 많은 제안 사항이 있는 경우 제어 패키지를 설치하고 실행하기 전에 제안 테이블의 구조를 변경하는 것이 좋습니다. 활동이 적은 기간 동안 쿼리를 실행하는 것이 좋습니다.

>[!NOTE]
>
>제안 테이블에서 특정 구성을 수행한 경우 그에 따라 쿼리를 조정합니다.


다음 두 가지 방법을 사용할 수 있습니다.

**작업 테이블** (권장)

```
CREATE TABLE NmsPropositionRcp_tmp AS SELECT * FROM nmspropositionrcp WHERE 0=1;
ALTER TABLE nmspropositionrcp_tmp
  ALTER COLUMN ipropositionid TYPE bigint,
  ALTER COLUMN iinteractionid TYPE bigint;
INSERT INTO nmspropositionrcp_tmp SELECT * FROM nmspropositionrcp;
DROP TABLE nmspropositionrcp;
CREATE INDEX proposition_id ON NmsPropositionRcp (ipropositionid);
CREATE INDEX nmspropositionrcp_deliveryid ON NmsPropositionRcp (ideliveryid);
CREATE INDEX nmspropositionrcp_lastmodified ON NmsPropositionRcp (tslastmodified);
CREATE INDEX nmspropositionrcp_offerid ON NmsPropositionRcp (iofferid);
CREATE INDEX nmspropositionrcp_offerspaceid ON NmsPropositionRcp (iofferspaceid);
CREATE INDEX nmspropositionrcp_recipientidid ON NmsPropositionRcp (irecipientid);
ALTER TABLE nmspropositionrcp_tmp RENAME TO nmspropositionrcp;
```

**표 변경**

```
ALTER TABLE nmspropositionrcp
  ALTER COLUMN ipropositionid TYPE bigint,
  ALTER COLUMN iinteractionid TYPE bigint;
```
