---
title: 미러 페이지에 링크 추가
description: 미러 페이지에 대한 링크를 추가하고 관리하는 방법을 알아봅니다
feature: Email
role: User
level: Beginner
source-git-commit: d8ceefe1dd56aecb810878d99395ac900f889c2e
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# 미러 페이지에 대한 링크{#mirror-page}

## 미러 페이지 정보{#about-mirror-page}

미러 페이지는 이메일의 온라인 버전입니다.

대부분의 이메일 클라이언트는 문제 없이 이미지를 렌더링하지만, 일부 사전 설정은 보안상의 이유로 이미지를 표시하지 않을 수 있습니다. 사용자는 이메일의 미러 페이지로 이동할 수 있습니다. 예를 들어 받은 편지함에서 이미지를 보려 할 때 렌더링 문제 또는 이미지가 손상된 경우 이 페이지를 찾을 수 있습니다. 액세스 가능성을 위해 온라인 버전을 제공하거나 소셜 공유를 권장하는 것이 좋습니다.

Adobe Campaign에서 생성한 미러 페이지에는 모든 개인화 데이터가 포함되어 있습니다.

![](assets/mirror-page-link.png)


## 미러 페이지에 링크 추가{#link-to-mirror-page}

미러 페이지에 링크를 삽입하는 것이 좋습니다. 이 링크는 &#39;브라우저에서 이 전자 메일 보기&#39; 또는 &#39;온라인에서 이 전자 메일 읽기&#39;와 같은 것일 수 있습니다. 이메일의 머리글 또는 바닥글에 종종 있습니다.

Adobe Campaign에서는 전용 페이지를 사용하여 전자 메일 콘텐츠의 미러 페이지에 대한 링크를 삽입할 수 있습니다 **개인화 블록**. 기본 제공 **미러 페이지에 대한 링크** 개인화 블록은 이메일 콘텐츠에 다음 코드를 삽입합니다. `<%@ include view='MirrorPage' %>`.

<!--For more on personalization blocks insertion, refer to [Personalization blocks](personalization-blocks.md).-->

## 미러 페이지 생성{#mirror-page-generation}

기본적으로 이메일 컨텐츠가 비어 있지 않고 미러 페이지에 대한 링크(미러 링크)가 포함되어 있는 경우 Adobe Campaign에서 미러 페이지를 자동으로 생성합니다.

이메일 미러 페이지의 생성 모드를 제어할 수 있습니다. 배달 속성에서 옵션을 사용할 수 있습니다. 다음 옵션에 액세스하려면

1. 다음 위치로 이동합니다. **[!UICONTROL Validity]** 전자 메일 속성의 탭입니다.
1. 에서 **미러 페이지 관리** 섹션에서 **[!UICONTROL Mode]** 드롭다운 목록

![](assets/mirror-page-generation.png)

기본 모드 외에 다음 옵션을 사용할 수 있습니다.

* **[!UICONTROL Force the generation of the mirror page]**: 게재에 미러 페이지에 대한 링크가 삽입되지 않은 경우에도 이 모드를 사용하여 미러 페이지를 생성합니다.
* **[!UICONTROL Do not generate the mirror page]**: 링크가 게재에 있어도 미러 페이지를 생성하지 않도록 하려면 이 모드를 사용합니다.
* **[!UICONTROL Generates a mirror page accessible using only the message identifier]**: 이 옵션을 사용하여 게재 로그 창에서 개인화 데이터를 사용하여 미러 페이지의 콘텐츠에 액세스할 수 있습니다. 이 미러 페이지에 액세스하려면 게재가 전송되면 해당 게재를 열고 게재를 찾습니다 **[!UICONTROL Delivery]** 탭. 수신자를 선택하고 **[!UICONTROL Display the mirror page for this message...]** 링크를 클릭합니다. 미러 페이지가 새 탭에 표시됩니다.

