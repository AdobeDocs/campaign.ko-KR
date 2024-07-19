---
title: 캠페인 상호 작용 오퍼 공간
description: 오퍼 공간을 만드는 방법 알아보기
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: c116d86a-d3e2-47e3-a641-e2d7c8cc575c
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 1%

---

# 오퍼 공간 만들기{#creating-offer-spaces}

오퍼 카탈로그의 콘텐츠는 오퍼 공간에 구성됩니다. 기본적으로 콘텐츠에는 **[!UICONTROL Title]**, **[!UICONTROL Destination URL]**, **[!UICONTROL Image URL]**, **[!UICONTROL HTML content]** 및 **[!UICONTROL Text content]** 필드가 포함될 수 있습니다. 오퍼 공간에 필드 시퀀스가 구성되어 있습니다.

**기술 관리자**&#x200B;로서 디자인 환경에서 오퍼 공간을 만들 수 있습니다. 오퍼 공간 하위 폴더에 대한 액세스 권한이 있어야 합니다. 이러한 오퍼 공간이 만들어지면 오퍼 승인 중에 라이브 환경에 자동으로 복제됩니다.

HTML 렌더링은 렌더링 함수를 통해 생성됩니다. 렌더링 함수에 정의된 필드의 시퀀스는 콘텐츠에 구성된 시퀀스와 동일해야 합니다.

![](assets/offer_space_create_009.png)

새 오퍼 공간을 만들려면 아래 단계를 수행하십시오.

1. 오퍼 공간 목록에서 **[!UICONTROL New]**&#x200B;을(를) 클릭합니다.

   ![](assets/offer_space_create_001.png)

1. 사용할 채널을 선택하고 오퍼 공간의 레이블을 변경합니다.

   ![](assets/offer_space_create_002.png)

1. **[!UICONTROL Enable unitary mode]** 옵션 확인

1. **[!UICONTROL Content field]** 창으로 이동하여 **[!UICONTROL Add]**&#x200B;을(를) 클릭합니다.

   ![](assets/offer_space_create_003.png)

1. **[!UICONTROL Content]** 노드로 이동하여 **[!UICONTROL Title]**, **[!UICONTROL Image URL]**, **[!UICONTROL HTML content]**, **[!UICONTROL Destination URL]** 순서로 필드를 선택합니다.

   ![](assets/offer_space_create_004.png)

1. 각 필드를 필수 항목으로 만들려면 **[!UICONTROL Required]** 옵션을 선택하십시오.

   >[!NOTE]
   >
   >이 옵션은 미리보기에서 사용되며 필수 필드 중 하나가 오퍼에서 누락된 경우 게시할 때 오퍼 공백을 유효하지 않게 합니다. 그러나 오퍼가 이미 오퍼 공간에 있는 경우 이러한 기준은 고려되지 않습니다.

   ![](assets/offer_space_create_005.png)

