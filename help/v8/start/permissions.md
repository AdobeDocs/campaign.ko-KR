---
solution: Campaign
product: Adobe Campaign
title: Campaign v8에 권한 부여
description: Campaign v8에 권한을 부여하는 방법 알아보기
feature: 대상자
role: Data Engineer
level: Beginner
source-git-commit: a57855556751e85e7a1f7751a103ca157f434a8a
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 5%

---

# 사용 권한 시작

Adobe Campaign에서 사용자는 **연산자**&#x200B;이고 **운영자 그룹**&#x200B;은 사용자 역할을 나타냅니다.

연산자는 로그인 및 작업을 수행할 수 있는 권한이 있는 Adobe Campaign 사용자입니다. 기본적으로 연산자는 **[!UICONTROL Administration > Access management > Operators]** 노드에 저장됩니다.

Adobe Campaign에는 캠페인 관리자 또는 워크플로우 감독자와 같은 내장된 운영자 그룹이 포함되어 있습니다. 모든 기본 제공 그룹은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}에 나열되어 있습니다.

운영자 그룹의 구성원으로서, 사용자는 &#39;명명된 권한&#39;이라는 작업을 수행할 수 있는 권한을 가지며, **탐색기** 보기의 폴더에 포함된 데이터에 액세스할 수 있습니다. 연산자는 여러 연산자 그룹의 멤버일 수 있습니다. 권한 및 액세스 권한은 추가 기능입니다.

명명된 권한 부여 권한:

* 작업 수행
예를 들어 **배달 준비** 명명된 오른쪽의 **배달 연산자** 그룹의 구성원에 대해 게재 편집기의 **분석** 단추가 활성화됩니다

* 폴더에 액세스
운영자 그룹의 멤버십은 폴더의 보안 설정을 변경하여 폴더에 대한 액세스 권한을 부여하거나 제한할 수 있습니다. [자세한 내용은 Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder)를 참조하십시오{target=&quot;_blank&quot;}. 예를 들어 영향을 줄 수 있습니다. **새 엔티티(예: 게재, 프로필 등)를 만들려면** 쓰기 액세스&#x200B;**엔티티를 사용하려면 읽기 액세스**, **액세스**&#x200B;삭제 엔티티를 삭제합니다.

## 보안 영역

각 연산자는 인스턴스에 로그온하기 위해 영역에 연결해야 하며 운영자 IP는 보안 영역에 정의된 주소 또는 주소 세트에 포함해야 합니다. 보안 영역 구성은 Adobe Campaign 서버의 구성 파일에서 수행됩니다.

연산자는 콘솔의 프로필에서 보안 영역에 연결되며 **[!UICONTROL Administration > Access management > Operators]** 노드에서 액세스할 수 있습니다.

?? Adobe은 관리되는 Cloud Services 사용자로 보안 영역을 설정합니다. 자세한 내용은 [Adobe](support.md#support)에 문의하십시오.

**Campaign Classic v7 설명서에서 자세히 알아보기**

* [기본 제공 명명된 권한](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html){target=&quot;_blank&quot;}

* [내장 연산자 그룹](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

* [권한](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html) 설정 단계{target=&quot;_blank&quot;}
