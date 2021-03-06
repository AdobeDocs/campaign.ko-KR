---
title: Campaign에서 프로필 가져오기
description: Campaign에서 연락처를 가져오는 방법을 알아봅니다
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
source-git-commit: 59046a11c3e057cf41c322f190a9d8aef310c356
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 11%

---

# 파일에서 프로필 가져오기{#create-profiles}

Campaign 데이터베이스를 채우려면 다음을 수행할 수 있습니다 [수동으로 프로필 추가](create-profiles.md) 또는 아래에 자세히 설명된 대로 프로필을 가져옵니다. 가져온 파일을 사용하여 연락처 데이터를 업데이트할 수도 있습니다.

## 워크플로우로 프로필 가져오기 {#import-profiles-with-a-wf}

워크플로우는 일부 가져오기 프로세스를 자동화하는 유용한 방법이 될 수 있습니다. 로컬 파일 또는 SFTP에서 데이터를 가져오든 관계없이 워크플로우를 사용하여 데이터 관리 절차를 표준화할 수 있습니다.

### 목록의 데이터 사용: 목록 읽기 {#data-from-read-list}

워크플로우로 가져올 수 있도록 파일에서 데이터를 준비하여 구조화합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html)

### 파일에서 데이터 로드 {#data-from-a-file}

워크플로우에서 처리된 데이터를 구조화된 파일에서 추출하여 Adobe Campaign으로 가져올 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html)

데이터가 수집되면 워크플로우에서 사용할 수 있습니다. 예를 들어 게재를 보강하거나 데이터베이스를 업데이트하는 등의 작업을 할 수 있습니다. 이 작업에 대한 자세한 정보는 [이 섹션](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html)을 참조하십시오.

## 일회성 가져오기{#import-jobs}

Adobe Campaign에서는 대상 모집단의 일부가 될 고객 또는 잠재 고객 목록을 추출하거나 외부 파일의 데이터를 데이터베이스에 제공할 수 있는 범용 가져오기 기능을 제공합니다.

일반 가져오기는 **[!UICONTROL Profiles and Targets > Jobs]** Adobe Campaign 홈 페이지의 메뉴.

![](assets/new-import-job.png)

일반 가져오기를 수행하는 단계는 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=ko){target=&quot;_blank&quot;}.
