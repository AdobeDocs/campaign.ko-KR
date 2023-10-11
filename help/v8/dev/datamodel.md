---
title: Campaign 데이터 모델 시작
description: Campaign 데이터 모델을 시작하고 소스의 데이터를 활용하여 더 나은 커뮤니케이션 및 마케팅 결과를 얻으십시오.
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 5%

---

# Campaign 데이터 모델 시작{#gs-ac-datamodel}

Adobe Campaign은 사전 정의된 데이터 모델을 제공합니다. 이 섹션에서는 Adobe Campaign 데이터 모델의 기본 제공 테이블과 상호 작용에 대한 몇 가지 세부 정보를 제공합니다. Adobe Campaign은 함께 연결된 테이블이 포함된 클라우드 데이터베이스를 사용합니다.

Adobe Campaign 데이터 모델의 기본 구조는 다음과 같이 설명할 수 있습니다.

* **수신자 테이블**: 데이터 모델은 기본적으로 수신자 테이블( )인 기본 테이블에 의존합니다.**nmsRecipient**). 이 표에는 모든 마케팅 프로필이 저장됩니다. 에서 수신자 표에 대해 자세히 알아보기 [이 섹션](#ootb-profiles).

* **게재 테이블**: 이 테이블은 게재 작업당 하나의 레코드를 저장합니다. 일반적으로 게재 테이블(**NmsDelivery**). 이 표에서는 게재 작업 또는 게재 템플릿을 나타냅니다. 여기에는 target, 콘텐츠 등 게재 수행에 필요한 모든 매개 변수가 포함되어 있습니다. 게재 진행 상황을 반영하도록 각 레코드가 여러 번 업데이트됩니다

* **로그 테이블**: 이 테이블은 캠페인 실행과 관련된 모든 로그를 저장합니다.

   * 게재 로그는 모든 채널에서 수신자 또는 장치에 전송되는 모든 메시지를 의미합니다. 기본 게재 로그 표(**NmsBroadLogRcp**)에는 모든 수신자에 대한 게재 로그가 포함됩니다.
   * 다음 **nmsBroadlog** 테이블은 시스템에서 가장 큰 테이블입니다. 이 보고서는 보낸 메시지당 하나의 레코드를 저장하며, 이러한 레코드는 삽입되고 업데이트되어 게재 상태를 추적하며 기록이 삭제되면 삭제됩니다.
   * 기본 추적 로그 표(**NmsTrackingLogRcp**)는 모든 수신자에 대한 추적 로그를 저장합니다. 추적 로그는 이메일 열기 및 클릭과 같은 수신자의 반응을 나타냅니다. 각 반응은 추적 로그에 해당합니다.

  게재 로그 및 추적 로그는 Adobe Campaign에 지정되며 수정할 수 있는 특정 기간 후에 삭제됩니다. 따라서 정기적으로 로그를 내보내는 것이 좋습니다.

* **기술 표**: 운영자 및 사용자 권한을 포함하여 애플리케이션 프로세스에 사용되는 기술 데이터 수집(**xtkGroup**), 사용자 세션(**xtkSessionInfo**), 탐색기 트리의 폴더(**XtkFolder**), 워크플로우 (**xtkWorkflow**) 등의 작업을 수행합니다.

>[!NOTE]
>
>각 테이블의 설명에 액세스하려면 다음으로 이동합니다. **관리 > 구성 > 데이터 스키마**&#x200B;목록에서 리소스를 선택하고 **설명서** 탭.

Adobe Campaign으로 시작할 때 기본 데이터 모델을 평가하여 마케팅 데이터를 저장하는 데 가장 적합한 테이블을 확인해야 합니다.

에 설명된 것처럼 기본 수신자 표에는 기본 필드가 있습니다 [이 섹션](#ootb-profiles). 필요한 경우 두 가지 메커니즘을 사용하여 확장할 수 있습니다.

* [기존 테이블 확장](extend-schema.md) 새 필드 사용. 예를 들어 수신자 테이블에 새 &quot;충성도&quot; 필드를 추가할 수 있습니다.
* [새 테이블 만들기](create-schema.md)예를 들어 데이터베이스의 각 프로필에서 수행한 모든 구매를 나열하는 &quot;구매&quot; 테이블을 사용하여 수신자 테이블에 연결합니다.

![](../assets/do-not-localize/glass.png) 에서 Campaign 데이터 모델을 사용할 때의 모범 사례 살펴보기 [이 섹션](datamodel-best-practices.md).

## 기본 제공 프로필 표 {#ootb-profiles}

Adobe Campaign의 기본 제공 수신자 테이블(nmsrecipient)은 데이터 모델을 구축하기 위한 좋은 시작점을 제공합니다. 여기에는 쉽게 확장할 수 있는 많은 사전 정의된 필드와 테이블 링크가 있습니다. 이 기능은 단순한 수신자 중심의 데이터 모델에 적합하기 때문에 주로 수신자를 타겟팅하는 경우 특히 유용합니다.

표준 수신자 테이블을 사용하면 다음과 같은 이점이 있습니다.

* 구독, 시드 목록 등과 같은 주요 기능을 즉시 사용 가능
* 수신자 중심 데이터 모델을 사용하여 마케팅 데이터베이스 제공
* 신속한 구축
* 지원 및 파트너에 의한 간편한 유지 관리

수신자 테이블을 확장할 수 있지만 테이블에 있는 필드나 링크의 수는 줄일 수 없습니다.

![](../assets/do-not-localize/glass.png) 에서 기존 스키마를 확장하는 방법 알아보기 [이 섹션](extend-schema.md).

![](../assets/do-not-localize/book.png) 에서 내장된 수신자 테이블 확장의 예를 알아봅니다. [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#extending-a-table){target="_blank"}

비즈니스 또는 기능 요구 사항에 더 잘 부합하도록 다른 수신자 테이블을 사용할 수도 있습니다. 이 방법에는 제한 사항이 있으며 다음에서 설명합니다. [이 섹션](custom-recipient.md).

## Campaign 테이블 및 클라우드 데이터베이스

Campaign v8의 테이블 관리를 더 잘 이해하려면 의 컨텍스트에서 [엔터프라이즈(FFDA) 배포](../architecture/enterprise-deployment.md): Campaign과 해당 Snowflake 클라우드 데이터베이스 간에 테이블이 복제됩니다.

![](../assets/do-not-localize/glass.png) 에서 복제 전략 및 메커니즘에 대해 자세히 알아보십시오. [이 섹션](../architecture/replication.md).

**관련 항목**

![](../assets/do-not-localize/glass.png) 에서 프로필을 가져오는 방법 살펴보기 [이 섹션](../start/import.md)
![](../assets/do-not-localize/glass.png) 에서 Campaign 대상자에 대해 자세히 알아보기 [이 섹션](../start/audiences.md)
