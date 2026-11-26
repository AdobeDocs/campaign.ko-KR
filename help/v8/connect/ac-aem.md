---
title: Campaign 및 Adobe Experience Manager 작업
description: Campaign을 Adobe Experience Manager과 함께 사용하는 방법에 대해 알아보기
feature: Experience Manager Integration
role: Admin, User
level: Beginner
exl-id: e83893f7-a8be-48a3-a7a6-aced7b4d4f69
TQID: 'https://experienceleague.adobe.com/LM635Kjl7bucy1SMcEPuhCElUI7MNrO4B3fwo9fpyFQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: df0d6518-6f49-46e2-b46e-3bcc513f553f
    internal-label: Experience Manager integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 765af3342eb29f27dafa12f72634f5d91361bed5
workflow-type: tm+mt
source-wordcount: '982'
ht-degree: 0%
---
# Campaign 및 Adobe Experience Manager 작업 {#ac-aem}

Adobe Campaign과 Adobe Experience Manager 간의 통합을 통해 이메일 게재의 콘텐츠와 양식을 Adobe Experience Manager에서 직접 관리할 수 있습니다.

## Campaign 웹 사용자 인터페이스와 함께 Adobe Experience Manager as a Cloud Service 사용 {#aem-cs-web-ui}

Campaign 웹 사용자 인터페이스를 사용하면 Adobe Experience Manager as a Cloud Service 환경을 연결하여 콘텐츠를 중앙 집중화할 수 있습니다. 에셋 및 템플릿에 대한 신뢰할 수 있는 단일 소스는 채널 간에 이메일을 일관되게 유지하고 두 솔루션 간에 콘텐츠가 중복되지 않도록 합니다.

* **Assets**: Adobe Experience Manager Assets에서 자산을 관리하고 이메일 콘텐츠에서 직접 재사용합니다. [자세히 알아보기](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/integrations/aem-assets){target="_blank"}
* **템플릿**: Adobe Experience Manager as a Cloud Service에서 전자 메일 템플릿을 만들고 승인한 다음 게재에서 콘텐츠 템플릿으로 사용합니다. [자세히 알아보기](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/integrations/aem-content){target="_blank"}

연결은 클라이언트 콘솔에 구성된 **[!UICONTROL AEM]** 외부 계정을 사용합니다. [외부 계정](../config/external-accounts.md)을 참조하세요.

## 클라이언트 콘솔에서 Adobe Experience Manager 사용 {#aem-console}

아래 섹션에서는 Campaign 클라이언트 콘솔의 통합에 대해 설명합니다.

