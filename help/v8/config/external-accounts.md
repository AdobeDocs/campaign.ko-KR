---
solution: Campaign Classic
product: campaign
title: 캠페인 외부 계정
description: 캠페인 외부 계정
feature: 개요
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 0e0cd6eb9fcf656c9ba6c72cd1a782098f9399fe
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 13%

---

# 외부 계정 구성

Adobe Campaign에는 미리 정의된 외부 계정 집합이 포함되어 있습니다. 외부 시스템과의 연결을 설정하려면 새 외부 계정을 만들 수 있습니다.

외부 계정은 기술 워크플로우 또는 캠페인 워크플로우와 같은 기술 프로세스에서 사용됩니다. 예를 들어 워크플로우에서 파일 전송을 설정하거나 다른 응용 프로그램(Adobe Target, Experience Manager 등)과 데이터 교환을 설정할 때 외부 계정을 선택해야 합니다.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/accessing-external-database/external-accounts.html)에서 외부 계정을 만들고 구성하는 방법에 대해 알아봅니다.

특정 외부 계정은 Campaign 로컬 데이터베이스와 클라우드 데이터베이스([!DNL Snowflake]) 간의 연결을 관리합니다.

:speech_bal풍선:관리 Cloud Services 사용자인 [!DNL Snowflake] 외부 계정은 Adobe으로 인스턴스용으로 구성됩니다.

이 외부 계정에 액세스하여 설정을 확인하고 복제 워크플로우를 실행할 수 있습니다. 이 작업을 수행하려면 아래 단계를 따르십시오.

1. 캠페인 **[!UICONTROL Explorer]**&#x200B;에서 **[!UICONTROL Administration > Platform > External Accounts]**&#x200B;을 클릭합니다.

1. **[!UICONTROL Full FDA]** 외부 계정을 선택합니다.

![](assets/snowflake-ext-account.png)

전역 설정이 **[!UICONTROL General tab]**&#x200B;에 표시됩니다.

**[!UICONTROL Parameters]** 탭과 **[!UICONTROL Deploy functions]** 버튼을 사용하여 함수를 만듭니다.

![](assets/snowflake-parameters.png)

**여기에 매개 변수 설명 추가**

복제 작업 과정을 강제 실행하려면 **[!UICONTROL Full FDA]** 탭을 사용합니다.

![](assets/snowflake-full-fda.png)

**여기에 세부 사항 추가**

