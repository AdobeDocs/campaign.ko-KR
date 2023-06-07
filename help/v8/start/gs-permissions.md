---
title: Campaign v8에서 권한 시작
description: Campaign v8에서 권한을 정의하는 단계 알아보기
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 290f4e9a0d13ef49caacb7a128ccc266bafd5e69
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 2%

---

# 사용 권한 시작{#gs-permissions}

Adobe Campaign을 사용하면 사용자에게 할당된 권한을 정의하고 관리할 수 있습니다. 다음은 권한을 부여하거나 거부한 권한 및 제한 세트입니다.

* 특정 기능에 액세스
* 특정 데이터 액세스
* 특정 작업(만들기, 수정, 삭제)에 대한 액세스

이러한 권한은 명명된 권한 및 폴더에 대한 권한을 연산자 그룹 권한으로 결합하여 정의됩니다.

Adobe Campaign에서 사용자는 **연산자** 및 **연산자 그룹** 사용자 역할을 나타냅니다. 운영자는 로그인하고 작업을 수행할 수 있는 권한이 있는 Adobe Campaign 사용자입니다. 사용자는 Admin Console에서 생성됩니다. 권한은 사용자 프로필 또는 사용자 그룹에 적용됩니다. 부여할 수 있는 권한은 두 가지 유형이 있습니다.

* 권한을 지정할 연산자 그룹을 정의한 다음 연산자를 하나 이상의 그룹과 연결할 수 있습니다. 이렇게 하면 권한을 재사용하고 운영자 프로필을 보다 일관되게 만들 수 있습니다. 또한 사용자 프로필의 관리 및 유지 관리를 용이하게 합니다.
* 명명된 권한을 사용자에게 직접 할당할 수 있으며, 경우에 따라 그룹을 통해 할당된 권한을 오버로드할 수 있습니다.

## 권한을 부여하는 주요 단계{#key-steps-permissions}

제품 관리자는 조직의 사용자에게 권한을 부여할 수 있습니다. 권한은 Adobe Admin Console 및 Campaign 클라이언트 콘솔을 통해 부여됩니다. 사용자가 Adobe ID으로 Adobe Campaign에 로그온합니다. 에서 Adobe Campaign에 연결하는 방법 알아보기 [이 페이지](connect.md).

주요 단계:

* **1단계**: 운영자 그룹을 정의하고 Campaign 클라이언트 콘솔에서 권한을 할당합니다. [자세히 알아보기](manage-permissions.md#create-product-profile).
기본 제공 연산자 그룹을 사용하여 를 시작할 수도 있습니다. 이러한 기본 그룹과 해당 권한은 [이 섹션](manage-permissions.md#ootb-productprofiles).
* **2단계**: Admin Console에서 해당 그룹과 일치하는 제품 프로필을 만듭니다. [자세히 알아보기](manage-permissions.md#create-product-profile).
기본 제공 제품 프로필을 사용하여 시작할 수 있습니다. [자세히 알아보기](manage-permissions.md#ootb-productprofiles)
* **3단계**: Admin Console에서 사용자를 만들고 제품 프로필에 할당합니다. [자세히 알아보기](manage-permissions.md#add-users)
* **4단계** (선택 사항): 폴더에 권한을 할당합니다. [자세히 알아보기](manage-permissions.md#ootb-productprofiles)

## Admin Console 정보{#gs-admin-console}

Adobe Admin Console은 조직 전체에서 Adobe 권한을 관리하기 위한 중앙 위치입니다. 제품 관리자만 액세스할 수 있습니다.

Admin Console을 사용하여 사용자를 추가하고, 제품 프로필(운영자 역할 그룹)을 만들고, 할당합니다.

에서 사용자를 추가하는 방법 알아보기 [이 페이지](manage-permissions.md#add-users).

## 제품 프로필 기본 정보{#ootb-product-profiles}

제품 프로필은 사용자에게 할당할 수 있는 제품 및 서비스 그룹입니다. Adobe Experience Cloud에서 권한은 사용자가 아닌 제품 프로필을 기반으로 합니다. 그러나 특정 사용자에게 관리 권한을 위임할 수 있습니다.

Admin Console에서 각 Adobe Experience Cloud **제품 프로필** for Campaign이 다음에 연결되었습니다. **운영자 그룹** Campaign 클라이언트 콘솔에 있습니다.

에서 제품 프로필을 만들고 할당하는 방법을 알아봅니다. [이 페이지](manage-permissions.md#create-a-product-profile).

## 캠페인 명명된 권한{#named-rights}

제품 프로필(즉, 운영자 그룹)의 멤버인 사용자는 &#39;명명된 권한&#39;이라고 하는 작업을 수행할 수 있는 권한이 있으며 데이터에 대한 읽기 및/또는 쓰기 액세스 권한이 있습니다. 연산자는 여러 연산자 그룹의 멤버일 수 있습니다. 권한 및 액세스 권한은 가산됩니다.

에서 명명된 권한에 대해 자세히 알아보기 [이 섹션](manage-permissions.md#use-named-rights).
