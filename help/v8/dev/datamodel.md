---
title: Campaign 데이터 모델 시작
description: Campaign 데이터 모델을 시작하고 소스의 데이터를 활용하여 커뮤니케이션과 마케팅 출력을 향상시킬 수 있습니다.
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: 507f30d16eecf5400ee88a4d29913e4cdaca9cba
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 3%

---

# Campaign 데이터 모델 시작{#gs-ac-datamodel}

Adobe Campaign은 사전 정의된 데이터 모델을 제공합니다. 이 섹션에서는 Adobe Campaign 데이터 모델의 기본 제공 테이블과 상호 작용에 대한 세부 사항을 제공합니다. Adobe Campaign은 함께 연결된 테이블이 포함된 클라우드 데이터베이스를 사용합니다.

Adobe Campaign 데이터 모델의 기본 구조는 다음과 같이 설명될 수 있습니다.

* **수신자 테이블**: 데이터 모델은 기본적으로 수신자 테이블(nmsRecipient)인 기본 테이블을 사용합니다. 이 표에는 모든 마케팅 프로필이 저장됩니다.

   ![](../assets/do-not-localize/glass.png) 수신자 테이블에 대한 자세한 내용은 [이 섹션](#ootb-profiles).

* **게재 테이블**: 데이터 모델에는 모든 마케팅 활동을 저장하도록 구성된 파트도 포함되어 있습니다. 일반적으로 게재 테이블(NmsDelivery)입니다. 이 테이블의 각 레코드는 게재 작업 또는 게재 템플릿을 나타냅니다. 여기에는 Target, 콘텐츠 등과 같은 게재를 수행하는 데 필요한 모든 매개 변수가 포함되어 있습니다.

* **로그 테이블**: 이러한 표는 캠페인 실행과 연관된 모든 로그를 저장합니다.

   게재 로그는 모든 채널에서 수신자 또는 장치로 전송되는 모든 메시지입니다. 기본 게재 로그 테이블(NmsBroadLogRcp)에는 모든 수신자에 대한 게재 로그가 포함되어 있습니다.
기본 추적 로그 테이블(NmsTrackingLogRcp)은 모든 수신자에 대한 추적 로그를 저장합니다. 추적 로그는 이메일 열기 및 클릭과 같이 수신자의 반응을 나타냅니다. 각 반응은 추적 로그에 해당합니다.
게재 로그 및 추적 로그는 Adobe Campaign에 지정되며 수정할 수 있는 특정 기간 후에 삭제됩니다. 따라서 정기적으로 로그를 내보내는 것이 좋습니다.

* **기술 테이블**: 연산자 및 사용자 권한(xtkGroup), 폴더(XtkFolder)를 포함하여 응용 프로그램 프로세스에 사용되는 기술 데이터를 수집합니다.

>[!NOTE]
>
>각 테이블의 설명에 액세스하려면 관리 > 구성 > 데이터 스키마로 이동하여 목록에서 리소스를 선택한 다음 를 클릭합니다. **설명서** 탭.

Adobe Campaign을 시작할 때 기본 데이터 모델을 평가하여 마케팅 데이터를 저장하는 데 가장 적합한 테이블을 확인해야 합니다.

에 설명된 것처럼 기본 수신자 테이블을 기본 필드와 함께 사용할 수 있습니다 [이 섹션](#ootb-profiles). 필요한 경우 두 가지 메커니즘으로 확장할 수 있습니다.

* [기존 테이블 확장](extend-schema.md) 새 필드 사용. 예를 들어 수신자 테이블에 새 &quot;충성도&quot; 필드를 추가할 수 있습니다.
* [새 표 만들기](create-schema.md)예를 들어, &quot;구매&quot; 테이블은 데이터베이스의 각 프로필에서 수행한 모든 구매를 나열한 다음 수신자 테이블에 연결합니다.

![](../assets/do-not-localize/glass.png) 에서 Campaign 데이터 모델을 사용할 때 모범 사례를 살펴보십시오 [이 섹션](datamodel-best-practices.md).

## 내장 프로필 테이블 {#ootb-profiles}

Adobe Campaign의 기본 제공 수신자 테이블(nmsrecipient)은 데이터 모델을 만드는 데 적합한 시작점을 제공합니다. 확장하기 쉬운 사전 정의된 필드와 테이블 링크가 많이 있습니다. 이 기능은 간단한 수신자 중심 데이터 모델에 적합하므로 주로 수신자를 타겟팅하는 경우에 특히 유용합니다.

표준 수신자 테이블을 사용하면 다음과 같은 이점이 있습니다.

* 구독, 시드 목록 등과 같은 주요 기능을 즉시 사용
* 수신자 중심 데이터 모델을 사용하여 마케팅 데이터베이스 제공
* 더욱 신속한 구현
* 지원 및 파트너의 간편한 유지 관리

수신자 테이블을 확장할 수는 있지만 테이블의 필드나 링크 수를 줄일 수는 없습니다.

![](../assets/do-not-localize/glass.png) 에서 기존 스키마를 확장하는 방법을 알아보십시오 [이 섹션](extend-schema.md).

![](../assets/do-not-localize/book.png) 에서 기본 제공 수신자 테이블 확장의 예를 살펴봅니다 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table){target=&quot;_blank&quot;}

또한 다른 수신자 테이블을 사용하여 비즈니스 또는 기능 요구 사항에 더 잘 맞출 수 있습니다. 이 메서드는 제한 사항과 함께 제공되며, [이 섹션](custom-recipient.md).

## Campaign 테이블 및 클라우드 데이터베이스

Campaign v8의 표 관리를 더 잘 이해하려면 [엔터프라이즈(FFDA) 배포](../architecture/enterprise-deployment.md), 표는 Campaign과 Snowflake Cloud 데이터베이스 간에 복제됩니다.

![](../assets/do-not-localize/glass.png) 의 복제 전략 및 메커니즘에 대해 자세히 알아보십시오. [이 섹션](../architecture/replication.md).

**관련 항목**

![](../assets/do-not-localize/glass.png) 에서 프로필을 가져오는 방법을 알아봅니다. [이 섹션](../start/import.md)
![](../assets/do-not-localize/glass.png) 에서 Campaign 대상에 대해 자세히 알아보십시오 [이 섹션](../start/audiences.md)
