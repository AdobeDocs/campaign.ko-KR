---
title: Campaign에서 프로필 가져오기
description: Campaign에서 연락처를 가져오는 방법 알아보기
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 9%

---

# 파일에서 프로필 가져오기{#create-profiles}

Campaign 데이터베이스를 채우려면 아래 설명된 대로 [프로필을 수동으로 추가](create-profiles.md)하거나 프로필을 가져올 수 있습니다. 가져온 파일을 사용하여 연락처 데이터를 업데이트할 수도 있습니다.

## 워크플로로 프로필 가져오기 {#import-profiles-with-a-wf}

워크플로우는 일부 가져오기 프로세스를 자동화하는 유용한 방법이 될 수 있습니다. 로컬 파일에서 데이터를 가져오든 SFTP에서 데이터를 가져오든 간에 워크플로우를 사용하여 데이터 관리 절차를 표준화할 수 있습니다.

### 목록의 데이터 사용: 목록 읽기 {#data-from-read-list}

워크플로우로 가져올 데이터를 파일에 준비하고 구성합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html?lang=ko){target="_blank"}.

### 파일에서 데이터 로드 {#data-from-a-file}

워크플로우에서 처리된 데이터는 Adobe Campaign으로 가져올 수 있도록 구조화된 파일에서 추출할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html?lang=ko){target="_blank"}.

데이터가 수집되면 워크플로우에서 사용할 수 있습니다. 예를 들어 게재를 보강하거나 데이터베이스를 업데이트할 수 있습니다. 이 작업에 대한 자세한 정보는 [이 섹션](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html?lang=ko){target="_blank"}을 참조하십시오.

## 일회성 가져오기{#import-jobs}

Adobe Campaign은 일반 가져오기 기능을 제공하여 예를 들어 대상 모집단의 일부가 될 고객 또는 잠재 고객 목록을 추출하거나 데이터베이스에 외부 파일의 데이터를 제공할 수 있습니다.

일반 가져오기는 Adobe Campaign 홈 페이지의 **[!UICONTROL Profiles and Targets > Jobs]** 메뉴에서 관리됩니다.

![](assets/new-import-job.png)

일반 가져오기를 수행하는 단계는 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=ko){target="_blank"}에 자세히 설명되어 있습니다.
