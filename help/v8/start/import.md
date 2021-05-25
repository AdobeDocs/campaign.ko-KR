---
solution: Campaign v8
product: Adobe Campaign
title: 프로필 시작
description: 프로필 시작
feature: 프로필
role: Data Engineer
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: 905003b74a1f875432f08c5c70edf3d0451b861f
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 0%

---

# 데이터를 Campaign {#ootb-profiles}에 가져오기

Campaign을 사용하면 Cloud 데이터베이스에 연락처를 추가할 수 있습니다. 파일을 로드하거나, 여러 연락처 업데이트를 예약 및 자동화하고, 웹에서 데이터를 수집하거나, 수신자 테이블에 직접 프로필 정보를 입력할 수 있습니다.

:[audiences](audiences.md) 시작
:Campaign [데이터 모델](../dev/datamodel.md) 이해

## 워크플로우에서 프로필 가져오기

프로필 가져오기는 **가져오기** 활동을 통해 워크플로우를 통해 실행되는 전용 템플릿에 구성됩니다. 예를 들어 일정에 따라 자동으로 반복될 수 있으므로 여러 정보 시스템 간의 데이터 교환을 자동화할 수 있습니다. 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/import-export-workflows.html)를 참조하십시오.

![](assets/import-wf.png)

자세한 내용은 Campaign Classic v7 설명서를 참조하십시오.

:arrow_upper_right:[가져오기 및 내보내기 시작](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/get-started-data-import-export.html)

:arrow_upper_right:[가져오기 및 내보내기 우수 사례](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/best-practices/import-export-best-practices.html)

:arrow_upper_right:[가져오기 구성 및 실행](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html)

## 단일 가져오기 실행

일반 데이터 가져오기 작업을 만들어 실행하여 클라우드 데이터베이스에 연락처를 로드합니다.

![](assets/new-import.png)

:arrow_upper_right:단일 가져오기 작업을 실행하여 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html)에서 데이터베이스를 제공하는 방법을 알아봅니다.

## 웹 앱을 통해 프로필 수집

Campaign을 사용하여 웹 양식을 만들고 쉽고 효율적으로 프로필 정보를 수집 및 관리할 수 있습니다. 이러한 양식을 웹 사이트에 공유할 수 있으므로 연락처가 해당 정보를 쉽게 제공할 수 있습니다. 해당 정보가 데이터베이스에 이미 있는 경우 프로필을 만들거나 정보를 업데이트하기 위해 Campaign으로 전송됩니다.

![](assets/web-form-page.png)

:arrow_upper_right:[Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html)에서 웹 양식을 만드는 방법을 알아봅니다.

**관련 항목**

* [대상자 만들기](audiences.md)
* [프로필 중복 제거](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/deduplication-merge.html)
* [프로필 데이터 보강](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html)
