---
title: Adobe Campaign으로 이메일 보내기
description: Adobe Campaign에서 이메일을 시작합니다. 대상 모집단에게 개인 맞춤화된 이메일을 전송합니다.
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 10%

---

# 이메일 디자인 및 보내기

이메일 게재를 사용하면 개인화된 이메일을 대상 모집단으로 보낼 수 있습니다. [자세히 알아보기](../send/send.md)

## 첫 번째 이메일 게재 만들기

나머지 고객 경험과 일관적인 개인화된 상황별 관련 이메일을 만들 수 있습니다.

![](assets/new-email-content.png)


다음 샘플에서는 개인화된 데이터, 외부 URL에 대한 링크 및 미러 페이지에 대한 링크가 포함된 Adobe Campaign에서의 이메일 게재를 디자인하는 단계를 배웁니다.

1. **게재 만들기**

   새 게재를 만들려면 **캠페인** 탭으로 이동하여 **게재**&#x200B;를 클릭하고 기존 게재 목록 위에 있는 **만들기** 단추를 클릭하십시오.

   ![](assets/delivery_step_1.png)

1. **템플릿 선택**

   게재 템플릿을 선택한 다음 게재 이름을 지정합니다. 이 이름은 Adobe Campaign 콘솔의 사용자만 볼 수 있고 수신자는 볼 수 없지만 이 제목은 게재 목록에 표시됩니다. **[!UICONTROL Continue]**&#x200B;를 클릭합니다.

   ![](assets/dce_delivery_model.png)

1. **콘텐츠 가져오기**

   **Source** 탭을 클릭하여 HTML 콘텐츠를 붙여넣습니다.

   ![](assets/paste-content.png)

   >[!NOTE]
   >
   >성능 문제를 방지하기 위해 이메일에 포함된 이미지는 100KB를 초과할 수 없습니다.

1. **메시지 개인화**

   * 수신자의 이름과 성 추가

     대상 프로필의 이름과 성을 메시지 내용에 삽입하려면 삽입할 위치에 커서를 놓고 도구 모음에서 마지막 아이콘을 클릭한 다음 **[!UICONTROL Include]**&#x200B;을(를) 클릭하고 **[!UICONTROL Greetings]**&#x200B;을(를) 선택합니다.

     ![](assets/include-greetings.png)

     미리보기 탭으로 이동하여 수신자를 선택하여 개인화를 확인합니다.

     ![](assets/perso-check.png)

     [이 섹션](personalize.md)에서 개인화 옵션에 대해 자세히 알아보세요.

   * 추적된 링크 삽입

     이미지 또는 텍스트를 통해 게재 수신자를 외부 주소로 보내려면 해당 주소를 선택하고 도구 모음에서 **[!UICONTROL Add a link]** 아이콘을 클릭합니다.

     **https://www.myURL.com** 형식을 사용하여 **URL** 필드에 링크의 URL을 입력한 다음 확인하십시오.

     ![](assets/add-a-link.png)

   * 미러 페이지 추가

     받는 사람이 웹 브라우저에서 게재 콘텐츠를 볼 수 있도록 하려면 메시지의 [미러 페이지](mirror-page.md)에 링크를 추가하십시오.

     이 링크를 삽입할 위치에 커서를 놓고 도구 모음에서 마지막 아이콘을 클릭한 다음 **[!UICONTROL Include]**&#x200B;을(를) 클릭하고 **[!UICONTROL link to mirror page]**&#x200B;을(를) 선택합니다.

     [이 섹션](mirror-page.md#link-to-mirror-page)에서 미러 페이지 관리에 대해 자세히 알아보세요.

1. BBC 주소로 메시지 사본 보내기, 메시지 형식 변경, 특정 인코딩 설정 등과 같은 이메일에 대한 추가 매개 변수를 정의할 수 있습니다. [이 섹션](email-parameters.md)에서 자세히 알아보십시오.

1. 콘텐츠가 준비되면 **저장**&#x200B;을 클릭합니다. 이제 콘텐츠가 **[!UICONTROL Campaigns > Deliveries]** 탭의 게재 목록에 표시됩니다.

첫 번째 이메일 게재가 준비되었습니다. 이제 대상자를 정의하고 게재를 확인하고 전송해야 합니다.

이 [사용 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html){target="_blank"}에서 전자 메일 콘텐츠를 가져오는 방법을 알아보세요.

다음 섹션에서 자세히 알아보세요.

<!--[Design an email in Campaign]-->
* [이메일 템플릿 만들기 및 사용](../send/create-templates.md)
* [이메일 대상자 선택](../audiences/gs-audiences.md)
* [게재 유효성 검사 및 증명 보내기](preview-and-proof.md)
* [게재 구성 및 보내기](configure-and-send.md)

## 이메일 테스트 및 유효성 검사

Campaign은 대상자에게 이메일을 보내기 전에 테스트하고 유효성을 검사하는 여러 가지 방법을 제공합니다. [이 섹션](../send/preview-and-proof.md)에서 전자 메일 콘텐츠를 미리 보고 테스트하는 방법을 알아보세요.

다음을 수행할 수 있습니다.

* [증명 보내기](preview-and-proof.md)
* [시드 주소 추가](../audiences/test-profiles.md)
* [게재 분석 로그 확인](delivery-analysis.md)

