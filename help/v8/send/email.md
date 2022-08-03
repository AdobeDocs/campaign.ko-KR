---
title: Adobe Campaign을 사용하여 이메일 보내기
description: Campaign 이메일 시작하기
feature: Email
role: Data Engineer
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 0a55d947a7646aab64ab2f9d0d09a6f930db576e
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 이메일 디자인 및 보내기

이메일 게재를 사용하면 개인화된 이메일을 대상 모집단으로 보낼 수 있습니다.

![](../assets/do-not-localize/book.png)자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html){target=&quot;_blank&quot;}를 참조하십시오

## 첫 번째 이메일 게재 만들기

나머지 고객 경험과 일관적인 개인화된 상황별 관련 이메일을 만들 수 있습니다.

![](assets/new-email-content.png)


다음 샘플에서는 개인화된 데이터, 외부 URL에 대한 링크 및 미러 페이지에 대한 링크가 포함된 Adobe Campaign에서 이메일 전달을 디자인하는 단계를 배웁니다.

1. **게재 만들기**

   새 게재를 만들려면 **캠페인** 탭, **게재** 을 클릭하고 **만들기** 기존 게재 목록 위의 단추.

   ![](assets/delivery_step_1.png)

1. **템플릿을 선택합니다**

   게재 템플릿을 선택한 다음 게재의 이름을 지정합니다. 이 이름은 수신자가 아니라 Adobe Campaign 콘솔 사용자만 볼 수 있지만 게재 목록에는 이 제목이 표시됩니다. **[!UICONTROL Continue]**&#x200B;를 클릭합니다.

   ![](assets/dce_delivery_model.png)

1. **콘텐츠 가져오기**

   을(를) 클릭합니다. **소스** 탭을 사용하여 HTML 컨텐츠를 붙여넣습니다.

   ![](assets/paste-content.png)


1. **메시지 개인화**


   * 수신자의 이름과 성을 추가합니다

      대상 프로필의 이름과 성을 메시지 콘텐츠에 삽입하려면 삽입할 위치에 커서를 놓고 도구 모음에서 마지막 아이콘을 클릭한 다음 를 클릭합니다 **[!UICONTROL Include]** 을(를) 선택합니다. **[!UICONTROL Greetings]**.

      ![](assets/include-greetings.png)

      수신자를 선택하여 미리 보기 탭으로 이동하여 개인화를 확인합니다.

      ![](assets/perso-check.png)

   * 추적된 링크 삽입

      이미지나 텍스트를 통해 게재 수신자를 외부 주소로 가져오려면 선택하고 을(를) 클릭합니다 **[!UICONTROL Add a link]** 아이콘 을 클릭하여 제품에서 사용할 수 있습니다.

      에 링크의 URL을 입력합니다. **URL** 다음 형식을 사용하는 필드 **https://www.myURL.com**&#x200B;를 입력한 다음 확인합니다.

      ![](assets/add-a-link.png)

   * 미러 페이지 추가

      수신자가 웹 브라우저에서 게재 콘텐츠를 볼 수 있도록 하려면 메시지의 미러 페이지에 링크를 추가합니다.

      이 링크를 삽입할 위치에 커서를 놓고 도구 모음에서 마지막 아이콘을 클릭한 다음 **[!UICONTROL Include]** 을(를) 선택합니다. **[!UICONTROL link to mirror page]**.
   컨텐츠가 준비되면 **저장**: 이제 게재 목록( **[!UICONTROL Campaigns > Deliveries]** 탭. 첫 번째 이메일 게재가 준비되었습니다. 이제 대상을 정의하고, 게재의 유효성을 확인하고, 전송해야 합니다.


여기에서 이메일 콘텐츠를 가져오는 방법을 알아봅니다 [사용 사례](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html).

자세한 내용은 **Campaign Classic v7 설명서**:

* Campaign에서 이메일 디자인
   ![](../assets/do-not-localize/book.png) [이메일 디자인 방법 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html){target=&quot;_blank&quot;}
* 이메일 템플릿 만들기 및 사용
   ![](../assets/do-not-localize/book.png) [이메일 템플릿에 대해 자세히 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html){target=&quot;_blank&quot;}
* 이메일 대상자를 선택합니다
   ![](../assets/do-not-localize/book.png) [대상 모집단을 정의하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target=&quot;_blank&quot;}
* 게재 유효성 검사 및 증명 보내기
   ![](../assets/do-not-localize/book.png) [게재의 유효성을 검사하는 주요 단계를 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}
* 추가 [시드 주소](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target=&quot;_blank&quot;}

## 이메일 테스트 및 유효성 검사

Campaign은 대상자에게 이메일을 보내기 전에 전자 메일을 테스트하고 확인하는 몇 가지 방법을 제공합니다.

![](../assets/do-not-localize/book.png) [Campaign Classic v7 설명서에 나열된 우수 사례 적용](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html){target=&quot;_blank&quot;}

다음을 수행할 수 있습니다.

* 게재 분석 로그 확인
* 증명 보내기
* 시드 주소 추가
* 통제 그룹 사용
* 전자 메일 렌더링 확인

![](../assets/do-not-localize/book.png)[자세한 내용은 Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}를 참조하십시오
