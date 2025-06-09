---
title: Campaign에서 프로필 대상자 만들기
description: 목록을 만들고 대상자를 만드는 방법을 알아봅니다
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 6fbe5616-7b8b-4504-988b-2bbbfd062548
source-git-commit: 70af3bceee67082d6a1bb098e60fd2899dc74600
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 3%

---

# 목록에서 대상자 만들기 {#create-segments}

Campaign 목록을 사용하여 대상자를 만들고 구성합니다.

목록은 게재 작업에서 타겟팅되거나 가져오기 또는 다른 워크플로우 작업 중에 업데이트될 수 있는 정적 연락처 집합입니다. 예를 들어 쿼리를 통해 데이터베이스에서 추출한 모집단을 목록으로 저장할 수 있습니다.

목록은 **[!UICONTROL Profiles and targets]** 탭의 **[!UICONTROL Lists]** 링크를 통해 만들고 관리합니다. 이러한 목록은 기본 Adobe Campaign 프로필 테이블(nms:recipient)을 기반으로 합니다. [자세히 알아보기](../dev/datamodel.md#ootb-profiles.md)

![](assets/list-dashboard.png)

워크플로우에서 **목록 업데이트** 활동을 사용하여 목록을 만들 수 있습니다. 이 활동은 결과 모집단을 목록에 저장합니다. 새 목록을 만들거나 기존 목록을 업데이트하는 데 사용합니다. 기본 제공 프로필 테이블 이외의 다른 유형의 데이터가 포함된 목록을 만들려면 워크플로우를 실행해야 합니다. 예를 들어 방문자 테이블에서 쿼리를 사용한 다음 목록을 업데이트하여 방문자 목록을 만들 수 있습니다. [자세히 알아보기](#create-a-list-wf).

이 비디오를 통해 Adobe Campaign의 목록 관리에 대해 자세히 알아보십시오.

>[!VIDEO](https://video.tv.adobe.com/v/334909?quality=12)


## 연락처 목록 만들기 {#create-a-list-of-contacts}

연락처 목록을 만들려면 아래 단계를 따르십시오.

1. **[!UICONTROL Create]** 단추를 클릭하고 **[!UICONTROL New list]**&#x200B;을(를) 선택합니다.

   ![](assets/new-list.png)

1. 목록 만들기 창의 **[!UICONTROL Edit]** 탭에 정보를 입력하십시오.

   ![](assets/list-details.png)

   * **[!UICONTROL Label]** 필드에 목록 이름을 입력하고 필요한 경우 내부 이름을 변경합니다.
   * 이 목록에 대한 설명을 추가합니다.
   * 만료 날짜를 지정할 수 있습니다. 이 날짜에 도달하면 목록이 삭제되고 자동으로 삭제됩니다.


1. **[!UICONTROL Content]** 탭에서 **[!UICONTROL Add]**&#x200B;을(를) 클릭하여 목록에 속한 프로필을 선택합니다.

   ![](assets/add-profiles-to-a-list.png)

   새 프로필을 만든 후 **[!UICONTROL Create]** 아이콘을 사용하여 이 창에서 바로 목록에 추가할 수 있습니다. 프로필이 데이터베이스에 추가됩니다.

1. 목록을 저장하려면 **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다. 그런 다음 목록 개요에 추가됩니다.


## 필터링된 연락처를 목록으로 변환 {#convert-data-to-a-list}

프로필을 선택하여 목록에 추가할 수 있습니다. 이렇게 하려면 아래 단계를 수행합니다.

1. Campaign 탐색기에서 프로필을 선택하고 마우스 오른쪽 단추를 클릭합니다.

   이러한 프로필은 특정 기준을 충족하도록 필터링할 수 있습니다.

1. **[!UICONTROL Actions > Associate selection with a list...]**&#x200B;을(를) 선택합니다.

   ![](assets/add-selection-to-a-list.png)

1. 기존 목록을 선택하거나 새 목록을 만들고 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다.

   ![](assets/select-the-list.png)

1. **[!UICONTROL Start]** 버튼을 클릭합니다.

   ![](assets/record-a-list.png)

**[!UICONTROL Recreate the list]** 옵션을 선택하여 목록에서 기존 콘텐츠를 삭제하고 목록 만들기를 최적화합니다(프로필이 이미 목록에 연결되어 있는지 확인하는 데 쿼리가 필요하지 않음).

**[!UICONTROL No trace of this job is saved in the database]** 옵션을 선택 취소하면 이 프로세스와 연결된 정보가 저장될 실행 폴더를 선택하거나 만들 수 있습니다.

창의 위쪽 섹션에서 실행을 모니터링할 수 있습니다. **[!UICONTROL Stop]** 단추를 사용하여 프로세스를 중지할 수 있습니다. 이미 처리된 연락처는 목록에 연결됩니다.

실행이 완료되면 **[!UICONTROL Profiles and Targets > Lists]** 메뉴에 액세스하고 목록을 선택합니다. **[!UICONTROL Content]** 탭에는 이 목록에 연결된 프로필이 표시됩니다.


## 워크플로우를 사용하여 목록 만들기  {#create-a-list-wf}

**[!UICONTROL List update]** 활동을 사용하여 목록을 만들거나 받는 사람 목록에 모집단을 추가할 수 있습니다.

아래 예에서는 25명에서 40명 사이의 모든 수신자 목록을 만듭니다.

1. **[!UICONTROL Profiles and targets]**, **[!UICONTROL Targeting workflows]**&#x200B;을(를) 선택한 다음 **[!UICONTROL Create]** 단추에서 새 워크플로우를 만듭니다.
1. 이 워크플로의 레이블(예: &#39;25-40개 연락처&#39;)을 입력하고 설명을 추가한 다음 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다.

   ![](assets/targeting-wf-sample.png)

1. **[!UICONTROL Query]** 활동을 삽입하여 대상 모집단을 정의하고 쿼리를 편집합니다.

   ![](assets/targeting-wf-edit-query.png)

1. 다음과 같이 필터 조건을 정의합니다.

   ![](assets/targeting-wf-age-filter.png)

   [이 섹션](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=ko){target="_blank"}의 워크플로우에서 쿼리를 만드는 방법을 알아봅니다.

1. 이 쿼리에 대한 레이블을 추가하고 변경 사항을 저장합니다.
1. **[!UICONTROL List update]** 활동을 추가하고 편집합니다.

   ![](assets/list-update-activity.png)

1. 활동에 대한 레이블을 입력합니다.
1. **[!UICONTROL Create the list if necessary (Computed name)]** 옵션을 선택하면 첫 번째 워크플로우가 실행되면 목록이 만들어지고 다음 실행으로 업데이트됩니다.
1. 폴더를 선택하고 목록의 레이블을 입력합니다.
1. 테이블을 저장할 **[!UICONTROL Database of the targeting dimension]**&#x200B;을(를) 선택하십시오.
1. 타깃팅 기준과 일치하지 않는 수신자를 삭제하고 새 수신자를 목록에 삽입하려면 **[!UICONTROL Purge the list if it exists (otherwise add to the list)]** 옵션을 선택된 상태로 두십시오.
1. **[!UICONTROL Create or use a list with its own table]** 옵션도 선택된 상태로 두십시오.
1. **[!UICONTROL Generate an outbound transition]** 옵션을 선택하지 않은 상태로 둡니다.
1. **[!UICONTROL Ok]**&#x200B;을(를) 클릭하고 워크플로를 저장합니다.
1. 워크플로를 시작합니다.

   그러면 일치하는 수신자 목록이 만들어집니다. 홈 페이지의 **[!UICONTROL Lists]** 항목에서 이 목록에 액세스할 수 있습니다.

   ![](assets/access-new-list.png)

   워크플로우에 스케줄러를 추가하여 이 워크플로우를 반복적으로 수행할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/scheduler.html?lang=ko){target="_blank"}.

## 목록에서 프로필 제거 {#remove-a-profile-from-a-list}

목록에서 프로필을 제거하려면 목록을 편집하고 **[!UICONTROL Content]** 탭에서 프로필을 선택한 다음 **[!UICONTROL Delete]** 아이콘을 클릭합니다.

## 프로필 목록 삭제 {#delete-a-list-of-profiles}

목록을 삭제하려면 Campaign 탐색기에서 해당 목록을 찾아 선택한 다음 마우스 오른쪽 단추를 클릭합니다. **[!UICONTROL Delete]**&#x200B;을(를) 선택하십시오. 삭제를 확인하는 경고 메시지가 표시됩니다.

>[!NOTE]
>
>목록을 삭제하면 목록의 프로필은 영향을 받지 않지만 프로필의 데이터는 업데이트됩니다.
