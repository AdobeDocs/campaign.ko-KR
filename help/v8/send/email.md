---
product: Adobe Campaign
title: Adobe Campaign을 사용하여 이메일 보내기
description: Campaign에서 이메일 시작
feature: 개요
role: Data Engineer
level: Beginner
source-git-commit: 5762e58aafb11932d0e28d87df84704974c09564
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 4%

---

# 이메일 디자인 및 보내기

이메일 게재를 사용하면 개인화된 이메일을 대상 모집단으로 보낼 수 있습니다.

[!DNL :arrow_upper_right:] 자세한 내용은  [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html)를 참조하십시오.

## 첫 번째 이메일 게재 만들기

나머지 고객 경험과 일관된 개인화된 상황별 관련 이메일을 만들 수 있습니다.

![](assets/new-email-content.png)

[!DNL :arrow_upper_right:] [Campaign Classic v7 설명서에서 이메일 배달을 만드는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/editing-html-content/use-case--creating-an-email-delivery.html)


다음 샘플에서는 개인화된 데이터, 외부 URL에 대한 링크, 미러 페이지에 대한 링크 및 웹 양식에 대한 링크가 포함된 Adobe Campaign에서 이메일 전달을 디자인하는 단계를 배웁니다.

1. 게재 만들기

   새 게재를 만들려면 **캠페인** 탭으로 이동하여 **게재**&#x200B;를 클릭하고 기존 게재 목록 위에 있는 **만들기** 단추를 클릭하십시오.

   ![](assets/delivery_step_1.png)

1. 템플릿을 선택합니다

   게재 템플릿을 선택한 다음 게재의 이름을 지정합니다. 이 이름은 수신자가 아니라 Adobe Campaign 콘솔 사용자만 볼 수 있지만 게재 목록에는 이 제목이 표시됩니다. **[!UICONTROL Continue]**&#x200B;을(를) 클릭합니다.

   ![](assets/dce_delivery_model.png)

1. 콘텐츠 가져오기

   **소스** 탭을 클릭하여 HTML 콘텐츠를 붙여넣습니다.

   ![](assets/paste-content.png)


1. 메시지 개인화


   * 수신자의 이름과 두 번째 이름을 표시합니다

      수신자의 첫 번째 및 두 번째 이름을 게재의 텍스트 필드에 삽입하려면 선택한 텍스트 필드를 클릭한 다음 표시하려는 위치에 커서를 놓습니다. 팝업 도구 모음에서 첫 번째 아이콘을 클릭한 다음 **[!UICONTROL Personalization block]** 을 클릭합니다. **[!UICONTROL Greetings]** 을 선택하고 **[!UICONTROL OK]** 을 클릭합니다.

   * 이미지에 링크 삽입

      이미지를 통해 게재 수신자를 외부 주소로 가져오려면 관련 이미지를 클릭하여 팝업 도구 모음을 표시하고 첫 번째 아이콘에 커서를 놓고 **[!UICONTROL Link to an external URL]** 를 클릭합니다.

      **URL** 필드에 다음 형식의 **https://www.myURL.com**&#x200B;을 사용하여 링크의 URL을 입력한 다음 확인합니다.

      언제든지 창 오른쪽의 섹션을 사용하여 링크를 변경할 수 있습니다.

   * 텍스트에 링크 삽입

      외부 링크를 게재의 텍스트에 통합하려면 일부 텍스트나 텍스트 블록을 선택한 다음 팝업 도구 모음에서 첫 번째 아이콘을 클릭합니다. **[!UICONTROL Link to an external URL]** 을 클릭하고 링크 주소를 **[!UICONTROL URL]** 필드에 입력합니다.

      언제든지 창 오른쪽의 섹션을 사용하여 링크를 변경할 수 있습니다.

   * 미러 페이지 추가

      수신자가 웹 브라우저에서 게재 콘텐츠를 볼 수 있도록 하려면 미러 페이지에 대한 링크를 게재에 통합할 수 있습니다.

      게시된 링크를 볼 텍스트 필드를 클릭합니다. 팝업 도구 모음에서 첫 번째 아이콘을 클릭하고 **[!UICONTROL Personalization block]**, **[!UICONTROL Link to Mirror Page (MirrorPage)]** 순으로 선택합니다. **[!UICONTROL Save]** 을 클릭하여 확인합니다.

   * 웹 애플리케이션에 대한 링크 통합

      디지털 콘텐츠 편집기를 사용하면 랜딩 페이지나 양식 페이지와 같은 Adobe Campaign 콘솔에서 웹 애플리케이션에 대한 링크를 통합할 수 있습니다.

      웹 응용 프로그램에 대한 링크의 텍스트 필드를 선택한 다음 첫 번째 아이콘을 클릭합니다. **[!UICONTROL Link to a Web application]** 을 선택한 다음 **웹 응용 프로그램** 필드 끝에 있는 아이콘을 클릭하여 원하는 응용 프로그램을 선택합니다.

1. 메시지 보내기

   컨텐츠가 통합되면 **저장**&#x200B;을 클릭하여 게재를 저장합니다. 이제 **[!UICONTROL Campaigns > Deliveries]** 탭에 있는 게재 목록에 표시됩니다.


## 컨텐츠 만들기 및 대상자 선택

Campaign으로 직접 만들거나 대상 및 이메일 콘텐츠를 가져올 수 있습니다. 아래 링크를 사용하여 다음 방법을 알아보십시오.

* Campaign에서 이메일 디자인
   [!DNL :arrow_upper_right:] [이메일 디자인 방법 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html)
* 이메일 콘텐츠 가져오기
   [!DNL :arrow_upper_right:] [사용 사례:게재 콘텐츠를 로드하는 워크플로우 만들기](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)
* 이메일 템플릿 만들기 및 사용
   [!DNL :arrow_upper_right:] [이메일 템플릿에 대해 자세히 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=ko)
* 이메일 대상자를 선택합니다
   [!DNL :arrow_upper_right:] [대상 모집단을 정의하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)
* 게재 유효성 검사 및 증명 보내기
   [!DNL :arrow_upper_right:] [게재의 유효성을 검사하는 주요 단계를 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
* [시드 주소 추가](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html)

## 이메일 테스트 및 유효성 검사

Campaign은 대상자에게 이메일을 보내기 전에 전자 메일을 테스트하고 확인하는 몇 가지 방법을 제공합니다.

[!DNL :arrow_upper_right:] [Campaign Classic v7 설명서에 나열된 우수 사례 적용](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html)

다음을 수행할 수 있습니다.

* 게재 분석 로그 확인
* 증명 보내기
* 시드 주소 추가
* 컨트롤 그룹 사용
* 전자 메일 렌더링 확인

[!DNL :arrow_upper_right:] [자세한 내용은 Campaign Classic v7 설명서를 참조하십시오](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)

## 이메일 모니터링

전송되면 게재 대시보드에서 게재 상태를 확인하고 게재 로그 및 보고서에 액세스하여 메시지가 올바르게 전송되었는지 확인합니다.

[!DNL :arrow_upper_right:] [자세한 내용은 Campaign Classic v7 설명서를 참조하십시오](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html)

