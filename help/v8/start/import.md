---
title: 프로필 시작
description: 프로필 시작
feature: Profiles
role: User
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: ht
source-wordcount: '228'
ht-degree: 100%

---

# 데이터를 Campaign으로 가져오기 {#ootb-profiles}

Campaign을 사용하면 Cloud 데이터베이스에 연락처를 추가할 수 있습니다. 파일을 불러오고, 여러 연락처 업데이트를 예약 및 자동화하고, 웹에서 데이터를 수집하거나, 수신자 표에 직접 프로필 정보를 입력할 수 있습니다.

![](../assets/do-not-localize/glass.png) [대상자](audiences.md) 시작

![](../assets/do-not-localize/glass.png) Campaign [데이터 모델](../dev/datamodel.md) 이해

## 워크플로우에서 프로필 가져오기

프로필 가져오기는 **가져오기** 활동을 통해 워크플로우를 통해 실행되는 전용 템플릿에서 구성됩니다. 일정에 따라 자동으로 반복될 수 있습니다. 예를 들어 여러 정보 시스템 간의 데이터 교환을 자동화할 수 있습니다. [이 섹션](../../automation/workflow/recurring-import-workflow.md)에서 자세히 알아봅니다.

![](assets/import-wf.png)


## 단일 가져오기 실행

일반 데이터 가져오기 작업을 만들고 실행하여 Cloud 데이터베이스에서 연락처를 불러들입니다.

![](assets/new-import.png)

![](../assets/do-not-localize/book.png) [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=ko){target="_blank"}에서 통합 가져오기 작업을 실행하여 데이터베이스에 데이터를 보충하는 방법을 알아봅니다.

## 웹 앱을 통해 프로필 수집

Campaign을 사용하여 웹 양식을 만들고 쉽고 효율적으로 프로필 정보를 수집 및 관리할 수 있습니다. 연락 대상이 해당 정보를 쉽게 제공할 수 있도록 이 양식을 웹 사이트에 공유할 수 있습니다. 해당 정보는 Campaign으로 전송하여 프로필을 만들거나, 데이터베이스에 이미 있는 경우 정보를 업데이트합니다.

![](assets/web-form-page.png)

![](../assets/do-not-localize/book.png) [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html?lang=ko){target="_blank"}에서 웹 폼을 만드는 방법을 알아봅니다.

**관련 항목**

* [대상자 만들기](audiences.md)
* [프로필 중복 제거](../../automation/workflow/deduplication-merge.md)
* [프로필 데이터 강화](../../automation/workflow/enrich-data.md)
