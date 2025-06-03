---
title: Campaign 폴더에 대한 권한 부여 및 제한
description: 폴더에 대한 권한을 부여하거나 제한하는 방법 알아보기
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 5bd8dbba-7a06-4737-bc5a-60354f91c709
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 18%

---

# 폴더 권한 관리{#manage-folder-permissions}

## 폴더에 대한 액세스 제한{#restrict-access-to-a-folder}

폴더에 대한 권한을 사용하여 Campaign 데이터에 대한 액세스를 구성하고 제어합니다.

폴더 관리는 [이 페이지](../audiences/folders-and-views.md)에 자세히 설명되어 있습니다.

특정 Campaign 폴더에 대한 권한을 편집하려면 아래 단계를 따르십시오.

1. 폴더를 마우스 오른쪽 단추로 클릭하고 **[!UICONTROL Properties...]**&#x200B;을(를) 선택합니다.
1. 이 폴더에 대한 권한을 보려면 **[!UICONTROL Security]** 탭으로 이동하십시오.

   ![](assets/folder-permissions.png)

* **그룹 또는 연산자를 승인**&#x200B;하려면 **[!UICONTROL Add]** 단추를 클릭하고 이 폴더에 대한 승인을 할당할 그룹 또는 연산자를 선택하십시오.
* **그룹 또는 연산자를 금지하려면** **[!UICONTROL Delete]**&#x200B;을(를) 클릭하고 그룹 또는 연산자를 선택하여 이 폴더에 대한 권한을 제거하십시오.
* **그룹 또는 연산자에 할당된 권한을 선택**&#x200B;하려면 그룹 또는 연산자를 선택하고 부여할 액세스 권한을 선택한 다음 다른 권한을 선택 취소합니다.

>[!NOTE]
>
>쓰기 권한이 있는 폴더가 최소 하나 이상 있어야 오브젝트를 만들 수 있습니다.
>
>조각을 만들려면 관리자 권한은 필요는 없지만 적어도 하나의 “콘텐츠 시각적 조각” 폴더에 대한 쓰기 권한이 있어야 합니다. 그렇지 않으면 시각적 조각을 만들 수 없습니다.

## 권한 전파 {#propagate-permissions}

권한 및 액세스 권한을 전파하려면 폴더 속성에서 **[!UICONTROL Propagate]** 옵션을 선택하십시오.

이 창에서 정의된 권한이 현재 노드의 모든 하위 폴더에 적용됩니다. 각 하위 폴더에 대해 이러한 권한을 항상 오버로드할 수 있습니다.

>[!NOTE]
>
>폴더에 대한 **[!UICONTROL Propagate]** 옵션을 선택 취소하면 하위 폴더에서 해당 옵션이 지워지지 않습니다. 각 하위 폴더에 대해 명시적으로 지워야 합니다.

## 모든 운영자에게 액세스 권한 부여 {#grant-access-to-all-operators}

**[!UICONTROL Security]** 탭에서 **[!UICONTROL System folder]**&#x200B;을(를) 선택하여 해당 사용 권한에 관계없이 모든 연산자에 대한 액세스를 허용합니다.

이 옵션을 선택하지 않은 경우 운영자(또는 해당 그룹)가 액세스할 수 있도록 승인 목록에 다시 명시적으로 추가해야 합니다.
