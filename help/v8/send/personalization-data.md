---
title: Personalization 데이터 소스
description: 개인화에 사용할 수 있는 소스 알아보기
feature: Personalization
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 711256e2-ab77-404a-b052-6793a85da193
source-git-commit: 25ee55d5327e0ba7f2192f7b462853269c8cbf46
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%

---

# Personalization 데이터 소스{#personalization-data}

Personalization 데이터는 Campaign 데이터베이스 데이터 소스, 외부 파일 데이터 소스 또는 외부 데이터베이스 데이터 소스 등 다양한 유형의 소스에서 검색할 수 있습니다.

## Campaign 데이터베이스 데이터 소스

가장 일반적인 경우 개인화 데이터가 데이터베이스에 저장됩니다. 예를 들어 &#39;수신자 개인화 필드&#39;는 수신자 테이블, 표준 필드(일반적으로 성, 이름, 주소, 도시, 생년월일 등) 또는 사용자 정의 필드에 정의된 모든 필드입니다.

![전자 메일의 Campaign 개인화 필드](assets/perso-campaign-datasource.png)


## 외부 파일 데이터 소스

열에 정의된 모든 필드가 포함된 외부 파일을 사용할 수 있습니다. 이 파일은 메시지 게재를 정의하는 동안 입력으로 사용됩니다. 이러한 프로파일을 데이터베이스에 삽입할지 여부를 선택할 수 있습니다.

데이터 원본으로 사용할 파일을 선택하려면 메시지 만들기 창에서 받는 사람 링크로 이동하여 **외부 파일에 정의됨** 옵션을 선택하십시오. 파일이 로드되면 **파일의 필드** 항목의 개인화 옵션에서 받는 사람 데이터에 액세스합니다.

![파일의 Personalization 데이터](assets/perso-from-file.png)


## FDA 데이터 소스

[페더레이션 데이터 액세스](../connect/fda.md)를 통해 외부 테이블에서 Personalization 데이터를 가져올 수 있습니다.  외부 데이터베이스의 데이터를 사용하여 게재에서 개인화를 수행하려면 워크플로우에서 사용할 데이터를 수집하여 임시 테이블에서 사용할 수 있도록 하십시오.

이렇게 하려면 타깃팅 워크플로우에서 **쿼리** 활동을 추가하고 **데이터 추가...** 링크를 사용하여 외부 데이터베이스를 선택하십시오. 자세한 프로세스는 [이 섹션](../../automation/workflow/query.md#adding-data)에서 확인할 수 있습니다.

그런 다음 임시 테이블의 데이터를 사용하여 게재를 개인화합니다. 쿼리 활동이 구성되면 **Target 확장** 항목에서 개인화 옵션의 외부 데이터에 액세스합니다.

![외부 데이터베이스의 Personalization 데이터](assets/perso-external-db.png)

FDA에서 액세스한 외부 데이터를 사용하는 경우 아래 설명된 대로 **워크플로우로 개인화 데이터 준비** 옵션을 사용하여 전용 워크플로우에서 메시지 개인화를 사전 처리하는 것이 좋습니다.

### 개인화 최적화 {#optimize-personalization}

게재 속성의 **[!UICONTROL Prepare the personalization data with a workflow]** 탭에서 사용할 수 있는 전용 옵션 **[!UICONTROL Analysis]**&#x200B;을(를) 사용하여 개인화를 최적화할 수 있습니다.

게재 분석 중에 이 옵션은 FDA에 연결된 테이블의 데이터를 포함하여 대상에 연결된 모든 데이터를 임시 테이블에 저장하는 워크플로우를 자동으로 만들고 실행합니다.

이 옵션을 선택하면 많은 데이터를 처리 중인 경우, 특히 개인화 데이터가 FDA를 통해 외부 테이블에서 전송된 경우 게재 분석 성능을 크게 향상시킬 수 있습니다. [자세히 알아보기](../connect/fda.md)

이 옵션을 사용하려면 아래 단계를 따르십시오.

1. 캠페인을 만듭니다.
1. 캠페인의 **[!UICONTROL Targeting and workflows]** 탭에서 **쿼리** 활동을 워크플로우에 추가합니다.
1. 워크플로우에 **[!UICONTROL Email delivery]** 활동을 추가하고 엽니다.
1. **[!UICONTROL Analysis]**&#x200B;의 **[!UICONTROL Delivery properties]** 탭으로 이동하여 **[!UICONTROL Prepare the personalization data with a workflow]** 옵션을 선택합니다.
1. 게재를 구성하고 분석을 시작하도록 워크플로우를 시작합니다.

분석이 완료되면 개인화 데이터는 분석 중에 즉시 생성되는 임시 기술 워크플로우를 통해 임시 테이블에 저장됩니다.

이 워크플로우는 Adobe Campaign 인터페이스에 표시되지 않습니다. 이는 개인화 데이터를 빠르게 저장하고 처리하기 위한 기술적 수단으로만 제공됩니다.

분석이 완료되면 워크플로우 **[!UICONTROL Properties]**(으)로 이동하여 **[!UICONTROL Variables]** 탭을 선택합니다. 여기에 포함된 ID를 표시하기 위해 SQL 호출을 수행하는 데 사용할 수 있는 임시 테이블의 이름이 표시됩니다.

## 워크플로우의 Personalization 데이터

워크플로우 컨텍스트에서 게재를 만들 때 임시 워크플로우 테이블의 데이터를 사용할 수 있습니다. 워크플로우 임시 작업 테이블에 저장된 데이터는 개인화 작업에 사용할 수 있습니다. 개인화 필드에서 데이터를 사용할 수 있습니다.

이 데이터는 **[!UICONTROL Target extension]** 메뉴에 그룹화되어 있습니다. 자세한 정보는 [이 섹션](../../automation/workflow/use-workflow-data.md#target-data)을 참조하세요.
