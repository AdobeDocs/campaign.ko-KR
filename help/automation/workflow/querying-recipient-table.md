---
product: campaign
title: 수신자 테이블 쿼리
description: 수신자 테이블을 쿼리하는 방법 알아보기
feature: Query Editor
role: User, Data Engineer
version: Campaign v8, Campaign Classic v7
exl-id: 7f859ce9-7ab8-46e1-8bd6-43aaffe30da2
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 3%

---

# 수신자 테이블 쿼리 {#querying-recipient-table}



이 예제에서는 이메일 도메인이 &quot;orange.co.uk&quot;이고 런던에 거주하지 않는 수신자의 이름과 이메일을 복구하려고 합니다.

* 어떤 테이블을 선택해야 할까요?

  수신자 테이블(nms:recipient)

* 출력 열로 선택할 필드

  이메일, 이름, 도시 및 계정 번호

* 수신자의 필터링 조건은 무엇입니까?

  구/군/시 및 이메일 도메인

* 정렬이 구성되었습니까?

  예, **[!UICONTROL Account number]** 및 **[!UICONTROL Last name]** 기반

이 예제를 만들려면 다음 단계를 적용합니다.

1. **[!UICONTROL Tools > Generic query editor...]**&#x200B;을(를) 클릭하고 **수신자**(**nms:recipient**) 테이블을 선택합니다. 그 다음 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다.
1. 선택: **[!UICONTROL Last name]**, **[!UICONTROL First name]**, **[!UICONTROL Email]**, **[!UICONTROL City]** 및 **[!UICONTROL Account number]**. 이러한 필드는 **[!UICONTROL Output columns]**&#x200B;에 추가됩니다. 그 다음 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다.

   ![](assets/query_editor_03.png)

1. 열을 정렬하여 올바른 순서로 표시합니다. 여기에서는 계정 번호를 내림차순으로 정렬하고 이름을 알파벳순으로 정렬합니다. 그 다음 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다.

   ![](assets/query_editor_04.png)

1. **[!UICONTROL Data filtering]** 창에서 검색을 구체화하십시오. **[!UICONTROL Filtering conditions]**&#x200B;을(를) 선택하고 **[!UICONTROL Next]**&#x200B;을(를) 클릭하십시오.
1. **[!UICONTROL Target element]** 창에서 필터 설정을 입력할 수 있습니다.

   필터 조건, 즉 이메일 도메인이 &quot;orange.co.uk&quot;과 같은 수신자를 정의합니다. 이렇게 하려면 **[!UICONTROL Expression]** 열에서 **전자 메일 도메인(@email)**&#x200B;을 선택하고 **[!UICONTROL Operator]** 열에서 **같음**&#x200B;을 선택한 다음 **[!UICONTROL Value]** 열에 &quot;orange.co.uk&quot;을 입력하십시오.

   ![](assets/query_editor_05.png)

1. 필요한 경우 **[!UICONTROL Distribution of values]** 단추를 클릭하여 잠재 고객의 전자 메일 도메인을 기반으로 배포를 봅니다. 백분율은 데이터베이스의 각 이메일 도메인에 대해 사용할 수 있습니다. 필터가 적용될 때까지 &quot;orange.co.uk&quot; 이외의 도메인이 표시됩니다.

   쿼리 요약이 창 하단에 표시됩니다. **이메일 도메인이 &#39;orange.co.uk&#39;**&#x200B;과(와) 같습니다.

1. 쿼리 결과에 대한 아이디어를 얻으려면 **[!UICONTROL Preview]**&#x200B;을(를) 클릭하십시오. &quot;orange.co.uk&quot; 전자 메일 도메인만 표시됩니다.

   ![](assets/query_editor_nveau_17.png)

1. 이제 London에 거주하지 않는 연락처를 찾기 위해 쿼리를 변경합니다.

   **[!UICONTROL Expression]** 열에서 **[!UICONTROL City (location/@city)]**&#x200B;을(를) 선택하고 **[!UICONTROL different from]**&#x200B;을(를) 연산자로 선택한 다음 **[!UICONTROL Value]** 열에 **[!UICONTROL London]**&#x200B;을(를) 입력합니다.

   ![](assets/query_editor_08.png)

1. **[!UICONTROL Data formatting]** 창으로 이동합니다. 열 순서를 확인합니다. &quot;계좌 번호&quot; 열 아래로 &quot;구/군/시&quot; 열을 위로 이동합니다.

   목록에서 제거하려면 &quot;이름&quot; 열의 선택을 취소하십시오.

   ![](assets/query_editor_nveau_15.png)

1. **[!UICONTROL Data preview]** 창에서 **[!UICONTROL Start the preview of the data]**&#x200B;을(를) 클릭합니다. 이 함수는 쿼리의 결과를 계산합니다.

   **[!UICONTROL Column results]** 탭에는 쿼리 결과가 열에 표시됩니다.

   그 결과 런던에 거주하지 않는 &quot;orange.co.uk&quot; 이메일 도메인을 사용하는 모든 수신자가 표시됩니다. 이전 단계에서 선택 취소되었으므로 &quot;First name&quot; 열은 표시되지 않습니다. 계정 번호는 내림차순으로 정렬됩니다.

   ![](assets/query_editor_nveau_12.png)

   **[!UICONTROL XML result]** 탭에는 결과가 XML 형식으로 표시됩니다.

   ![](assets/query_editor_nveau_13.png)

   **[!UICONTROL Generated SQL queries]** 탭에는 쿼리 결과가 SQL 형식으로 표시됩니다.

   ![](assets/query_editor_nveau_14.png)
