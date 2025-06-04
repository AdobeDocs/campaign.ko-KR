---
product: campaign
title: 콘텐츠 관리
description: 콘텐츠 관리
feature: Workflows, Data Management
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 9b225f78-1959-4e4f-aa4e-ff8a63051154
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 2%

---

# 콘텐츠 관리{#content-management}

**콘텐츠 관리** 활동을 사용하면 콘텐츠를 만들고 조작하고 이 콘텐츠를 기반으로 파일을 생성할 수 있습니다. 그런 다음 &#39;게재&#39; 활동을 통해 이 콘텐츠를 게재할 수 있습니다.

>[!CAUTION]
>
>컨텐츠 관리는 선택적 Adobe Campaign 모듈입니다. 사용권 계약을 확인하십시오.

>[!NOTE]
>
>Adobe Campaign 웹 사용자 인터페이스를 사용하면 콘텐츠에 콘텐츠 조각을 사용할 수 있습니다. 이를 통해 마케팅 사용자는 하나 이상의 메시지에서 참조할 수 있는 재사용 가능한 구성 요소 덕분에 여러 사용자 지정 콘텐츠 블록을 사전 빌드할 수 있으므로 향상된 디자인 프로세스에서 메시지 콘텐츠를 신속하게 조합할 수 있습니다. 콘텐츠 조각에 대한 자세한 내용은 [Adobe Campaign 웹 UI 설명서](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/manage-reusable-content/fragments/fragments){target=_blank}를 참조하세요.

활동의 속성은 다음 세 단계로 나뉘어 있습니다.

* **콘텐츠 선택**: 콘텐츠를 이전에 만들었거나 활동을 통해 만들 수 있습니다.
* **콘텐츠 업데이트**: 작업에서 콘텐츠 제목을 수정하거나 모든 XML 콘텐츠를 가져올 수 있습니다.
* **작업**: 결과 콘텐츠를 저장하거나 생성할 수 있습니다.

  ![](assets/content_mgmt_edit.png)

1. **컨텐츠**

   * **[!UICONTROL Specified in the transition]**

     이 옵션을 사용하면 전환에 지정된 콘텐츠를 사용할 수 있습니다. 즉, 콘텐츠 관리를 활성화하는 이벤트에는 **[!UICONTROL contentId]** 변수가 포함되어야 합니다. 이 변수는 이전 콘텐츠 관리 또는 모든 스크립트에 의해 설정할 수 있습니다.

   * **[!UICONTROL Explicit]**

     이 옵션을 사용하면 **[!UICONTROL Content]** 필드를 통해 이미 만들어진 콘텐츠를 선택할 수 있습니다. 이 필드는 **[!UICONTROL Explicit]** 옵션을 선택한 경우에만 표시됩니다.

     ![](assets/content_mgmt_explicit.png)

   * **[!UICONTROL Calculated by a script]**

     콘텐츠 식별자는 스크립트에 의해 계산됩니다. **[!UICONTROL Script]** 필드를 사용하면 콘텐츠의 식별자(기본 키)를 평가하는 JavaScript 템플릿을 정의할 수 있습니다. 이 필드는 **[!UICONTROL Calculated by a script]** 옵션을 선택한 경우에만 표시됩니다.

     ![](assets/content_mgmt_script.png)

   * **[!UICONTROL New, created from a publication template]**

     게시 템플릿에서 새 컨텐츠를 만듭니다. 이 새 콘텐츠는 **[!UICONTROL String]** 필드에 지정된 파일에 저장됩니다. **[!UICONTROL Template]** 필드는 콘텐츠를 만드는 데 사용할 게시 템플릿을 지정합니다.

     ![](assets/content_mgmt_new.png)

1. **콘텐츠 업데이트**

   * **[!UICONTROL Subject]**

     이 필드에서는 콘텐츠의 제목을 수정할 수 있습니다.

   * **[!UICONTROL Access to data from an XML feed]**

     이 옵션을 사용하면 XSL 스타일시트를 통해 다운로드한 XML 문서에서 컨텐트를 만들 수 있습니다. 이 옵션을 선택하면 **[!UICONTROL URL]** 필드에 XML 콘텐츠 다운로드 URL이 지정됩니다. **[!UICONTROL XSL stylesheet]**&#x200B;에서 다운로드한 XML 문서를 변환하는 데 사용할 스타일시트를 지정할 수 있습니다. 이 속성은 선택 사항입니다.

     ![](assets/content_mgmt_xmlcontent.png)

1. **실행할 작업**

   * **[!UICONTROL Save]**

     이 옵션은 생성되거나 수정된 콘텐츠를 저장합니다.

     아웃바운드 전환은 **[!UICONTROL contentId]** 변수에 저장된 콘텐츠를 매개 변수로 사용하여 한 번만 활성화됩니다.

   * **[!UICONTROL Generate]**

     이 옵션은 콘텐츠를 저장한 다음 &#39;파일&#39; 유형 게시로 각 변환 템플릿에 대한 출력 파일을 생성합니다.

     ![](assets/content_mgmt_generate.png)

     **[!UICONTROL contentId]** 변수에 저장된 콘텐츠의 식별자를 매개 변수로 사용하고 **[!UICONTROL filename]** 변수에 파일 이름을 사용하여 생성된 각 파일에 대해 아웃바운드 전환이 활성화됩니다.

## 입력 매개 변수 {#input-parameters}

* contentId

**[!UICONTROL Specified in the transition]** 옵션이 활성화된 경우 사용할 콘텐츠의 식별자입니다.

## 출력 매개 변수 {#output-parameters}

* contentId

  콘텐츠 식별자.

* 파일 이름

  선택한 작업이 **[!UICONTROL Generate]**&#x200B;인 경우 생성된 파일의 전체 이름입니다.
