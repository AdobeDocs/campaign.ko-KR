---
title: Campaign 및 외부 데이터베이스(FDA) 작업
description: Campaign 및 외부 데이터베이스로 작업하는 방법을 알아봅니다
feature: Federated Data Access
role: Admin
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 631c4986d24daeff870412566318adb170ce040f
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 1%

---

# FDA(Federated Data Access){#gs-fda}

FDA 커넥터(Federated Data Access)를 사용하여 Campaign을 하나 이상의 **외부 데이터베이스**&#x200B;에 연결하고 Campaign Cloud 데이터베이스 데이터에 영향을 주지 않고 저장된 정보를 처리합니다. 그런 다음 Adobe Campaign 데이터의 구조를 변경하지 않고 외부 데이터에 액세스할 수 있습니다.

>[!NOTE]
>
>* Federated Data Access에 대해 호환되는 데이터베이스는 [호환성 매트릭스](../start/compatibility-matrix.md)에 나열되어 있습니다.
>
>* [엔터프라이즈(FFDA) 배포](../../v8/architecture/enterprise-deployment.md)의 컨텍스트에서는 Campaign 로컬 데이터베이스와 Snowflake 클라우드 데이터베이스 간의 통신을 관리하는 데 특정 외부 계정을 사용할 수 있습니다. 이 외부 계정은 Adobe에서 설정되었으며 **수정해서는 안 됩니다**.
>
>* Managed Cloud Services 사용자는 [Adobe에 문의](../start/campaign-faq.md#support)하여 외부 데이터베이스를 Campaign에 연결합니다.


## 모범 사례 및 제한 사항

FDA 옵션은 사용하는 타사 데이터베이스 시스템의 제한을 따릅니다.

또한 다음 제한 사항 및 모범 사례를 숙지하십시오.

* FDA 옵션은 워크플로우에서 배치 모드로 외부 데이터베이스의 데이터를 조작하기 위해 만들어집니다. 성능 문제를 방지하기 위해 개인화, 상호 작용, 실시간 메시징 등과 같은 단일 작업의 컨텍스트에서는 FDA 모듈을 사용하지 않는 것이 좋습니다.

* Adobe Campaign과 외부 데이터베이스를 모두 사용해야 하는 작업을 가능한 한 피하십시오. 이렇게 하려면 다음 작업을 수행할 수 있습니다.

   * Adobe Campaign 데이터베이스를 외부 데이터베이스로 내보내고 결과를 Adobe Campaign으로 다시 가져오기 전에 외부 데이터베이스에서만 작업을 실행합니다.

   * 외부 Adobe Campaign 데이터베이스에서 데이터를 수집하고 작업을 로컬로 실행합니다.

  외부 데이터베이스의 데이터를 사용하여 게재에서 개인화를 수행하려면 워크플로우에서 사용할 데이터를 수집하여 임시 테이블에서 사용할 수 있도록 하십시오. 그런 다음 임시 테이블의 데이터를 사용하여 게재를 개인화합니다. 이를 수행하려면 게재 속성의 **[!UICONTROL Prepare the personalization data with a workflow]** 탭에서 사용할 수 있는 **[!UICONTROL Analysis]** 옵션을 사용하여 전용 워크플로우에서 메시지 개인화를 전처리하십시오. 게재 분석 시 이 옵션은 외부 데이터베이스에 연결된 테이블의 데이터를 포함하여 대상에 연결된 모든 데이터를 임시 테이블에 저장하는 워크플로우를 자동으로 만들고 실행합니다.

  >[!CAUTION]
  >
  >이 옵션은 개인화 단계를 실행할 때 성능을 크게 향상시킵니다.


## 워크플로우에서 외부 데이터 사용

Campaign에는 외부 데이터베이스의 데이터와 상호 작용하는 데 사용할 수 있는 몇 가지 워크플로우 활동이 포함되어 있습니다.

* **외부 데이터 필터링** - **[!UICONTROL Query]** 활동을 사용하여 외부 데이터를 추가하고 정의된 필터 구성에서 사용합니다.

* **하위 집합 만들기** - **[!UICONTROL Split]** 활동을 사용하여 하위 집합을 만드십시오. 외부 데이터를 사용하여 사용할 필터링 기준을 정의할 수 있습니다.

* **외부 데이터베이스 로드** - **[!UICONTROL Data loading (RDBMS)]** 활동에서 외부 데이터를 사용합니다.

* **정보 및 링크 추가** - **[!UICONTROL Enrichment]** 활동을 사용하여 워크플로우의 작업 테이블에 데이터를 추가하고 외부 테이블에 링크를 추가합니다. 이 컨텍스트에서는 외부 데이터베이스의 데이터를 사용할 수 있습니다.

위에 나열된 모든 워크플로우 활동에서 외부 데이터베이스에 대한 연결을 직접 정의하여 임시로 사용할 수도 있습니다. 이 경우 로컬 외부 데이터베이스에 있으며 현재 워크플로우 내에서만 사용됩니다.

>[!CAUTION]
>
>이 유형의 구성은 데이터를 수집하기 위해 임시적으로만 사용해야 합니다. 다른 모든 용도에서는 외부 계정 구성을 선호해야 합니다.

예를 들어 **[!UICONTROL Query]** 활동에서 다음과 같이 외부 데이터베이스에 대한 임시 연결을 정의할 수 있습니다.

1. 활동을 열고 **[!UICONTROL Add data...]** 클릭
1. **[!UICONTROL External data]** 옵션 선택
1. **[!UICONTROL Locally defining the data source]** 옵션 선택
1. 드롭다운 목록에서 대상 데이터베이스 엔진을 선택합니다. 서버 이름을 입력하고 인증 매개 변수를 제공합니다. 외부 데이터베이스의 이름도 지정합니다.
1. 데이터가 저장된 테이블을 선택합니다. 해당 필드에 직접 테이블 이름을 입력하거나 편집 아이콘을 눌러 데이터베이스 테이블 목록에 액세스할 수 있습니다.
1. 외부 데이터베이스 데이터와 Adobe Campaign 데이터베이스의 데이터 사이에 하나 또는 여러 조정 필드를 정의하려면 **[!UICONTROL Add]** 단추를 클릭하십시오. **[!UICONTROL Edit expression]** 및 **[!UICONTROL Remote field]**&#x200B;의 **[!UICONTROL Local field]** 아이콘을 사용하면 각 테이블의 필드 목록에 액세스할 수 있습니다.
1. 필요한 경우 필터링 조건 및 데이터 정렬 모드를 지정합니다.
1. 외부 데이터베이스에서 수집할 추가 데이터를 선택합니다. 이렇게 하려면 추가할 필드를 두 번 클릭하여 **[!UICONTROL Output columns]**&#x200B;에 표시합니다.
1. 이 구성을 확인하려면 **[!UICONTROL Finish]**&#x200B;을(를) 클릭하십시오.
