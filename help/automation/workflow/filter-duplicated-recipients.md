---
product: campaign
title: 중복 수신자 필터링
description: 중복 수신자를 필터링하는 방법 알아보기
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: cfa1f45c-e1ac-4055-996c-6e8d041889bb
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 4%

---

# 중복 수신자 필터링 {#filtering-duplicated-recipients}



이 예제에서는 중복 프로필을 복구하기 위해 게재에 두 번 이상 나타나는 수신자를 필터링하려고 합니다.

이 예제를 만들려면 다음 단계를 적용합니다.

1. 워크플로우에서 **[!UICONTROL Query]** 활동을 끌어다 놓고 활동을 엽니다.
1. **[!UICONTROL Edit query]**&#x200B;을(를) 클릭하고 대상 및 필터링 차원을 **[!UICONTROL Recipients]**(으)로 설정합니다.

   ![](assets/query_recipients_1.png)

1. 게재 로그에 존재하는 수신자를 타겟팅하려면 다음 필터 조건을 정의하십시오. **식** 열에서 **받는 사람 게재 로그(broadlog)**&#x200B;를 선택하고 **연산자** 열에서 **존재(예:**)를 선택합니다.

   ![](assets/query_recipients_2.png)

1. 게재를 타겟팅할 다음 필터 조건을 정의합니다. 식 열에서 **[!UICONTROL Internal name]**&#x200B;을(를) 선택하고 연산자 열에서 **[!UICONTROL equal to]**&#x200B;을(를) 선택합니다.
1. 값 열에서 타겟팅된 게재의 내부 이름을 추가합니다.

   ![](assets/query_recipients_3.png)

1. **[!UICONTROL AND]** 연산자를 사용하여 다른 게재를 대상으로 동일한 작업을 반복합니다.

   ![](assets/query_recipients_4.png)

아웃바운드 전환에는 게재에서 타겟팅한 중복 수신자가 포함됩니다.
