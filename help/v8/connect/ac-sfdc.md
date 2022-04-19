---
title: Campaign을 SFDC와 함께 사용하기
description: Campaign 및 Salesforce.com으로 작업하는 방법 알아보기
feature: Overview
role: Data Engineer
level: Beginner
source-git-commit: 59ccee717d857545ed2b3ba6fb850ef8a9d0907b
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 0%

---

# Campaign을 SFDC와 함께 사용하기{#crm-sfdc}

Campaign v8을 연결하도록 Campaign CRM 커넥터를 구성하는 방법을 알아봅니다. **Salesforce.com**.

구성이 완료되면 전용 워크플로우 활동을 통해 시스템 간 데이터 동기화가 수행됩니다. [자세히 알아보기](crm-data-sync.md)

>[!NOTE]
>
>지원되는 SFDC 버전은 Campaign에 자세히 설명되어 있습니다 [호환성 매트릭스](../start/compatibility-matrix.md).


Salesforce 데이터를 Adobe Campaign으로 가져오고 내보낼 수 있는 전용 외부 계정을 구성하려면 아래 단계를 따르십시오.

## 연결 만들기{#new-sfdc-external-account}

먼저 Salesforce 외부 계정을 만들어야 합니다.

1. 찾아보기 **[!UICONTROL Administration > Platform > External accounts]** 노드 아래에 배치하여 외부 계정을 만듭니다.
1. 선택 **[!UICONTROL Salesforce.com]** 의 외부 계정 **유형** 섹션을 참조하십시오.
1. 연결을 활성화할 설정을 입력합니다.

   ![](assets/sfdc-external-account.png)

   Adobe Campaign에서 작동하도록 Salesforce CRM 외부 계정을 구성하려면 다음 세부 정보를 제공해야 합니다.

   * 에 Salesforce 로그인을 입력합니다. **[!UICONTROL Account]** 필드.
   * Salesforce 암호를 입력합니다.
   * 을 무시할 수 있습니다 **[!UICONTROL Client identifier]** 필드.
   * Salesforce 복사/붙여넣기 **[!UICONTROL Security token]**
   * 을(를) 선택합니다 **[!UICONTROL API version]**. 지원되는 SFDC API 버전은 Campaign에 나열되어 있습니다 [호환성 매트릭스](../start/compatibility-matrix.md).

1. 을(를) 선택합니다 **활성화** campaign에서 계정을 활성화하는 옵션.

>[!NOTE]
>
>설정을 승인하려면 로그오프했다가 Adobe Campaign 콘솔에 다시 로그온해야 합니다.

## 동기화할 테이블 선택{#sfdc-create-tables}

이제 동기화할 테이블을 구성할 수 있습니다.

1. 을(를) 클릭합니다. **[!UICONTROL Salesforce CRM configuration wizard...]**.
1. 동기화할 테이블을 선택하고 프로세스를 시작합니다.
1. Adobe Campaign에서 생성된 스키마를 **[!UICONTROL Administration > Configuration > Data schemas]** 노드 아래에 있어야 합니다.

   예 **Salesforce** Campaign에서 가져온 스키마:

   ![](assets/sfdc-schemas.png)

## 열거형 동기화{#sfdc-enum-sync}

스키마가 만들어지면 Salesforce에서 Adobe Campaign으로 열거형을 자동으로 동기화할 수 있습니다.

1. 에서 도우미를 엽니다.  **[!UICONTROL Synchronizing enumerations...]** 링크를 클릭합니다.
1. Salesforce 열거와 일치하는 Adobe Campaign 열거형을 선택합니다.
Adobe Campaign 열거형의 모든 값을 CRM의 값으로 바꿀 수 있습니다. 이렇게 하려면 을(를) 선택합니다. **[!UICONTROL Yes]** 에서 **[!UICONTROL Replace]** 열.

   ![](assets/sfdc-enum.png)

1. 클릭 **[!UICONTROL Next]** 그리고 **[!UICONTROL Start]** 열거형 가져오기를 시작하려면

1. 찾아보기 **[!UICONTROL Administration > Platform > Enumerations]** 노드 를 사용하여 가져온 값을 확인합니다.


이제 Adobe Campaign 및 Salesforce.com이 연결됩니다. 두 시스템 간에 데이터 동기화를 설정할 수 있습니다.

Adobe Campaign 데이터와 SFDC 간의 데이터를 동기화하려면 워크플로우를 만들고 **[!UICONTROL CRM connector]** 활동.

데이터 동기화에 대해 자세히 알아보기 [이 페이지에서](crm-data-sync.md).
