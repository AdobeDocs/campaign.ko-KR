---
title: 데이터 소스 변경
description: 데이터 소스 변경 활동에 대해 자세히 알아보기
feature: Workflows, Data Management, Federated Data Access
role: User
exl-id: ca7eca9d-9112-4ea1-9a0c-a24cf6a978e6
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%

---

# 데이터 소스 변경 {#change-data-source}

사용 **[!UICONTROL Change data source]** 의 데이터 소스를 변경하는 활동 [워크플로 작업 표](use-workflow-data.md#workflow-temporary-work-table). 이 활동을 통해 FDA(Federated Data Access), FFDA(Campaign Cloud Database) 및 Campaign 로컬 데이터베이스와 같은 다양한 데이터 소스에서 데이터를 보다 유연하게 관리할 수 있습니다.

워크플로우 **[!UICONTROL Working table]** 은 워크플로우 활동과 데이터를 처리하고 공유하는 데 사용됩니다.

기본적으로 **[!UICONTROL Working table]** 쿼리해야 하는 데이터의 소스와 동일한 데이터베이스에 생성됩니다.
예를 들어 **[!UICONTROL Recipients]** 클라우드 데이터베이스에 저장된 테이블에는 워크플로가 **[!UICONTROL Working table]** 동일한 클라우드 데이터베이스에서.

사용 **[!UICONTROL Change Data Source]** 다른 데이터 소스를 사용하기 위한 활동 **[!UICONTROL Working table]**.

를 사용할 때는 **[!UICONTROL Change Data Source]** 활동에서 워크플로우 실행을 계속하려면 클라우드 데이터베이스로 다시 전환해야 합니다.

을(를) 사용하려면 **[!UICONTROL Change Data Source]** 활동. 다음을 수행해야 합니다.

1. 워크플로 만들기.

1. 을(를) 사용하여 타겟팅된 수신자 쿼리 **[!UICONTROL Query]** 활동.

   에 대한 자세한 내용은 **[!UICONTROL Query]** 활동. 다음을 참조하십시오. [페이지](query.md#create-a-query).

1. 추가 **[!UICONTROL Change data source]** 활동.

   ![](assets/change-data-source.png)

1. 편집 **[!UICONTROL Change data source]** 선택할 활동 **[!UICONTROL Default data source]**.

   그러면 쿼리 결과가 포함된 작업 테이블이 기본 Campaign 로컬 데이터베이스로 이동합니다.

   ![](assets/change-data-source_2.png)

1. 추가 **[!UICONTROL JavaScript code]** 작업 테이블에서 단일 작업을 수행하는 활동.

   에 대한 자세한 내용은 **[!UICONTROL JavaScript code]** 활동( )은 [이 페이지](sql-code-and-javascript-code.md#javascript-code).

1. 다른 항목 추가 **[!UICONTROL Change data source]** 활동을 클라우드 데이터베이스로 다시 전환합니다.

1. 이 활동을 편집하고 선택 **[!UICONTROL Active FDA external account]**&#x200B;및 해당 **[!UICONTROL External database]** 외부 계정입니다.

   ![](assets/change-data-source_3.png)

1. 이제 워크플로우를 시작할 수 있습니다.
