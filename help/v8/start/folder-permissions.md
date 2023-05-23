---
title: Campaign 폴더에 대한 권한 부여 및 제한
description: 폴더에 대한 권한을 부여하거나 제한하는 방법 알아보기
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 5bd8dbba-7a06-4737-bc5a-60354f91c709
source-git-commit: b96ac3bd2365c548d071e626721d606dd33200b5
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# 폴더 권한 관리{#manage-folder-permissions}

## 폴더에 대한 액세스 제한{#restrict-access-to-a-folder}

폴더에 대한 권한을 사용하여 Campaign 데이터에 대한 액세스를 구성하고 제어합니다.

폴더 관리에 대한 자세한 내용은 [이 페이지](../audiences/folders-and-views.md).

특정 Campaign 폴더에 대한 권한을 편집하려면 아래 단계를 따르십시오.

1. 폴더를 마우스 오른쪽 단추로 클릭하고 **[!UICONTROL Properties...]**.
1. 다음으로 이동 **[!UICONTROL Security]** 이 폴더에 대한 권한을 보려면 탭하십시오.

   ![](assets/folder-permissions.png)

* 종료 **그룹 또는 운영자 승인**&#x200B;를 클릭하고 **[!UICONTROL Add]** 단추를 클릭하고 이 폴더에 대한 권한을 할당할 그룹 또는 연산자를 선택합니다.
* 종료 **그룹 또는 연산자 금지**, 클릭 **[!UICONTROL Delete]** 이 폴더에 대한 권한 부여를 제거하려면 그룹 또는 연산자를 선택하십시오.
* 종료 **그룹 또는 연산자에 할당된 권한 선택**&#x200B;을 클릭하고, 그룹 또는 연산자를 선택하고, 부여할 액세스 권한을 선택한 다음, 다른 권한은 선택 취소합니다.

## 권한 전파 {#propagate-permissions}

권한 및 액세스 권한을 전파하려면 **[!UICONTROL Propagate]** 폴더 속성의 옵션입니다.

이 창에서 정의된 권한이 현재 노드의 모든 하위 폴더에 적용됩니다. 각 하위 폴더에 대해 이러한 권한을 항상 오버로드할 수 있습니다.

>[!NOTE]
>
>선택 취소 **[!UICONTROL Propagate]** 폴더 옵션은 하위 폴더에 대해 지우지 않습니다. 각 하위 폴더에 대해 명시적으로 지워야 합니다.

## 모든 운영자에게 액세스 권한 부여 {#grant-access-to-all-operators}

다음에서 **[!UICONTROL Security]** 탭에서 **[!UICONTROL System folder]** 사용 권한에 관계없이 모든 운영자에 대한 액세스를 허용합니다.

이 옵션을 선택하지 않은 경우 운영자(또는 해당 그룹)가 액세스할 수 있도록 승인 목록에 다시 명시적으로 추가해야 합니다.