[이 문서에서 Adobe Experience Manager에 대해 자세히 알아보세요](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html?lang=ko#aem-and-adobe-campaign-integration-workflow){target="_blank"}.


>[!NOTE]
>
>Managed Cloud Services 사용자는 [Adobe에 문의](../start/campaign-faq-comprehensive.md#support)하여 Adobe Experience Manager을 Campaign과 통합하세요.

## Adobe Experience Manager에서 컨텐츠 가져오기 {#integrating-with-aem}

예를 들어 이 통합을 사용하여 Adobe Experience Manager에서 뉴스레터를 생성하고 이메일 캠페인의 일부로 Adobe Campaign에서 사용할 수 있습니다.

**Adobe Experience Manager에서:**

1. [!DNL Adobe Experience Manager] 작성자 인스턴스로 이동하여 페이지의 왼쪽 상단에 있는 Adobe Experience를 클릭합니다. 메뉴에서 **[!UICONTROL Sites]**&#x200B;을(를) 선택합니다.

   Sites 옵션이 강조 표시된 ![Adobe Experience Manager 탐색 메뉴](assets/aem_authoring_1.png)

1. **[!UICONTROL Campaigns > Name of your brand (here we.Shopping) > Main Area > Email]**&#x200B;에 액세스합니다.

1. **[!UICONTROL Create]**&#x200B;을(를) 클릭하고 드롭다운 메뉴에서 **[!UICONTROL Page]**&#x200B;을(를) 선택합니다.

   ![만들기 메뉴가 열리고 페이지가 선택된 AEM Sites 전자 메일 폴더](assets/aem_authoring_2.png)

1. **[!UICONTROL Adobe Campaign Email]** 템플릿을 선택하고 뉴스레터 이름을 지정합니다.

1. 페이지를 만든 후 **[!UICONTROL Page information]** 메뉴에 액세스하고 **[!UICONTROL Open Properties]**&#x200B;을(를) 클릭합니다.

   ![페이지 정보 메뉴가 열리고 속성 열기가 강조 표시된 뉴스레터 페이지 편집기](assets/aem_authoring_3.png)

1. Adobe Campaign의 개인화 필드와 같은 구성 요소를 추가하여 이메일 콘텐츠를 사용자 정의합니다. 자세한 내용은 [Adobe Experience Manager 설명서](https://experienceleague.adobe.com/docs/experience-manager-65/content/sites/authoring/aem-adobe-campaign/campaign.html?lang=ko#editing-email-content){target="_blank"}를 참조하세요.

1. 전자 메일이 준비되면 **[!UICONTROL Page information]** 메뉴로 이동하여 **[!UICONTROL Start workflow]**&#x200B;을(를) 클릭합니다.

   ![페이지 정보 메뉴를 열고 워크플로 시작 강조 표시된 뉴스레터 페이지 편집기](assets/aem_authoring_4.png)

1. 첫 번째 드롭다운에서 **[!UICONTROL Approve Adobe Campaign]**&#x200B;을(를) 워크플로 모델로 선택하고 **[!UICONTROL Start workflow]**&#x200B;을(를) 클릭합니다.

   ![워크플로 모델로 선택된 Adobe Campaign에 대한 승인이 있는 워크플로 시작 대화 상자](assets/aem_authoring_5.png)

1. 페이지 맨 위에 `This page is subject to the workflow Approve for Adobe Campaign`을(를) 나타내는 면책조항이 나타납니다. 면책조항 옆의 **[!UICONTROL Complete]**&#x200B;을(를) 클릭하여 검토를 확인하고 **[!UICONTROL Ok]**&#x200B;을(를) 클릭합니다.

1. **[!UICONTROL Complete]**&#x200B;을(를) 다시 클릭하고 **[!UICONTROL Next Step]** 드롭다운에서 **[!UICONTROL Newsletter approval]**&#x200B;을(를) 선택합니다.

   ![다음 단계 목록 및 확인 단추에서 선택한 뉴스레터 승인이 있는 작업 항목 완료 대화 상자](assets/aem_authoring_6.png)

이제 뉴스레터가 준비되었으며 Adobe Campaign에서 동기화되었습니다.

**Adobe Campaign에서:**

1. **[!UICONTROL Campaigns]** 탭에서 **[!UICONTROL Deliveries]**&#x200B;을(를) 클릭한 다음 **[!UICONTROL Create]**&#x200B;을(를) 클릭합니다.

1. **[!UICONTROL Delivery template]** 드롭다운 메뉴에서 **[!UICONTROL Email delivery with AEM content (mailAEMContent)]** 템플릿을 선택합니다.

   ![AEM 콘텐츠(mailAEMContent)가 선택된 이메일 게재가 포함된 캠페인 게재 템플릿 목록](assets/aem_authoring_7.png)

1. 게재에 **[!UICONTROL Label]**&#x200B;을(를) 추가하고 **[!UICONTROL Continue]**&#x200B;을(를) 클릭합니다.

1. AEM 게재에 액세스하려면 **[!UICONTROL Synchronize]**&#x200B;을(를) 클릭하십시오.

   인터페이스에 단추가 표시되지 않으면 **[!UICONTROL Properties]** 단추로 이동하여 **[!UICONTROL Advanced]** 탭에 액세스합니다. **[!UICONTROL Content editing mode]** 필드가 **[!UICONTROL AEM]**(으)로 구성되어 있는지 확인하고 **[!UICONTROL AEM account]** 필드에 AEM 인스턴스 세부 정보를 입력하십시오.

   ![동기화 버튼이 강조 표시된 캠페인 이메일 게재 도구 모음](assets/aem_authoring_8.png)

1. [!DNL Adobe Experience Manager]에서 이전에 만든 AEM 게재를 선택하고 **[!UICONTROL Ok]**&#x200B;을(를) 클릭하여 확인합니다.

   ![뉴스레터 행이 선택된 승인된 AEM 이메일을 나열하는 AEM 콘텐츠와 동기화 대화 상자](assets/aem_authoring_11.png)

1. AEM 게재를 수정할 때마다 **[!UICONTROL Refresh content]** 단추를 클릭해야 합니다.

   ![콘텐츠 새로 고침 단추가 강조 표시되고 동기화 해제 단추가 있는 동기화된 전자 메일 게재](assets/aem_authoring_12.png)

1. Experience Manager과 Campaign 간의 연결을 제거하려면 **[!UICONTROL Desynchronize]**&#x200B;을(를) 클릭합니다.

이제 대상자에게 이메일을 보낼 준비가 되었습니다.

## Adobe Experience Manager Assets 라이브러리에서 자산 가져오기 {#assets-library}

Adobe Campaign에서 전자 메일 또는 랜딩 페이지를 편집하는 동안 [!DNL Adobe Experience Manager Assets Library]에서 직접 자산을 삽입할 수도 있습니다. 이 기능은 [Adobe Experience Manager Assets 설명서](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html?lang=ko){target="_blank"}에 자세히 설명되어 있습니다.

**Adobe Experience Manager에서:**

1. [!DNL Adobe Experience Manager] 작성자 인스턴스로 이동하여 페이지의 왼쪽 상단에 있는 Adobe Experience를 클릭합니다. 메뉴에서 **[!UICONTROL Assets]** `>` **[!UICONTROL Files]**&#x200B;을(를) 선택합니다.

   ![파일 옵션이 강조 표시된 AEM Assets 탐색 메뉴](assets/aem_assets_1.png)

1. **만들기**&#x200B;를 클릭한 다음 **파일**&#x200B;을 클릭하여 자산을 **Adobe Experience Manager Assets 라이브러리**&#x200B;로 가져옵니다. 자세한 내용은 [Adobe Experience Manager 설명서](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html?lang=ko#uploading-assets){target="_blank"}를 참조하세요.

   ![만들기 메뉴를 열고 자산을 업로드하도록 선택한 파일을 사용하여 AEM Assets 파일 보기](assets/aem_assets_2.png)

1. 필요한 경우 에셋 이름을 변경하고 **업로드**&#x200B;를 선택합니다.

이제 에셋이 **Adobe Experience Manager Assets 라이브러리**&#x200B;에 업로드되었습니다.

**Adobe Campaign에서:**

1. Adobe Campaign에서 **캠페인** 탭으로 이동하여 새 게재를 만들고 **게재**&#x200B;를 클릭한 다음 기존 게재 목록 위에 있는 **만들기** 단추를 클릭합니다.

   [만들기] 단추가 강조 표시된 캠페인 탭의 ![캠페인 게재 목록](assets/aem_assets_3.png)

1. **게재 템플릿**&#x200B;을 선택한 다음 게재 이름을 지정합니다.

1. 메시지 콘텐츠를 정의하고 개인화합니다. [자세히 알아보기](../send/email.md)

1. **Adobe Experience Manager Assets 라이브러리**&#x200B;를 사용하려면 AEM 게재의 **[!UICONTROL Properties]**&#x200B;에 액세스하여 **[!UICONTROL Advanced]** 탭을 선택하십시오.

   **AEM 계정**&#x200B;을(를) 선택하고 **[!UICONTROL Use above AEM instance as shared asset library]** 옵션을 활성화하세요.

   ![AEM 계정 설정 및 공유 자산 라이브러리 옵션이 활성화된 배달 속성 고급 탭](assets/aem_authoring_9.png)

1. **이미지** 아이콘에서 **[!UICONTROL Select a shared asset]** 메뉴에 액세스합니다.

   ![공유 에셋 선택 강조 표시된 Campaign 전자 메일 편집기 이미지 메뉴](assets/aem_assets_4.png)

1. 선택 창에서 **Adobe Experience Manager Assets 라이브러리**&#x200B;의 이미지를 선택한 다음 **선택**&#x200B;합니다.

   ![jogging-newsletter.jpg가 선택된 AEM Assets 라이브러리 파일을 나열하는 공유 자산 창을 선택하십시오](assets/aem_assets_5.png)

이제 에셋이 이메일 게재에 업로드됩니다. 이제 타겟 대상을 지정하고, 게재를 확인하고, 전송을 진행할 수 있습니다.
