---
title: Campaign v8에서 쿼리 디자인
description: Campaign 클라이언트 콘솔에서 쿼리를 만드는 방법을 알아봅니다
feature: Query Editor, Data Management
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: edd495a377559007dad7158c9ab4a4917d89ae73
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 2%

---

# Campaign 데이터베이스 쿼리

쿼리는 선택한 테이블의 필드를 사용하거나 공식을 사용하여 만들어집니다.

Adobe Campaign에서 쿼리를 작성하는 단계는 다음과 같습니다.

1. [작업 테이블을 선택하십시오](#step-1---choose-a-table).
1. [추출할 데이터를 선택합니다](#step-2---choose-data-to-extract).
1. [데이터 정렬 모드를 정의](#step-3---sort-data)합니다.
1. [데이터 필터링 옵션을 정의](#step-4---filter-data)합니다.
1. [데이터 서식을 구성합니다](#step-5---format-data).
1. [쿼리 결과를 미리 봅니다](#step-6---preview-data).

이러한 모든 단계는 [일반 쿼리 편집기](query-editor.md)에서 사용할 수 있습니다. 쿼리가 다른 컨텍스트에서 작성되면 일부 단계가 누락될 수 있습니다. 쿼리에 대한 자세한 내용은 [워크플로우 쿼리 활동 설명서](../../automation/workflow/query.md)를 참조하세요.


## 1단계 - 표 선택 {#step-1---choose-a-table}

Campaign 데이터베이스를 쿼리하려면 **[일반 쿼리 편집기](query-editor.md)**&#x200B;를 열고 **[!UICONTROL Document type]** 창에서 쿼리할 데이터가 포함된 테이블을 선택하십시오.

![](assets/query_editor_nveau_21.png)

필요한 경우 필터 필드 또는 **[!UICONTROL Filters]** 단추를 사용하여 데이터를 필터링합니다.

## 2단계 - 추출할 데이터 선택 {#step-2---choose-data-to-extract}

**[!UICONTROL Data to extract]** 화면에서 출력에 포함할 필드를 선택합니다. 이러한 필드는 결과에 표시되는 열을 정의합니다.

예를 들어 **[!UICONTROL Age]**, **[!UICONTROL Primary key]**, **[!UICONTROL Email domain]** 및 **[!UICONTROL City]**&#x200B;을(를) 선택할 수 있습니다. 출력은 이 선택에 따라 구조화됩니다. 열의 순서를 조정하려면 창 오른쪽에 있는 파란색 화살표를 사용합니다.

![](assets/query_editor_nveau_01.png)

수식을 추가하거나 집계 함수에 프로세스를 적용하여 표현식을 수정할 수 있습니다. 표현식을 편집하려면 **[!UICONTROL Expression]** 열 필드를 클릭한 다음 **[!UICONTROL Edit expression]**&#x200B;을(를) 선택합니다.

![](assets/query_editor_nveau_97.png)

출력 열에 표시된 데이터를 그룹화할 수 있습니다. 이렇게 하려면 **[!UICONTROL Yes]** 창의 **[!UICONTROL Group]** 열에서 **[!UICONTROL Data to extract]**&#x200B;을(를) 선택합니다. 그러면 선택한 그룹화 축을 기준으로 결과가 집계됩니다. 그룹화를 사용하는 쿼리의 예제는 [이 섹션](../../automation/workflow/query-delivery-info.md)을 참조하세요.

![](assets/query_editor_nveau_56.png)

* **[!UICONTROL Handle groupings (GROUP BY + HAVING)]** 옵션을 사용하면 결과를 그룹화하고 해당 그룹에 조건을 적용할 수 있습니다. 출력 열의 모든 필드에 적용됩니다. 예를 들어, 출력 열의 값을 그룹화한 다음 결과를 필터링하여 35세에서 50세 사이의 수신자와 같은 특정 정보만 검색할 수 있습니다.

  이 작업에 대한 자세한 정보는 [이 섹션](../../automation/workflow/query-grouping-management.md)을 참조하십시오.

**[!UICONTROL Remove duplicate rows (DISTINCT)]** 옵션은 출력에서 동일한 행을 제거합니다(중복 제거). 예를 들어 **성**, **이름** 및 **전자 메일**&#x200B;을(를) 출력 열로 선택하면 세 필드 모두에서 값이 같은 모든 레코드가 중복 항목으로 간주됩니다. 각 연락처가 한 번만 표시되도록 하기 위해 하나의 인스턴스만 결과에 유지됩니다.

## 3단계 - 데이터 정렬 {#step-3---sort-data}

**[!UICONTROL Sorting]** 창을 사용하면 열 내용을 정렬할 수 있습니다. 화살표를 사용하여 열 순서를 변경합니다.

* **[!UICONTROL Sorting]** 열을 사용하면 열 내용을 A부터 Z까지 또는 오름차순으로 간단히 정렬하고 정렬할 수 있습니다.
* **[!UICONTROL Descending sort]**&#x200B;은(는) 콘텐츠를 Z부터 A까지 내림차순으로 정렬합니다. 예를 들어 가장 높은 수치가 목록 맨 위에 표시되는 것과 같이 레코드 매출을 볼 때 유용합니다.

이 예제에서 데이터는 수신자 연령을 기준으로 오름차순으로 정렬됩니다.

![](assets/query_editor_nveau_57.png)

## 4단계 - 데이터 필터링 {#step-4---filter-data}

쿼리 편집기를 사용하면 데이터를 필터링하여 결과를 좁힐 수 있습니다. 사용 가능한 필터는 쿼리하는 테이블에 따라 다릅니다.

![](assets/query_editor_nveau_09.png)

**[!UICONTROL Filtering conditions]**&#x200B;을(를) 선택하면 **[!UICONTROL Target elements]** 섹션이 열립니다. 여기에서 수집할 데이터를 필터링하는 규칙을 정의할 수 있습니다.

* 새 필터를 만들려면 조건을 만드는 데 필요한 필드, 연산자 및 값을 선택합니다. [이 페이지의 &#x200B;](filter-conditions.md)에 설명된 대로 여러 조건을 결합할 수도 있습니다.

* 기존 필터를 다시 사용하려면 **[!UICONTROL Add]** 단추를 클릭하고 **[!UICONTROL Predefined filter]**&#x200B;을(를) 선택한 다음 원하는 필터를 선택하십시오.

  ![](assets/query_editor_15.png)

**[!UICONTROL Generic query editor]**&#x200B;에서 만든 필터는 다른 쿼리 응용 프로그램에서 다시 사용할 수 있으며, 그 반대도 마찬가지입니다. 나중에 사용할 수 있도록 필터를 저장하려면 **[!UICONTROL Save]** 아이콘을 클릭합니다.

>[!NOTE]
>
>필터를 만들고 사용하는 방법에 대한 자세한 내용은 [필터링 옵션](filter-conditions.md)을 참조하세요.

다음 예제와 같이 모든 영어권 수신자를 복구하려면 &quot;받는 사람 언어 **같음** EN&quot;을 선택하십시오.

![](assets/query_editor_nveau_89.png)

>[!NOTE]
>
>**값** 필드에 다음 공식을 입력하여 옵션에 직접 액세스할 수 있습니다. **$(options:OPTION_NAME)**.

필터링 조건의 결과를 보려면 **[!UICONTROL Preview]** 탭을 클릭하십시오. 이 경우 모든 영어권 수신자는 이름, 이름 및 이메일 주소와 함께 표시됩니다.

![](assets/query_editor_nveau_98.png)

SQL 언어에 익숙한 사용자는 **[!UICONTROL Generate SQL query]**&#x200B;을(를) 클릭하여 SQL에서 쿼리를 볼 수 있습니다.

![](assets/query_editor_nveau_99.png)

## 5단계 - 데이터 서식 지정 {#step-5---format-data}

제한 필터를 구성하면 **[!UICONTROL Data formatting]** 창이 열립니다. 이 창에서는 출력 열을 재배열하고, 데이터를 변환하고, 열 레이블 대소문자를 조정할 수 있습니다. 계산된 필드를 만들어 최종 결과에 공식을 적용할 수도 있습니다.

>[!NOTE]
>
>계산된 필드의 형식에 대한 자세한 내용은 [계산된 필드 만들기](filter-conditions.md#creating-calculated-fields)를 참조하세요.

선택하지 않은 열은 데이터 미리 보기 창에서 숨겨집니다.

![](assets/query_editor_nveau_10.png)

**[!UICONTROL Transformation]** 열을 사용하면 열 레이블을 대문자 또는 소문자로 변경할 수 있습니다. 열을 선택하고 **[!UICONTROL Transformation]** 열을 클릭합니다. 다음을 선택할 수 있습니다.

* **[!UICONTROL Switch to lower case]**,
* **[!UICONTROL Switch to upper case]**,
* **[!UICONTROL First letter in upper case]**.

![](assets/query_editor_nveau_42.png)

## 6단계 - 데이터 미리보기 {#step-6---preview-data}

**[!UICONTROL Data preview]** 창은 쿼리 프로세스의 마지막 단계를 표시합니다. 열 또는 XML 형식으로 표시할 수 있는 결과를 검토하려면 **[!UICONTROL Start the preview of the data]**&#x200B;을(를) 클릭하십시오. 기본 SQL 쿼리를 검사하려면 **[!UICONTROL Generated SQL queries]** 탭을 엽니다. 이 단계에서는 쿼리를 더 사용하기 전에 쿼리가 예상대로 작동하는지 확인할 수 있습니다.

이 예제에서 데이터는 수신자 연령을 기준으로 오름차순으로 정렬됩니다.

![](assets/query_editor_nveau_11.png)

>[!NOTE]
>
>콘솔에서 사용할 수 있는 모든 목록의 경우처럼 기본적으로 처음 200개의 줄만 **[!UICONTROL Data preview]** 창에 표시됩니다. 변경하려면 **[!UICONTROL Lines to display]** 상자에 숫자를 입력하고 **[!UICONTROL Start the preview of the data]**&#x200B;을(를) 클릭합니다. [자세히 알아보기](../config/ui-settings.md#manage-and-customize-lists)



**관련 항목**

* [워크플로우 쿼리 활동](../../automation/workflow/query.md)
* [수신자 테이블 쿼리](../../automation/workflow/querying-recipient-table.md)
* [필터링 조건](filter-conditions.md)