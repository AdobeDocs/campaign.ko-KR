---
solution: Campaign Classic
product: campaign
title: Campaign 데이터 모델 시작
description: Campaign 데이터 모델 시작
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896,b1319b34-ee07-48ed-9ab1-e2d12d3d99f8
translation-type: tm+mt
source-git-commit: e509feb4624b26e33d43f2a1d926b563ab52a8c4
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 4%

---

# Campaign 데이터 모델 시작{#gs-ac-datamodel}

Adobe Campaign은 사전 정의된 데이터 모델을 제공합니다. 이 섹션에서는 Adobe Campaign 데이터 모델의 내장 테이블과 상호 작용에 대한 세부 사항을 제공합니다. Adobe Campaign은 서로 연결된 테이블이 포함된 클라우드 데이터베이스를 사용합니다.

Adobe Campaign 데이터 모델의 기본 구조는 다음과 같습니다.

* **수신자 테이블**:데이터 모델은 기본적으로 받는 사람 테이블(nmsRecipient)인 기본 테이블을 사용합니다. 이 표를 사용하면 모든 마케팅 프로필을 저장할 수 있습니다.

   : 전구:수신자 테이블에 대한 자세한 내용은 [이 섹션](#ootb-profiles)을 참조하십시오.

* **배달 표**:또한 데이터 모델에는 모든 마케팅 활동을 저장하도록 하는 부분도 포함됩니다. 일반적으로 배달 테이블(NmsDelivery)입니다. 이 테이블의 각 레코드는 배달 작업 또는 배달 템플릿을 나타냅니다. 여기에는 타겟, 컨텐츠 등과 같은 전달 수행에 필요한 모든 매개 변수가 포함되어 있습니다.

* **로그 테이블**:이러한 표는 캠페인 실행과 연관된 모든 로그를 저장합니다.

   배달 로그는 모든 채널에서 받는 사람 또는 장치로 보낸 모든 메시지입니다. 기본 배달 로그 테이블(NmsBroadLog)에는 모든 받는 사람의 배달 로그가 포함되어 있습니다.
주 추적 로그 테이블(NmsTrackingLog)은 모든 받는 사람의 추적 로그를 저장합니다. 추적 로그는 이메일 공개와 클릭 수와 같은 수신자의 반응을 나타냅니다. 각 반응은 추적 로그에 해당합니다.
배달 로그 및 추적 로그는 Adobe Campaign에 지정된 특정 기간 후에 삭제되며 수정할 수 있습니다. 따라서 정기적으로 로그를 내보내는 것이 좋습니다.

* **기술 표**:연산자 및 사용자 권한(NmsGroup), 폴더(XtkFolder)를 포함하여 응용 프로그램 프로세스에 사용되는 기술 데이터를 수집합니다.

>[!NOTE]
>
>각 테이블의 설명에 액세스하려면 관리 > 구성 > 데이터 스키마로 이동하고 목록에서 리소스를 선택하고 **설명서** 탭을 클릭합니다.

Adobe Campaign을 시작할 때 기본 데이터 모델을 평가하여 마케팅 데이터를 저장하는 데 가장 적합한 표를 확인해야 합니다.

[이 섹션](#ootb-profiles)에 설명된 것과 같이 기본 수신자 테이블과 기본 필드를 함께 사용할 수 있습니다. 필요한 경우 두 가지 메커니즘으로 확장할 수 있습니다.

* [새 필드를 사용하여 기존 ](extend-schema.md) 테이블을 확장합니다. 예를 들어 새 &quot;충성도&quot; 필드를 수신자 테이블에 추가할 수 있습니다.
* [데이터베이스의 각 프로필에서 구입한 모든 구매를 나열하는 &quot;구매](create-schema.md)&quot; 테이블 등 새 테이블을 만들고 이 테이블을 수신자 테이블에 연결합니다.

: 전구:[이 섹션](datamodel-best-practices.md)에서 캠페인 데이터 모델을 사용하여 작업할 때 우수 사례를 알아봅니다.

## 내장 프로필 테이블 {#ootb-profiles}

Adobe Campaign의 기본 제공 수신자 테이블(nmsrecipient)은 데이터 모델을 구축하기 위한 좋은 시작점을 제공합니다. 미리 정의된 필드 및 표 링크를 많이 제공하므로 쉽게 확장할 수 있습니다. 이 기능은 간단한 수신자 중심의 데이터 모델에 적합하므로 주로 수신자를 대상으로 하는 경우에 특히 유용합니다.

표준 수신자 테이블을 사용하면 다음과 같은 이점이 있습니다.

* 구독, 시드 목록 등의 주요 기능을 즉시 사용
* 수신자 중심의 데이터 모델을 사용하여 마케팅 데이터베이스 제공
* 더욱 빨라진 구현
* 지원 및 파트너를 통한 간편한 유지 관리

받는 사람 테이블을 확장할 수는 있지만 테이블의 필드나 링크 수를 줄일 수는 없습니다.

: 전구:[이 섹션](extend-schema.md)에서 기존 스키마를 확장하는 방법을 알아봅니다.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table)에서 내장 받는 사람 표 확장의 예를 알아봅니다.

또한 다른 수신자 테이블을 사용하여 비즈니스 또는 기능 요구 사항에 보다 잘 맞출 수 있습니다. 이 메서드는 제한 사항이 있으며 [이 섹션](custom-recipient.md)에 설명되어 있습니다.

## 캠페인 테이블 및 클라우드 데이터베이스

Campaign v8의 표 관리를 더 잘 이해하려면 Campaign과 해당 Snowflake Cloud 데이터베이스 간에 테이블이 복제됩니다.

: 전구:복제 전략 및 메커니즘에 대한 자세한 내용은 [이 섹션](../config/replication.md)을 참조하십시오.

**관련 항목**

: 전구:[이 섹션](../start/import.md)에서 프로필을 가져오는 방법을 알아봅니다.
: 전구:[이 섹션](../start/audiences.md)에서 캠페인 대상에 대해 자세히 알아보십시오.
