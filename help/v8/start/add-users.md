---
title: Campaign v8에 권한 부여
description: Campaign v8에 권한을 부여하는 방법 알아보기
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 2%

---

# 사용 권한 시작

Adobe Campaign에서 사용자는 **운영자**&#x200B;이고 **운영자 그룹**&#x200B;은 사용자 역할을 나타냅니다.

운영자는 로그인하고 작업을 수행할 수 있는 권한이 있는 Adobe Campaign 사용자입니다. 기본적으로 연산자는 **[!UICONTROL Administration > Access management > Operators]** 노드에 저장됩니다.

Adobe Campaign에는 캠페인 관리자 또는 워크플로우 감독자와 같은 기본 제공 연산자 그룹이 포함되어 있습니다. [이 섹션](../start/gs-permissions.md)에서 사용 권한에 대해 자세히 알아보기

연산자 그룹의 구성원인 사용자는 &#39;명명된 권한&#39;이라는 작업을 수행할 수 있는 권한이 있으며 **Explorer** 보기의 폴더에 포함된 데이터에 액세스할 수 있습니다. 연산자는 여러 연산자 그룹의 멤버일 수 있습니다. 권한 및 액세스 권한은 가산됩니다.

명명된 권한 부여 대상:

* 작업 수행
예를 들어, 배달 편집기의 **분석** 단추가 **배달 준비** 이름이 오른쪽에 있는 **배달 연산자** 그룹의 구성원에 대해 활성화됩니다

* 폴더 액세스
운영자 그룹의 멤버십은 폴더에 대한 보안 설정을 변경하여 폴더에 대한 액세스 권한을 부여하거나 제한할 수 있습니다. 자세한 내용은 [이 페이지](../start/folder-permissions.md)를 참조하세요. 예를 들어 다음 항목에 영향을 줄 수 있습니다. **쓰기 액세스**(게재, 프로필 등), **읽기 액세스**(엔터티 사용), **액세스 삭제**(엔터티 삭제).

## 보안 영역

각 연산자는 영역에 연결되어 인스턴스에 로그온해야 하며 연산자 IP는 보안 영역에 정의된 주소 또는 주소 집합에 포함되어야 합니다. 보안 영역 구성은 Adobe Campaign 서버의 구성 파일에서 수행됩니다.

연산자가 콘솔의 프로필에서 보안 영역에 연결되어 **[!UICONTROL Administration > Access management > Operators]** 노드에서 액세스할 수 있습니다.

>[!NOTE]
>
>관리 Cloud Service 사용자는 Adobe이 보안 영역을 설정합니다. 자세한 내용은 [Adobe 문의](https://helpx.adobe.com/kr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}하세요.

**자세히 알아보기**

* [기본 제공 명명된 권한](../start/gs-permissions.md)

* [권한 설정 단계](../start/manage-permissions.md)
