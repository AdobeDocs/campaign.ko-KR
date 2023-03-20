---
title: 개인화 블록
description: 메시지 콘텐츠에서 내장된 개인화 블록을 사용하는 방법을 알아봅니다
feature: Personalization
role: User
level: Beginner
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 1%

---


# 개인화 블록{#personalization-blocks}

개인화 블록은 게재에 삽입할 수 있는 특정 렌더링을 포함하는 동적 콘텐츠입니다. 예를 들어 로고, 인사말 또는 미러 페이지에 대한 링크를 추가할 수 있습니다.

개인화된 콘텐츠 블록에 액세스하려면 다음 위치로 이동하십시오. **[!UICONTROL Resources > Campaign Management > Personalization blocks]** 노드 아래에 있는 노드 아래에 있는 노드 아래에 있는 노드 아래에 있는 노드 아래에 있는 노드 아래에 있는 노드 이름을 지정합니다. 기본 제공 개인화 블록은 [이 섹션](#ootb-personalization-blocks).

게재 개인화를 최적화하는 새 블록을 정의할 수도 있습니다. [자세히 알아보기](#create-custom-personalization-blocks)

## 개인화 블록 삽입 {#insert-personalization-blocks}

메시지에 개인화 블록을 삽입하려면 아래 단계를 수행하십시오.

1. 게재 마법사의 콘텐츠 편집기에서 개인화 아이콘을 클릭하고 을(를) 선택합니다 **[!UICONTROL Include]** 메뉴 아래의 제품에서 사용할 수 있습니다.
1. 목록에서 개인화 블록을 선택하거나 **[!UICONTROL Other...]** 메뉴를 사용하여 전체 목록에 액세스합니다.

   ![](assets/perso-content-block.png)

1. 그런 다음 개인화 블록이 스크립트로 삽입됩니다. 개인화가 생성되면 수신자 프로필에 자동으로 조정됩니다.
1. 다음 위치로 이동합니다. **[!UICONTROL Preview]** 탭하고 수신자를 선택하여 특정 수신자에 대해 이 블록의 콘텐츠를 봅니다.

게재 콘텐츠에 개인화 블록의 소스 코드를 포함할 수 있습니다. 이렇게 하려면 을(를) 선택합니다. **[!UICONTROL Include the HTML source code of the block]** 선택합니다.

## 내장 개인화 블록 {#ootb-personalization-blocks}

내장 개인화 블록은 다음과 같습니다.

* **[!UICONTROL Enabled by Adobe Campaign]**: &quot;Enabled by Adobe Campaign&quot; 로고를 삽입합니다.
* **[!UICONTROL Formatting function for proper nouns]**: 는 **[!UICONTROL toSmartCase]** 각 단어의 첫 번째 문자를 대문자로 변경하는 Javascript 함수입니다.
* **[!UICONTROL Greetings]**: 받는 사람의 전체 이름과 쉼표를 삽입합니다. 예: &quot;안녕하세요, 존 도.&quot;
* **[!UICONTROL Insert logo]**: 인스턴스 설정에 정의된 로고를 삽입합니다.
* **[!UICONTROL Link to mirror page]**: 에 링크를 삽입합니다. [미러 페이지](mirror-page.md). 기본 형식은 다음과 같습니다. &quot;이 메시지를 올바르게 볼 수 없는 경우 여기를 클릭하십시오.&quot;
* **[!UICONTROL Mirror page URL]**: 는 미러 페이지 URL을 삽입하여 게재 디자이너가 링크를 확인할 수 있도록 합니다.
* **[!UICONTROL Offer acceptance URL in unitary mode]**: 오퍼를 설정할 수 있는 URL을 삽입합니다. **[!UICONTROL Accepted]**. (상호 작용 모듈이 활성화된 경우 이 블록을 사용할 수 있습니다.)
* **[!UICONTROL Registration confirmation]**: 구독을 확인하는 링크를 삽입합니다.
* **[!UICONTROL Registration link]**: 구독 링크를 삽입합니다. 이 링크는 인스턴스 설정에서 정의됩니다. 기본 콘텐츠는 다음과 같습니다. &quot;등록하려면 여기를 클릭하십시오.&quot;
* **[!UICONTROL Registration link (with referrer)]**: 방문자 및 게재를 식별할 수 있도록 구독 링크를 삽입합니다. 이 링크는 인스턴스 설정에서 정의됩니다.
* **[!UICONTROL Registration page URL]**: 구독 URL을 삽입합니다.
* **[!UICONTROL Style of content emails]** 및 **[!UICONTROL Notification style]**: 사전 정의된 HTML 스타일로 전자 메일의 형식을 지정하는 코드를 생성합니다.
* **[!UICONTROL Unsubscription link]**: 모든 게재에서 구독을 취소할 수 있는 링크를 차단 목록 삽입합니다. 연결된 기본 컨텐츠는 다음과 같습니다. &quot;이 메시지를 받는 이유는 ***조직 이름*** 또는 제휴 더 이상 메시지를 받지 않으려면 ***조직 이름*** 여기를 클릭하세요.&quot;

## 맞춤형 개인화 블록 만들기 {#create-custom-personalization-blocks}

개인화 아이콘에서 삽입할 개인화된 새로운 콘텐츠 블록을 정의할 수 있습니다.

개인화 블록을 만들려면 아래 단계를 수행하십시오.

1. 다음 위치로 이동합니다. **[!UICONTROL Resources > Campaign Management > Personalization blocks]** 캠페인 탐색기의 폴더.
1. 기본 제공 블록 목록 위에서 **[!UICONTROL New]**.

   ![](assets/perso-new-block.png)

1. 개인화 블록의 설정을 입력합니다.

   ![](assets/perso-custom-block.png)

   * 블록의 레이블을 입력합니다. 이 레이블은 개인화 필드 삽입 창에 표시됩니다.
   * 선택 **배달** 컨텐츠 유형.
   * 를 활성화합니다 **[!UICONTROL Visible in the customization menus]** 개인화 필드 삽입 아이콘에서 이 블록에 액세스할 수 있는 옵션입니다.
   * 필요한 경우 **[!UICONTROL The content of the personalization block depends upon the format]** HTML 및 텍스트 이메일에 대해 두 개의 서로 다른 블록을 정의하는 옵션.
   * 컨텐츠(HTML, 텍스트, JavaScript 등)를 개인화 블록 중에서 **[!UICONTROL Save]**.

저장하면 게재 편집기에서 새 개인화 블록을 사용할 수 있습니다.

## 튜토리얼 비디오 {#personalization-blocks-video}

다음 비디오에서 다이내믹 콘텐츠 블록을 만들고 이 블록을 사용하여 이메일 게재의 콘텐츠를 개인화하는 방법을 알아봅니다.

>[!VIDEO](https://video.tv.adobe.com/v/342088?quality=12)


