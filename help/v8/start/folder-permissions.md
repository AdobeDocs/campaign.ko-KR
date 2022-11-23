---
title: Campaign 폴더에 대한 권한 부여 및 제한
description: 폴더에 대한 권한을 부여하거나 제한하는 방법을 알아봅니다
feature: Permissions
role: User, Admin
level: Beginner
source-git-commit: 857445d7d7d8080e479bdc596fb3162c2b4a2b6b
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# 폴더 권한 관리{#manage-folder-permissions}

## 폴더에 대한 액세스 제한{#restrict-access-to-a-folder}

폴더에 대한 권한을 사용하여 Campaign 데이터에 대한 액세스를 구성하고 제어할 수 있습니다.

폴더 관리에 대해서는 [이 페이지](../audiences/folders-and-views.md).

특정 Campaign 폴더에 대한 권한을 편집하려면 아래 단계를 따르십시오.

1. 폴더를 마우스 오른쪽 단추로 클릭하고 를 선택합니다. **[!UICONTROL Properties...]**.
1. 다음 위치로 이동합니다. **[!UICONTROL Security]** 탭하여 이 폴더의 승인을 확인합니다.

   ![](assets/folder-permissions.png)

* 종료 **그룹 또는 연산자 인증**&#x200B;를 클릭하고 **[!UICONTROL Add]** 버튼을 클릭하고 이 폴더에 대한 권한을 할당할 그룹 또는 연산자를 선택합니다.
* 종료 **그룹 또는 연산자 사용 금지**&#x200B;를 클릭합니다. **[!UICONTROL Delete]** 이 폴더에 대한 권한을 제거할 그룹 또는 연산자를 선택하십시오.
* 종료 **그룹 또는 연산자에 할당된 권한을 선택합니다**&#x200B;를 클릭하고 그룹 또는 연산자를 선택하고 부여할 액세스 권한을 선택한 다음 다른 권한을 선택 취소합니다.

## 권한 전파 {#propagate-permissions}

권한 및 액세스 권한을 전파하려면 **[!UICONTROL Propagate]** 옵션을 클릭합니다.

이 창에 정의된 권한은 현재 노드의 모든 하위 폴더에 적용됩니다. 각 하위 폴더에 대해 항상 이러한 권한을 오버로드할 수 있습니다.

>[!NOTE]
>
>확인 취소 **[!UICONTROL Propagate]** 폴더에 대한 옵션이 하위 폴더에 대해 지워지지 않습니다. 각 하위 폴더에 대해 명시적으로 지우십시오.

## 모든 연산자에 대한 액세스 권한 부여 {#grant-access-to-all-operators}

에서 **[!UICONTROL Security]** 탭에서 을 선택합니다 **[!UICONTROL System folder]** 권한에 관계없이 모든 연산자에 대한 액세스를 허용합니다.

이 옵션이 지워지면 액세스를 허용할 수 있도록 운영자(또는 그 그룹)를 권한 목록에 명시적으로 추가해야 합니다.
