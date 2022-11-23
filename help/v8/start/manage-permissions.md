---
title: Campaign v8에 권한 부여
description: Campaign v8 사용자에게 권한을 부여하는 방법을 알아봅니다
feature: Permissions
role: User, Admin
level: Beginner
source-git-commit: b63dc1616bc7ce1387a7bd0590c289b59f11b33f
workflow-type: tm+mt
source-wordcount: '1640'
ht-degree: 1%

---

# 사용자 권한 관리{#manage-permissions}

## 사용자 추가 {#add-users}

제품 관리자는 사용자를 추가하고 Campaign에 대한 액세스 권한을 부여할 수 있습니다.

사용자를 추가하려면 아래 단계를 따르십시오.

1. 에서 [Admin Console](https://adminconsole.adobe.com/enterprise){target=&quot;_blank&quot;} 홈 페이지에서 다음을 선택합니다. **사용자 추가**.

   ![](assets/add-a-user.png)

1. 사용자의 이메일 주소를 입력합니다.
1. 사용자에게 할당할 제품 프로필 또는 사용자 그룹을 선택하려면 &#39;+&#39; 기호를 사용하십시오.

   ![](assets/add-a-product-profile.png)

   Campaign 기본 제공 제품 프로필은 [이 섹션](#ootb-productprofiles).

   에서 사용자 그룹을 만드는 방법을 알아봅니다. [이 섹션](#user-groups)

1. 클릭 **저장**. 사용자가 추가되고 사용자 목록에 표시됩니다. 사용자에게 관리자 역할 또는 제품 프로필을 할당하면 사용자에게 이메일 알림이 전송됩니다. 사용자는 링크를 따라 프로필을 완료해야 합니다.

의 Admin Console에서 사용자 만들기에 대해 자세히 알아보십시오 [이 페이지](https://helpx.adobe.com/ie/enterprise/using/manage-users-individually.html){target=&quot;_blank&quot;}.

새 사용자가 [campaign에 로그온](connect.md) Adobe ID을 사용하면 클라이언트 콘솔의 Campaign 연산자 목록에 추가됩니다. Campaign 연산자는 **[!UICONTROL Administration > Access management > Operators]** 캠페인 탐색기의 폴더.

## 제품 프로필 작업{#product-profiles}

제품 프로필을 사용하여 제품에 포함된 기능을 사용자에게 부여할 수 있습니다.

* Admin Console의 각 제품에 대해 하나 이상의 제품 프로필을 만들 수 있습니다.
* 각 제품 프로필에서는 사용자 및 사용자 그룹(조직의)을 지정합니다.
* 사용자가 제품 프로필에 지정된 자격 증명으로 로그인하면 제품 프로필이 기반으로 하는 제품의 앱 및 서비스에 대한 액세스 권한을 받습니다.

이러한 제품 프로필은 **[!UICONTROL Administration > Access management > Operator groups]** 캠페인 탐색기의 폴더.

Admin Console에서 제품 프로필은 다음 구문을 사용합니다.

campaign - `<your instance>` - 운영자 그룹의 내부 이름

예를 들어 **게재 연산자** &#39;test&#39; 인스턴스의 Admin Console 그룹에는의 제품 프로필이

campaign - 테스트 - 게재

기본 제품 프로필을 사용하거나 새 제품 프로필을 만들 수 있습니다.

### 제품 프로필 만들기{#create-product-profile}

새 제품 프로필을 Adobe에 추가하려면 먼저 Campaign 클라이언트 콘솔에서 만든 다음 Admin Console에 추가해야 합니다.

예를 들어 &#39;검토자&#39; 제품 프로필을 만들려면 아래 단계를 수행하십시오.

#### Campaign에서 운영자 그룹 만들기{#create-op-group}

1. Campaign에 연결하고 탐색기를 열고 **[!UICONTROL Administration > Access management > Operator groups]**.
1. 클릭 **[!UICONTROL New]**를 클릭하고 연산자 그룹의 이름을 정의하고 내부 이름(&#39;검토자&#39;)을 설정합니다.
   ![](assets/new-op-group.png)
1. 명명된 권한을 선택하여 연결된 권한을 정의합니다. 명명된 권한은 [이 섹션](#use-named-rights)
1. 새 연산자 그룹을 저장합니다.

#### Admin Console에서 제품 프로필 만들기{#create-profile-in-admin-console}

1. 에 연결 [Admin Console](https://adminconsole.adobe.com/enterprise){target=&quot;_blank&quot;}.
1. 에서 **제품 및 서비스** 섹션에서 Campaign 제품을 엽니다.
1. 클릭 **새 프로필** 및에 작성할 제품 프로필의 이름을 입력하고, 설명된 대로 정확한 구문을 사용합니다 [여기](#product-profiles). 이 예제에서는 다음을 입력합니다. campaign - `<your-instance-name>` - 검토자

   ![](assets/new-product-profile-ui.png)

1. 변경 내용을 저장합니다.

이제 다음에 설명된 대로 이 새 제품 프로필에 사용자를 추가할 수 있습니다. [이 섹션](#add-users).

우수 사례는 제품 프로필을 사용자 그룹에 할당하는 것입니다. 사용자별 권한 관리는 지속 가능한 모델이 아닙니다.


### 기본 제품 프로필 및 운영자 그룹 {#ootb-productprofiles}

Adobe Campaign에는 기본 제공 **제품 프로필** Adobe이 환경을 활성화하면 정의됩니다.

![](assets/ootb-product-profiles.png)

이러한 제품 프로필은 Campaign과 일치합니다 **연산자 그룹**. 기본 연산자 그룹 및 해당 [명명된 권한](#use-named-rights) 아래에 나열된 항목은 다음과 같습니다.

1. **[!UICONTROL Administrator]** (관리자)

   이 그룹의 연산자는 인스턴스에 대한 전체 액세스 권한을 갖습니다. 관리자는 사용자 인터페이스의 가장 기술적인 부분에 액세스할 수 있는 사용자입니다.

   이 그룹에는 이름이 지정된 다음 권한이 포함되어 있습니다.

   * **[!UICONTROL ADMINISTRATION]**: 워크플로우, 게재, 스크립트 등과 같은 모든 객체를 실행/생성/편집/삭제할 수 있는 권한.

1. **[!UICONTROL Delivery operators]** (배달)

   이 그룹의 연산자는 게재 관리를 담당합니다. 게재를 만들고 준비하는 데 필요한 기본 리소스(캠페인 유형화, 게재 매핑, 기본 템플릿, 개인화 블록 등)에 액세스할 수 있습니다.

   이 그룹에는 다음과 같은 명명된 권한이 포함되어 있습니다.

   * **[!UICONTROL PREPARE DELIVERIES]**: 게재 분석을 만들고, 편집하고, 시작할 수 있는 권한
   * **[!UICONTROL START DELIVERIES]**: 이전에 분석한 게재를 승인할 수 있는 권한.

1. **[!UICONTROL Campaign managers]** (작업)

   이 그룹의 운영자는 마케팅 캠페인을 관리할 수 있습니다. 캠페인(계획, 프로그램, 워크플로우, 예산 등)에 연결된 객체에 액세스할 수 있습니다. 의 프레임워크 내에서 **[!UICONTROL Campaign]** (선택적 Adobe Campaign 모듈).

   이 그룹에는 다음과 같은 명명된 권한이 포함되어 있습니다.

   * **[!UICONTROL INSERT FOLDERS]**: Adobe Campaign 트리에 폴더를 삽입할 수 있는 권한(관련 분기에 대한 편집 권한이 있는 경우),
   * **[!UICONTROL WORKFLOW]**: 워크플로우를 사용할 수 있는 권한.

   >[!NOTE]
   >
   >이 그룹에서는 연산자가 게재를 시작할 수 없습니다.

1. **[!UICONTROL Content contributors]** (컨텐츠)

   이 그룹의 사용자는 **[!UICONTROL Content management]** 추가 기능. 이 그룹은 추가 권한을 부여하지 않습니다.

1. **[!UICONTROL Access to reports]** (보고서)

   이 그룹은 외부 운영자를 위해 예약되어, [웹 액세스](../start/campaign-ui.md#web-browser).

1. **[!UICONTROL Workflow execution]** (워크플로우)

   다음 **[!UICONTROL Workflow execution]** 그룹 을 사용하면 타깃팅 워크플로우의 실행 및 승인을 제어할 수 있습니다. 오른쪽 워크플로우가 이 그룹의 연산자에 매핑됩니다. 데이터 파일에 대한 액세스 권한 외에 워크플로우의 모든 작업에 필요합니다. 기본적으로 **[!UICONTROL Workflow execution]** 그룹에는 표준 타겟팅 워크플로우 파일 및 워크플로우 템플릿에 대한 읽기 전용 액세스 권한이 있습니다. 이 그룹의 연산자도 보류 중인 승인 파일에 대한 읽기 및 쓰기 액세스 권한도 갖습니다.

1. **[!UICONTROL Workflow supervisors]** (workflowSupervisor)

   이 그룹의 사용자는 워크플로우 승인을 관리하고 캠페인 워크플로우와 관련된 경고가 발생한 경우 이메일 알림을 받습니다.

1. **로컬 / 중앙 관리** (중앙/로컬)

   이 그룹의 사용자는 **[!UICONTROL Distributed marketing]** 추가 기능.

1. **[!UICONTROL Offer managers]** (오퍼)

   이 그룹의 연산자는 상호 작용 추가 기능을 사용할 때 오퍼를 만들고 유지 관리할 수 있습니다. [자세히 알아보기](../interaction/interaction-operators.md)

   이 그룹에는 다음과 같은 명명된 권한이 포함되어 있습니다.

   * **[!UICONTROL INSERT FOLDERS]**: Adobe Campaign 트리에 폴더를 삽입할 수 있는 권한(관련 분기에 대한 편집 권한이 있는 경우),
   * **[!UICONTROL EDIT FOLDERS]**: 내부 이름, 레이블, 연결된 이미지, 하위 폴더 순서 등과 같은 폴더 속성을 변경할 수 있는 권한.

   오퍼 관리자에 할당된 권한을 사용하여 다음 작업을 수행할 수 있습니다.

   * 수정 **[!UICONTROL Design]** 환경.
   * 보기 **[!UICONTROL Live]** 환경.
   * 관리 함수(사전 정의된 공간 및 필터)를 구성합니다.
   * 카테고리를 만들고 업데이트합니다.
   * 오퍼 만들기.
   * 오퍼 자격 을 구성합니다.
   * 오퍼를 승인합니다.

   >[!NOTE]
   >
   >**오퍼 관리자** 검토자가 지정되지 않았거나 오퍼 템플릿에서 검토자로 설정된 경우에만 오퍼를 승인할 수 있습니다.

   환경별 오퍼 관리자 권한 매트릭스는 [이 페이지](../interaction/interaction-operators.md#recap-of-rights-according-to-operator).

## 사용자 그룹 작업{#user-groups}

Admin Console을 사용하여 사용자 그룹을 만들고 사용자를 해당 그룹에 지정할 수 있습니다.

사용자 그룹은 공유 권한 집합을 지정해야 하는 다양한 사용자의 컬렉션입니다. 에서 사용자 그룹을 만드는 방법을 알아봅니다. [이 섹션](https://helpx.adobe.com/ie/enterprise/using/user-groups.html){target=&quot;_blank&quot;}.

제품 프로필을 사용자 그룹에 할당할 수 있습니다. 따라서 해당 그룹의 모든 사용자는 동일한 제품 권한 세트를 받게 됩니다.

## 명명된 권한{#use-named-rights}

Adobe Campaign에는 사용자 및 사용자 그룹에 할당된 권한을 정의할 수 있는 명명된 권한 세트가 포함되어 있습니다. 이러한 권한은 **[!UICONTROL Administration > Access management > Named rights]** 캠페인 탐색기의 폴더.

명명된 권한 부여 권한:

* 작업 수행 예: **분석** 게재 편집기의 버튼이 **배달 연산자** 가지고 있는 그룹 **게재 준비** 명명된 오른쪽

* 폴더 액세스 운영자 그룹의 멤버십은 폴더의 보안 설정을 변경하여 폴더에 대한 액세스 권한을 부여하거나 제한할 수 있습니다. [자세히 알아보기](folder-permissions.md#restrict-access-to-a-folder)

   예를 들어 영향을 줄 수 있습니다. **쓰기 액세스** 새 개체(예: 게재, 프로필 등)를 만들려면 다음을 수행하십시오. **읽기 액세스** 엔티티를 사용하려면 **액세스 삭제** 엔티티를 삭제하려면 다음을 수행하십시오.

Adobe Campaign에서 이름이 지정된 기본 권한은 다음과 같습니다.

* **[!UICONTROL ADMINISTRATION]**: 연산자가 **[!UICONTROL ADMINISTRATION]** 인스턴스에 대한 전체 액세스 권한이 있습니다. 관리자 사용자는 워크플로우, 전달, 스크립트 등과 같은 개체를 실행/생성/편집/삭제할 수 있습니다.

* **[!UICONTROL APPROVAL ADMINISTRATION]**: 워크플로우 및 게재 내에서 여러 승인 단계를 설정하여 현재 상태가 지정된 운영자 또는 그룹에 의해 승인되었는지 확인할 수 있습니다. 을 사용하는 사용자 **[!UICONTROL APPROVAL ADMINISTRATION]** 권한 은 승인 단계를 설정하고 해당 단계를 승인해야 하는 운영자 또는 운영자 그룹을 지정할 수도 있습니다.

* **[!UICONTROL CENTRAL]**: 중앙 관리 권한(분산 마케팅).

* **[!UICONTROL DELETE FOLDER]**: 폴더를 삭제할 수 있는 권한. 이 권한을 사용하면 사용자가 탐색기 보기에서 폴더를 삭제할 수 있습니다.

* **[!UICONTROL EDIT FOLDERS]**: 내부 이름, 레이블, 연결된 이미지, 하위 폴더 순서 등과 같은 폴더 속성을 변경할 수 있는 권한.

* **[!UICONTROL EXPORT]**: 사용자는 Adobe Campaign 인스턴스의 데이터를 **[!UICONTROL EXPORT]** 워크플로우 활동.

* **[!UICONTROL FILES ACCESS]**: 에서 작성할 수 있는 스크립트를 통해 파일에 대한 읽기 및 쓰기 액세스 권한 **[!UICONTROL JavaScript]** 서버에서 파일을 읽기/쓰기 위한 워크플로우 활동.

* **[!UICONTROL IMPORT]**: 일반 데이터 가져오기에 대한 권한. **[!UICONTROL IMPORT]** 데이터를 다른 테이블로 가져올 수 있지만 **[!UICONTROL RECIPIENT IMPORT]** 오른쪽에서는 수신자 테이블로만 가져올 수 있습니다.

* **[!UICONTROL INSERT FOLDERS]**: 폴더를 삽입할 수 있는 권한. 을 사용하는 사용자 **[!UICONTROL INSERT FOLDERS]** 탐색기 보기의 폴더 트리에서 새 폴더를 만들 수 있습니다.

* **[!UICONTROL LOCAL]**: 로컬 관리 권한(분산 마케팅).

* **[!UICONTROL MERGE]**: 선택한 레코드를 하나로 병합할 수 있는 권한. 수신자가 중복으로 존재하는 경우 **[!UICONTROL MERGE]** 마우스 오른쪽 단추를 사용하면 사용자가 중복을 선택하고 기본 수신자로 병합할 수 있습니다.

* **[!UICONTROL PREPARE DELIVERIES]**: 게재 생성, 편집 및 저장 권한. 을 사용하는 사용자 **[!UICONTROL PREPARE DELIVERIES]** 게재 분석 프로세스를 시작할 수도 있습니다.

* **[!UICONTROL PRIVACY DATA RIGHT]**: 개인 정보 데이터를 수집 및 삭제할 권한. [자세히 알아보기](privacy.md)

* **[!UICONTROL PROGRAM EXECUTION]**: 다양한 프로그래밍 언어로 명령을 실행할 수 있는 권한.

* **[!UICONTROL RECIPIENT IMPORT]**: 수신자를 가져올 수 있는 권한. 을 사용하는 사용자 **[!UICONTROL RECIPIENT IMPORT]** 로컬 파일을 수신자 테이블로 가져올 수 있는 권한이 있습니다.

* **[!UICONTROL SQL SCRIPT EXECUTION]** 데이터베이스에서 직접 SQL 명령을 실행할 수 있는 권한.

* **[!UICONTROL START DELIVERIES]**: 이전에 분석한 게재를 승인할 수 있는 권한. 게재 분석 후, 게재는 다양한 승인 단계에서 일시 중지되며 재개하려면 승인을 받아야 합니다. 을 사용하는 사용자 **[!UICONTROL START DELIVERIES]** 게재 승인 권한이 허용됩니다.

* **[!UICONTROL USE SQL DATA MANAGEMENT ACTIVITY]**: 작업 테이블을 만들고 채우기 위해 SQL 데이터 관리 활동을 사용하여 고유한 SQL 스크립트를 작성할 수 있는 권한. [자세히 알아보기](../../automation/workflow/sql-data-management.md)

* **[!UICONTROL WORKFLOW]**: 워크플로우에만 이름이 지정된 권한입니다. 워크플로우를 만들고, 시작하고, 중지할 수 있습니다. 명명된 권한을 적용할 수 있으려면 워크플로우 파일에 대한 읽기 권한이 필요합니다. 워크플로우 타겟팅의 경우 **[!UICONTROL Profiles and Targets]** 폴더는 필수입니다.


* **[!UICONTROL WEBAPP]**: 웹 응용 프로그램을 사용할 수 있는 권한.

>[!NOTE]
>
>이 목록은 환경에 설치된 추가 기능에 따라 다를 수 있습니다.



## 추가 리소스{#additional-res}

* [워크플로우에 대한 권한 관리](../../automation/workflow/managing-rights.md)
* [분산 마케팅에 대한 권한 관리](../../automation/distributed-marketing/about-distributed-marketing.md#operators)
* [상호 작용 모듈에 대한 권한 관리](../interaction/interaction-operators.md)
* [스키마에 대한 액세스 필터링](../dev/filter-schema.md)
* [PI 보기 제한](../dev/restrict-pi-view.md)
