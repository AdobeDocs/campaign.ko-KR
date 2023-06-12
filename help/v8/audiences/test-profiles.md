---
title: Campaign에서 테스트 프로필 만들기
description: Adobe Campaign에서 테스트 프로필을 만들고 관리하는 방법 알아보기
feature: Audiences, Profiles
role: User
level: Beginner
source-git-commit: 19c42bcd2a96173f3d33e3e259192107b5e64c6c
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 1%

---

# 테스트 프로필 만들기 및 관리 {#create-test-profiles}

## 시드 주소란? {#gs-seeds}

테스트 프로필은 시드 주소로 만들어집니다. 정의된 대상 기준과 일치하지 않는 수신자를 타겟팅하는 데 사용됩니다. 시드 주소를 사용하면 게재를 보내기 전에 증명을 보내 개인화 및 렌더링을 미리 보고 테스트할 수 있습니다.

시드 주소에는 다음과 같은 이점이 있습니다.

* 수신자 프로필에서 가져온 데이터로 필드를 임의로 대체: 시드 주소 섹션과 같은 이메일 주소만 입력하고 Campaign에서 프로필의 다른 필드를 자동으로 채울 수 있습니다. 자세히 알아보기: [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html?lang=en){target="_blank"}.
* Datamanagement 기능이 있는 워크플로우를 사용하는 경우 게재에서 처리된 추가 데이터를 시드 주소 수준에서 입력하여 값을 강제 적용할 수 있습니다. 이는 무작위 값 대체를 회피합니다.
* 시드 주소는 다음 게재 통계에 대한 보고서에서 자동으로 제외됩니다. **[!UICONTROL Clicks]**, **[!UICONTROL Opens]**, **[!UICONTROL Unsubscriptions]**.

시드 주소는 가져오거나 게재 또는 캠페인에서 직접 만들어 게재 대상에 추가됩니다.

>[!NOTE]
>
>시드 주소는 수신자 표에 만들어지지 않고 별도의 표에 만들어집니다. 새 데이터로 수신자 테이블을 확장하는 경우 동일한 데이터로 시드 주소 테이블을 확장해야 합니다. 그렇지 않으면 확장 필드는 시드 주소에 대해 고려되지 않습니다.
>
>다음은 시드 주소 테이블을 확장하는 방법의 예입니다 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html){target="_blank"}.



## 시드 주소 만들기

시드 주소는 표준 프로필 및 대상을 통해 관리되지 않고 Adobe Campaign 탐색기의 전용 노드에서 관리됩니다. **[!UICONTROL Resources > Campaign management > Seed addresses]**. 하위 폴더를 만들어 시드 주소를 구성할 수 있습니다.