1. 렌더링 함수를 만들려면 **[!UICONTROL Edit functions]**&#x200B;을(를) 클릭하십시오.

   이러한 함수는 오퍼 공간에서 오퍼 표시를 생성하는 데 사용됩니다. 가능한 형식은 HTML 또는 텍스트와 같이 몇 가지가 있습니다.

   **참고** - XML 형식은 이 버전의 제품에서 사용할 수 없는 인바운드 상호 작용으로 제한됩니다. [자세히 알아보기](../start/v7-to-v8.md#gs-unavailable-features)

   ![](assets/offer_space_create_006.png)_

1. **[!UICONTROL HTML rendering]** 탭으로 이동하여 **[!UICONTROL Overload the HTML rendering function]**&#x200B;을(를) 선택합니다.
1. 렌더링 함수를 삽입합니다.

   ![](assets/offer_space_create_007.png)

## 오퍼 제안 상태 {#offer-proposition-statuses}

오퍼 제안 상태는 타겟팅된 모집단과의 상호 작용에 따라 달라집니다. 캠페인 상호 작용 모듈은 라이프사이클 전체에서 오퍼 제안에 적용할 수 있는 값 세트와 함께 제공됩니다. 오퍼 제안을 만들고 수락할 때 상태가 변경되도록 플랫폼을 구성해야 합니다.

>[!NOTE]
>
>상태 업데이트가 **비동기** 프로세스입니다. 매시간 트리거되는 추적 워크플로우에 의해 수행됩니다.

### 오퍼 상태 목록 {#status-list}

사용 가능한 오퍼 상태는 다음과 같습니다.

* **[!UICONTROL Accepted]**
* **[!UICONTROL Scheduled]**
* **[!UICONTROL Generated]**
* **[!UICONTROL Interested]**
* **[!UICONTROL Presented]**
* **[!UICONTROL Rejected]**

이러한 값은 기본적으로 적용되지 않습니다. 구성해야 합니다.

>[!NOTE]
>
>오퍼가 &quot;전송됨&quot; 상태의 게재에 연결된 경우 오퍼 제안 상태가 자동으로 &quot;표시됨&quot;으로 변경됩니다.

### 제안 생성 시 오퍼 상태 {#configuring-the-status-when-the-proposition-is-created}

오퍼 제안이 **created**&#x200B;이면 해당 상태가 업데이트됩니다.

**[!UICONTROL Design]** 환경에서 각 오퍼 공간에 대해 오퍼 보고서에 표시할 정보에 따라 제안을 만들 때 적용할 상태를 구성합니다.

이렇게 하려면 아래 단계를 수행합니다.

1. 원하는 스페이스의 **[!UICONTROL Storage]** 탭으로 이동합니다.
1. 제안이 생성될 때 적용할 상태를 선택합니다.

   ![](assets/offer_update_status_001.png)

### 제안이 수락될 때의 오퍼 상태 {#configuring-the-status-when-the-proposition-is-accepted}

제안 제안이 **수락됨**&#x200B;되면 기본적으로 제공되는 값 중 하나를 사용하여 제안의 새 상태를 구성하십시오. 업데이트는 수신자가 오퍼에서 링크를 클릭하면 적용됩니다.

이렇게 하려면 아래 단계를 수행합니다.

1. 원하는 스페이스의 **[!UICONTROL Storage]** 탭으로 이동합니다.
1. 제안이 수락될 때 적용할 상태를 선택합니다.

   ![](assets/offer_update_status_002.png)


**인바운드 상호 작용**

**[!UICONTROL Storage]** 탭에서는 **제안** 및 **수락** 오퍼 제안에 대한 상태만 정의할 수 있습니다. 인바운드 상호 작용의 경우 인터페이스를 통해서가 아니라 오퍼 엔진을 호출하기 위한 URL에 오퍼 제안 상태를 직접 지정해야 합니다. 이렇게 하면 오퍼 제안이 거부되는 등의 다른 경우에 적용할 상태를 지정할 수 있습니다.

```
<BASE_URL>?a=UpdateStatus&p=<PRIMARY_KEY_OF_THE_PROPOSITION>&st=<NEW_STATUS_OF_THE_PROPOSITION>&r=<REDIRECT_URL>
```

예를 들어 **Neobank** 사이트에 표시된 **홈 보험** 오퍼와 일치하는 제안(식별자 **40004**)에는 다음 URL이 포함되어 있습니다.

```
<BASE_URL>?a=UpdateStatus&p=<40004>&st=<3>&r=<"http://www.neobank.com/insurance/subscribe.html">
```

방문자가 오퍼를 클릭하여 URL을 사용하는 즉시 **[!UICONTROL Accepted]** 상태(값 **3**)가 제안에 적용되고 방문자는 **Neobank** 사이트의 새 페이지로 리디렉션되어 보험 계약을 체결합니다.

>[!NOTE]
>
>URL에 다른 상태를 지정하려면(예: 오퍼 제안이 거부된 경우) 원하는 상태에 해당하는 값을 사용하십시오. 예: **[!UICONTROL Rejected]** = &quot;5&quot;, **[!UICONTROL Presented]** = &quot;1&quot; 등.
>
>상태 및 해당 값은 **[!UICONTROL Offer propositions (nms)]** 데이터 스키마에서 검색할 수 있습니다. 자세한 정보는 이 [페이지](../dev/create-schema.md)를 참조하십시오.

**아웃바운드 상호 작용**

게재에 링크가 포함된 경우 오퍼 제안에 **[!UICONTROL Interested]** 상태를 자동으로 적용할 수 있습니다. 링크에 **_urlType=&quot;11&quot;** 값을 추가하기만 하면 됩니다.

```
<a _urlType="11" href="<DEST_URL>">Link inserted into the delivery</a>
```

## 공간별 오퍼 미리보기 {#offer-preview-per-space}

**[!UICONTROL Preview]** 탭에서 선택한 방법을 통해 수신자에게 적합한 오퍼를 볼 수 있습니다. 아래 예에서 수신자는 메일을 통해 3개의 오퍼 제안을 받을 수 있습니다.

![](assets/offer_space_overview_002.png)

수신자가 오퍼에 적합하지 않은 경우 미리보기에 표시됩니다.

![](assets/offer_space_overview_001.png)


컨텍스트가 공백으로 제한되면 미리보기에서 해당 컨텍스트를 무시할 수 있습니다. 이는 인바운드 채널을 사용하여 스페이스에서 참조된 필드를 추가하기 위해 상호 작용 스키마를 확장한 경우입니다.

자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/advanced-parameters/extension-example.html){target="_blank"}에서 이 샘플을 참조하세요.