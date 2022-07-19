---
title: 데이터 소스 변경
description: 데이터 소스 변경 활동에 대해 자세히 알아보십시오
feature: Workflows, Data Management, Federated Data Access
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%

---

# 데이터 소스 변경 {#change-data-source}

를 사용하십시오 **[!UICONTROL Change data source]** 활동을 사용하여 [워크플로우 작업 테이블](use-workflow-data.md#workflow-temporary-work-table). 이 활동을 사용하면 FDA(Federated Data Access), FDA(Campaign Cloud 데이터베이스) 및 Campaign Local 데이터베이스와 같은 다양한 데이터 소스에서 데이터를 관리할 수 있습니다.

워크플로우 **[!UICONTROL Working table]** 는 워크플로우 활동을 처리하고 데이터와 공유하는 데 사용됩니다.

기본적으로 **[!UICONTROL Working table]** 는 쿼리해야 하는 데이터의 소스와 동일한 데이터베이스에 만들어집니다.
예를 들어 **[!UICONTROL Recipients]** 클라우드 데이터베이스에 저장된 테이블에서 워크플로우는 **[!UICONTROL Working table]** ( 동일한 Cloud 데이터베이스)를 참조하십시오.

다음 작업 **[!UICONTROL Change Data Source]** 활동에 대해 다른 데이터 소스를 사용 **[!UICONTROL Working table]**.

를 사용할 때는 **[!UICONTROL Change Data Source]** 활동을 수행하려면 클라우드 데이터베이스로 다시 전환해야 합니다.

를 사용하려면 **[!UICONTROL Change Data Source]** 활동, 다음 작업을 수행해야 합니다.

1. 워크플로우 만들기.

1. 타겟팅된 수신자를 **[!UICONTROL Query]** 활동.

   에 대한 자세한 내용은 **[!UICONTROL Query]** 활동, 다음 문서를 참조하십시오 [페이지](query.md#create-a-query).

1. 추가 **[!UICONTROL Change data source]** 활동.

   ![](assets/change-data-source.png)

1. 편집 **[!UICONTROL Change data source]** 선택할 활동 **[!UICONTROL Default data source]**.

   쿼리 결과가 포함된 작업 테이블이 기본 Campaign Local 데이터베이스로 이동합니다.

   ![](assets/change-data-source_2.png)

1. 추가 **[!UICONTROL JavaScript code]** 작업 테이블에서 단일 작업을 수행하는 활동.

   에 대한 자세한 내용은 **[!UICONTROL JavaScript code]** 활동, [이 페이지](sql-code-and-javascript-code.md#javascript-code).

1. 다른 추가 **[!UICONTROL Change data source]** 활동을 사용하여 다시 클라우드 데이터베이스로 전환합니다.

1. 이 활동을 편집하고 을(를) 선택합니다 **[!UICONTROL Active FDA external account]**, 및 해당 **[!UICONTROL External database]** 외부 계정.

   ![](assets/change-data-source_3.png)

1. 이제 워크플로우를 시작할 수 있습니다.