또한 Adobe Campaign을 사용하면 게재 또는 캠페인으로 가져오고 관련 게재 및 캠페인의 특정 요구 사항에 따라 조정되는 시드 주소 템플릿을 만들 수 있습니다. 을(를) 참조하십시오 [시드 주소 템플릿 만들기](#creating-seed-address-templates).

### 주소 정의 {#defining-addresses}

시드 주소를 만들려면 다음 단계를 수행합니다.

1. 다음을 클릭합니다. **[!UICONTROL New]** 시드 주소 목록 위에 있는 단추입니다.
1. 해당 주소의 연결된 데이터를 **[!UICONTROL Recipient]** 탭. 사용 가능한 필드는 게재 수신자 프로필의 표준 필드(nms:recipient table)(이름, 이름, 이메일 등)에 해당합니다.

   >[!NOTE]
   >
   >주소의 레이블은 정의한 성과 이름으로 자동으로 채워집니다.
   >
   >시드 주소를 생성할 때 각 탭의 모든 필드를 입력할 필요는 없습니다. 누락된 개인화 요소는 게재 분석 중에 임의로 입력됩니다.

1. 다음에서 **[!UICONTROL Address fields]** 탭에서 분석 단계 중에 게재 로그에 삽입할 값을 **[!UICONTROL nms:broadLog]** 테이블.

1. 다음에서 **[!UICONTROL Additional data]** 탭에서 데이터 관리 워크플로우에서 만든 게재에 사용되고 특정 값을 지정할 개인화 데이터를 입력합니다.

   추가 대상 데이터가에서 &#39;@&#39;으로 시작하는 별칭으로 정의되었는지 확인하십시오. **[!UICONTROL Enrichment]** 워크플로우 활동. 그렇지 않으면 게재 활동에서 시드 주소와 함께 이 매개 변수를 제대로 사용할 수 없습니다.

### 시드 주소 템플릿 만들기 {#creating-seed-address-templates}

각 게재에 대해 가져오고 수정할 수 있는 주소 템플릿을 만들 수 있습니다. 프로세스는 새 시드 주소를 정의할 때와 동일합니다. 유일한 차이점은 시드 주소 템플릿 주소를 &#39;템플릿&#39; 유형 폴더에 저장해야 한다는 것입니다.

### DM 게재용 시드 주소 {#direct-mail-seed-addresses}

대상 [dm 게재](../send/direct-mail.md), 시드 주소는 추출 중에 추가되고 출력 문서에 혼합됩니다.

DM 게재의 경우 추출 파일 형식은 다음 제한 사항을 준수해야 합니다.

* 옵션을 사용하면 안 됩니다. **[!UICONTROL Handle groupings (GROUP BY+HAVING)]**.

* 요소 컬렉션이 추출되면 이 필드에는 다음과 같은 상황이 발생하지 않는 한 시드 주소에 대한 값이 비어 있습니다. **[!UICONTROL Single row (expert user)]** 옵션이 선택되어 있습니다.

## 게재에 시드 주소 추가{#seed-addresses-in-a-delivery}

게재할 특정 시드 주소를 추가하려면 **[!UICONTROL To]** 링크를 클릭한 다음 **[!UICONTROL Seed addresses]** 탭.

세 가지 가능한 삽입 모드가 있습니다.

1. 단일 시드 주소를 입력합니다.  이렇게 하려면 **[!UICONTROL Add]** 단추를 클릭하고 주소 필드의 내용을 정의합니다. 각 주소에 대해 이 작업을 반복합니다.

1. 가져오기 [시드 주소 템플릿](#creating-seed-address-template) 필요에 맞게 조정할 수 있습니다. 이렇게 하려면 **[!UICONTROL Import seed templates...]** 주소 템플릿이 들어 있는 폴더를 연결하고 선택합니다.

   필요한 경우 추가한 후 두 번 클릭하거나 **[!UICONTROL Detail...]** 단추를 클릭하여 각 주소의 콘텐츠를 조정합니다.

1. 삽입할 제어 주소를 동적으로 선택하는 조건을 만듭니다. 이렇게 하려면 **[!UICONTROL Edit the dynamic condition...]** 링크를 클릭한 다음 시드 주소 선택 매개 변수를 입력합니다. 예를 들어 특정 폴더에 포함된 모든 시드 주소 또는 조직의 특정 부서에 속한 시드 주소를 포함할 수 있습니다.

   이에 대한 예는 다음과 같습니다. [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html){target="_blank"}.

게재의 경우 추출 파일에 주소를 삽입하는 방법을 사용자 지정할 수도 있습니다. 기본적으로 출력 파일의 정렬 순서에 삽입되지만 파일의 끝이나 시작 부분에 삽입하거나 기본 대상의 수신자 중에 임의로 삽입하도록 선택할 수 있습니다.

## 캠페인에 시드 주소 추가 {#seed-addresses-in-a-campaign}

캠페인의 대상에 시드 주소를 추가하려면 작업을 선택하고 **[!UICONTROL Edit]** 탭.

다음을 클릭합니다. **[!UICONTROL Advanced campaign settings...]** 링크를 클릭한 다음 **[!UICONTROL Seed addresses]** 탭. 캠페인에서 삽입된 시드 주소는 캠페인의 각 게재 타겟에 추가됩니다.

## 시드 주소 및 사용자 지정 테이블 {#using-an-external-recipient-table}

게재 테이블이 외부 테이블인 경우 추가 구성을 수행해야 합니다. 다음 **[!UICONTROL nms:seedmember]** 스키마를 확장해야 합니다. 적절한 필드를 정의하기 위해 시드 주소에 탭이 추가됩니다

이 경우 게재에 시드 주소를 추가하려면 일치 탭에 직접 해당 필드를 입력하거나 주소 템플릿을 가져옵니다.

<!--The **nms:seedMember** schema extension is [this section](../../configuration/using/seed-addresses.md).-->

