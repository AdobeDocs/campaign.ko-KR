---
title: Campaign 및 SFDC 작업
description: Campaign 및 Salesforce.com 을 사용하여 작업하는 방법을 알아봅니다.
feature: Salesforce Integration
role: Admin, User
level: Beginner, Intermediate
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
source-git-commit: 41e39e046ec77de8b5e657ba76645898ff1cd2d7
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 3%

---

# Campaign 및 SFDC 작업{#crm-sfdc}

Campaign v8을 **Salesforce.com**&#x200B;에 연결하도록 Campaign CRM 커넥터를 구성하는 방법을 알아봅니다.

구성이 완료되면 전용 워크플로우 활동을 통해 시스템 간의 데이터 동기화가 수행됩니다. [자세히 알아보기](crm-data-sync.md).

>[!NOTE]
>
>지원되는 SFDC 버전은 Campaign [호환성 매트릭스](../start/compatibility-matrix.md)에 자세히 설명되어 있습니다.

Salesforce 데이터를 Adobe Campaign으로 가져오고 내보내도록 전용 외부 계정을 구성하려면 아래 단계를 따르십시오.

## 연결 만들기{#new-sfdc-external-account}

먼저 Salesforce 외부 계정을 만들어야 합니다.

1. Campaign 탐색기의 **[!UICONTROL Administration > Platform > External accounts]** 노드를 검색하고 외부 계정을 만듭니다.
1. **Type** 섹션에서 **[!UICONTROL Salesforce.com]** 외부 계정을 선택하십시오.
1. 연결을 활성화하려면 설정을 입력하십시오.

   ![](assets/sfdc-external-account.png)

   Adobe Campaign에서 작동하도록 Salesforce CRM 외부 계정을 구성하려면 다음 세부 정보를 제공해야 합니다.

   * **[!UICONTROL Account]** 필드에 Salesforce 로그인을 입력합니다.
   * Salesforce 암호를 입력합니다.
   * **[!UICONTROL Client identifier]** 필드는 무시할 수 있습니다.
   * Salesforce **[!UICONTROL Security token]** 복사/붙여넣기
   * **[!UICONTROL API version]**&#x200B;을(를) 선택합니다. 지원되는 SFDC API 버전은 Campaign [호환성 매트릭스](../start/compatibility-matrix.md)에 나와 있습니다.

1. Campaign에서 계정을 활성화하려면 **사용** 옵션을 선택하십시오.

>[!NOTE]
>
>설정을 승인하려면 Adobe Campaign 클라이언트 콘솔에서 로그오프했다가 다시 로그온해야 합니다.

## 동기화할 테이블 선택{#sfdc-create-tables}

이제 동기화할 테이블을 구성할 수 있습니다.

1. **[!UICONTROL Salesforce CRM configuration wizard...]**&#x200B;을(를) 클릭합니다.
1. 동기화할 테이블을 선택하고 프로세스를 시작합니다.
1. **[!UICONTROL Administration > Configuration > Data schemas]** 노드의 Adobe Campaign에서 생성된 스키마를 확인합니다.

   Campaign에서 가져온 **Salesforce** 스키마의 예:

   ![](assets/sfdc-schemas.png)

## 열거형 동기화{#sfdc-enum-sync}

스키마가 만들어지면 Salesforce에서 Adobe Campaign으로 열거형을 자동으로 동기화할 수 있습니다.

1. **[!UICONTROL Synchronizing enumerations...]** 링크에서 도우미를 엽니다.
1. Salesforce 열거와 일치하는 Adobe Campaign 열거를 선택합니다.
Adobe Campaign 열거형의 모든 값을 CRM의 값으로 바꿀 수 있습니다. 이렇게 하려면 **[!UICONTROL Replace]** 열에서 **[!UICONTROL Yes]**&#x200B;을(를) 선택하십시오.

   ![](assets/sfdc-enum.png)

1. 열거형을 가져오려면 **[!UICONTROL Next]**&#x200B;을(를) 클릭한 다음 **[!UICONTROL Start]**&#x200B;을(를) 클릭합니다.

1. 가져온 값을 확인하려면 **[!UICONTROL Administration > Platform > Enumerations]** 노드를 검색하십시오. [이 페이지](../config/ui-settings.md#enumerations)의 열거형에 대해 자세히 알아보세요.

이제 Adobe Campaign 및 Salesforce.com이 연결되었습니다. 두 시스템 간에 데이터 동기화를 설정할 수 있습니다.

Adobe Campaign 데이터와 SFDC 간에 데이터를 동기화하려면 워크플로우를 만들고 **[!UICONTROL CRM connector]** 활동을 사용합니다.

이 페이지](crm-data-sync.md)에서 데이터 동기화 [에 대해 자세히 알아보세요.
