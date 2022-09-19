---
title: Campaign 및 외부 데이터베이스 작업(FDA)
description: Campaign 및 외부 데이터베이스로 작업하는 방법 알아보기
feature: Federated Data Access
role: Data Engineer
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: bb03c804c1c65322d275d0a2ca1db0bfe974636d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# FDA(Federated Data Access){#gs-fda}

FDA 커넥터(Federated Data Access)를 사용하여 Campaign을 하나 이상 연결합니다 **외부 데이터베이스** 및 Campaign Cloud 데이터베이스 데이터에 영향을 주지 않고 데이터베이스에 저장된 정보를 처리합니다. 그런 다음 Adobe Campaign 데이터의 구조를 변경하지 않고 외부 데이터에 액세스할 수 있습니다.

![](../assets/do-not-localize/speech.png)   관리 Cloud Services 사용자로, [연락처 Adobe](../start/campaign-faq.md#support) campaign을 사용하여 Experience Cloud 트리거를 구현하려면 다음을 수행하십시오.


>[!NOTE]
>
>* Federated Data Access에 대한 호환 데이터베이스는 [호환성 매트릭스](../start/compatibility-matrix.md).
>
>* 의 컨텍스트에서 [엔터프라이즈(FFDA) 배포](../architecture/enterprise-deployment.md)인 경우 Campaign 로컬 데이터베이스와 Snowflake 클라우드 데이터베이스 간의 통신을 관리하는 데 특정 외부 계정을 사용할 수 있습니다. 이 외부 계정은 Adobe 및 **필수가 아니어야 합니다.** 수정됩니다.
>



## 모범 사례 및 제한 사항

FDA 옵션은 사용하는 타사 데이터베이스 시스템의 제한을 따릅니다.

또한 다음 제한 사항과 모범 사례를 확인하십시오.

* FDA 옵션은 워크플로우에서 일괄 처리 모드에서 외부 데이터베이스의 데이터를 조작하기 위해 수행됩니다. 성능 문제를 방지하려면 다음과 같이 단일 작업 컨텍스트에서 FDA 모듈을 사용하지 않는 것이 좋습니다. 개인화, 상호 작용, 실시간 메시징 등.

* Adobe Campaign과 외부 데이터베이스를 모두 가능한 한 사용해야 하는 작업을 방지합니다. 이렇게 하려면 다음을 수행할 수 있습니다.

   * Adobe Campaign 데이터베이스를 외부 데이터베이스로 내보내고 외부 데이터베이스에서만 작업을 수행한 후에 결과를 Adobe Campaign으로 다시 가져옵니다.

   * 외부 Adobe Campaign 데이터베이스에서 데이터를 수집하고 작업을 로컬로 실행합니다.
   외부 데이터베이스의 데이터를 사용하여 게재에서 개인화를 수행하려는 경우 워크플로우에서 사용할 데이터를 수집하여 임시 테이블에서 사용할 수 있도록 하십시오. 그런 다음 임시 테이블의 데이터를 사용하여 게재를 개인화합니다. 이를 수행하려면 다음을 사용하여 전용 워크플로우에서 메시지 개인화를 사전 처리합니다 **[!UICONTROL Prepare the personalization data with a workflow]** 선택 사항, 사용 가능한 **[!UICONTROL Analysis]** 전달 속성의 탭입니다. 게재 분석 중에 이 옵션은 외부 데이터베이스에 연결된 테이블의 데이터를 포함하여 대상에 연결된 모든 데이터를 임시 테이블에 저장하는 워크플로우를 자동으로 만들고 실행합니다.

   >[!CAUTION]
   >
   >이 옵션은 개인화 단계를 실행할 때 성능을 크게 향상시킵니다.


## 워크플로우에서 외부 데이터 사용

Campaign에는 외부 데이터베이스의 데이터와 상호 작용하는 데 사용할 수 있는 몇 가지 워크플로우 활동이 포함되어 있습니다.

* **외부 데이터 필터** - 다음 사용 **[!UICONTROL Query]** 활동은 외부 데이터를 추가하고 정의된 필터 구성에서 사용합니다.

* **하위 집합 만들기** - 다음 사용 **[!UICONTROL Split]** 활동 을 클릭하여 하위 세트를 만듭니다. 외부 데이터를 사용하여 사용할 필터링 기준을 정의할 수 있습니다.

* **외부 데이터베이스 로드** - 에서 외부 데이터 사용 **[!UICONTROL Data loading (RDBMS)]** 활동.

* **정보 및 링크 추가** - 다음 사용 **[!UICONTROL Enrichment]** 활동을 통해 워크플로우의 작업 테이블에 추가 데이터를 추가하고 외부 테이블에 연결합니다. 이 컨텍스트에서는 외부 데이터베이스의 데이터를 사용할 수 있습니다.

임시 사용을 위해 위에 나열된 모든 워크플로우 활동에서 외부 데이터베이스에 대한 연결을 직접 정의할 수도 있습니다. 이 경우 로컬 외부 데이터베이스에 있으며 현재 워크플로우 내에서만 사용됩니다.

>[!CAUTION]
>
>이 유형의 구성은 데이터를 수집하는 데 임시로 사용해야 합니다. 다른 용도에는 외부 계정 구성을 사용하는 것이 좋습니다.

예를 들어, **[!UICONTROL Query]** 다음과 같이 외부 데이터베이스에 대한 임시 연결을 정의할 수 있습니다.

1. 활동을 열고 을(를) 클릭합니다. **[!UICONTROL Add data...]**
1. 을(를) 선택합니다 **[!UICONTROL External data]** 옵션
1. 을(를) 선택합니다 **[!UICONTROL Locally defining the data source]** 옵션
1. 드롭다운 목록에서 대상 데이터베이스 엔진을 선택합니다. 서버 이름을 입력하고 인증 매개 변수를 제공합니다. 외부 데이터베이스의 이름도 지정합니다.
1. 데이터가 저장되는 테이블을 선택합니다. 해당 필드에 직접 테이블 이름을 입력하거나 편집 아이콘을 눌러 데이터베이스 테이블 목록에 액세스할 수 있습니다.
1. 을(를) 클릭합니다. **[!UICONTROL Add]** 외부 데이터베이스 데이터와 Adobe Campaign 데이터베이스의 데이터 간에 하나 또는 여러 개의 조정 필드를 정의하는 단추입니다. 다음 **[!UICONTROL Edit expression]** 아이콘 **[!UICONTROL Remote field]** 및 **[!UICONTROL Local field]** 각 테이블의 필드 목록에 액세스할 수 있습니다.
1. 필요한 경우 필터링 조건 및 데이터 정렬 모드를 지정합니다.
1. 외부 데이터베이스에서 수집할 추가 데이터를 선택합니다. 이렇게 하려면 추가할 필드를 두 번 클릭하여 을 **[!UICONTROL Output columns]**.
1. 클릭 **[!UICONTROL Finish]** 이 구성을 확인합니다.
