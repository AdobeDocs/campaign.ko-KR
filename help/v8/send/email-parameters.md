---
title: Adobe Campaign의 이메일 매개 변수
description: Adobe Campaign의 이메일 게재와 관련된 옵션 및 설정에 대해 알아봅니다.
feature: Email
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: ad75f01e-2c6c-4607-b15a-8870d399002a
source-git-commit: 6b70ad987b828dc1c17bc4f0683046be4eff0408
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 8%

---

# 이메일 매개변수 {#email-parameters}

이 섹션에서는 이메일 게재와 관련된 게재 속성에서 사용할 수 있는 옵션 및 매개 변수를 제공합니다.

## 이메일 숨은 참조 사용 {#email-bcc}

플랫폼에서 전송된 이메일 사본을 유지하도록 Adobe Campaign을 구성할 수 있습니다. 이 옵션은 [이 페이지](email-bcc.md)에 자세히 설명되어 있습니다.

## 메시지 형식 선택 {#selecting-message-formats}

보낸 이메일 메시지 형식을 변경할 수 있습니다. 이렇게 하려면 게재 속성을 편집하고 **[!UICONTROL Delivery]** 탭을 클릭하십시오.

![](assets/email-message-format.png)

창의 아래 섹션에서 전자 메일 형식을 선택합니다.

* **[!UICONTROL Use recipient preferences]**(기본 모드)

  메시지 형식은 받는 사람 프로필에 저장된 데이터에 따라 정의되며 기본적으로 **[!UICONTROL email format]** 필드(@emailFormat)에 저장됩니다. 수신자가 특정 형식으로 메시지를 수신하려는 경우에 보내는 형식입니다. 필드를 입력하지 않으면 다중 파트 대체 메시지가 전송됩니다(아래 참조).

* **[!UICONTROL Let recipient mail client choose the most appropriate format]**

  메시지에는 텍스트 및 HTML의 두 형식 모두가 포함됩니다. 수신에 표시되는 형식은 수신자의 메일 소프트웨어(다중 파트 대체)의 구성에 따라 다릅니다.

  >[!IMPORTANT]
  >
  >이 옵션에는 문서의 두 버전이 모두 포함됩니다. 따라서 메시지 크기가 더 크기 때문에 게재 처리량이 감소합니다.

* **[!UICONTROL Send all messages in text format]**

  메시지는 텍스트 형식으로 전송됩니다. HTML 형식은 전송되지 않지만 수신자가 메시지를 클릭할 때만 미러 페이지에 사용됩니다.

<!--
>[!NOTE]
>
>For more on defining the email content, see [this section]().-->

## 문자 인코딩 설정 {#character-encoding}

게재 매개 변수의 **[!UICONTROL SMTP]** 탭에서 **[!UICONTROL Character encoding]** 섹션을 사용하여 특정 인코딩을 설정할 수 있습니다.

기본 인코딩은 UTF-8입니다. 수신자의 이메일 공급자 중 일부가 UTF-8 표준 인코딩을 지원하지 않는 경우 이메일 수신자에게 특수 문자를 제대로 표시하도록 특정 인코딩을 설정할 수 있습니다.

예를 들어 일본어 문자가 포함된 이메일을 보내려고 합니다. 모든 문자가 일본에 있는 수신자에게 올바르게 표시되도록 하려면 표준 UTF-8이 아닌 일본어 문자를 지원하는 인코딩을 사용할 수 있습니다.

이렇게 하려면 **[!UICONTROL Force the encoding used for messages]** 섹션에서 **[!UICONTROL Character encoding]** 옵션을 선택하고 표시되는 드롭다운 목록에서 인코딩을 선택합니다.

![](assets/email-smtp-encoding.png)

## 바운스 이메일 관리 {#managing-bounce-emails}

게재 속성의 **[!UICONTROL SMTP]** 탭을 사용하여 바운스 메일 관리도 구성할 수 있습니다.

* **[!UICONTROL Errors-to-address]**: 기본적으로 반송된 이메일은 플랫폼의 기본 오류 상자에 수신되지만 게재에 대한 특정 오류 주소를 정의할 수 있습니다.

* **[!UICONTROL Bounce address]**: 처리되지 않은 반송된 전자 메일이 전달되는 다른 주소를 정의할 수도 있습니다. 이 주소를 사용하면 애플리케이션에서 이메일을 자동으로 검증할 수 없을 때 반송 원인을 조사할 수 있습니다.

이러한 각 필드는 전용 아이콘을 사용하여 개인화할 수 있습니다. [이 섹션](personalization-fields.md)의 개인화 필드에 대해 자세히 알아보세요.

![](assets/email-smtp-bounce.png)

바운스 메일 관리에 대한 자세한 내용은 [이 섹션](delivery-failures.md#bounce-mail-management)을 참조하세요.

## 원클릭 목록 구독 취소 활성화 {#one-click-list-unsubscribe}

원클릭 목록 구독 취소 URL은 이메일 발신자 정보 옆에 표시되는 링크 또는 단추로서, 한 번의 클릭으로 수신자가 메일링 목록에서 즉시 옵트아웃할 수 있습니다. <!--[Learn more](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=ko#list-unsubscribe){target="_blank"}-->

ISP의 이메일 인터페이스에 **구독 취소** 링크로 표시됩니다. 예제:

![](assets/email-list-unsubscribe-example.png)

최적의 전달성 관리를 위해 List-Unsubscribe라는 SMTP 헤더를 추가해야 하며 &quot;스팸으로 보고&quot; 아이콘 대신 사용할 수 있습니다. 실제로 이 기능을 사용하면 컴플레인 비율이 낮아지고 평판이 보호됩니다.

>[!IMPORTANT]
>
>이메일 헤더에 원클릭 구독 취소 URL을 표시하려면 수신자의 이메일 클라이언트가 이 기능을 지원해야 합니다.

이 기능을 사용하려면 게재 속성의 **[!UICONTROL Addition of One-click List-Unsubscription Header]** 탭에서 **[!UICONTROL SMTP]** 옵션을 선택하십시오.

>[!NOTE]
>
>이 옵션은 기본적으로 활성화되어 있습니다.

![](assets/email-smtp-list-unsubscribe.png)

<!--
>[!WARNING]
>
>If you uncheck this option in the delivery template, it will still be enabled by default in the deliveries created from this template. You need to enable the option again at the delivery level.-->

이메일 클라이언트와 옵트아웃을 수행하는 데 사용하는 방법에 따라 이메일 헤더의 **구독 취소** 링크를 클릭하면 다음과 같은 영향을 받을 수 있습니다.

* 전자 메일 클라이언트가 **한 번의 클릭으로** 목록 구독 취소 메서드를 사용하는 경우 받는 사람이 직접 옵트아웃됩니다.

  >[!NOTE]
  >
  >Google 및 Yahoo! 등 주요 ISP 보낸 사람이 **One-Click List-Unsubscribe**&#x200B;를 준수하도록 요청하고 있습니다.

* 이메일 클라이언트가 One-Click List-Unsubscribe를 지원하지 않는 경우에도 **&quot;mailto&quot;** List-Unsubscribe 메서드를 사용할 수 있습니다. 이 메서드는 이메일 헤더에 지정된 구독 취소 주소로 미리 채워진 이메일을 보냅니다.

  헤더에서 주소를 명시적으로 설정하거나 배포 마법사를 통해 설정할 수 있는 동적 주소(예: &lt;%=errorAddress%> 또는 옵션 &#39;NmsEmail_DefaultErrorAddr&#39; 사용)를 사용할 수 있습니다.

>[!NOTE]
>
>[한 번 클릭 목록 구독 취소](https://experienceleague.adobe.com/ko/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations?lang=en#one-click-list-unsubscribe){target="_blank"} 및 [&quot;mailto&quot; 목록 구독 취소](https://experienceleague.adobe.com/ko/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations?lang=en#mailto-list-unsubscribe){target="_blank"} 메서드를 수동으로 설정할 수도 있습니다. 자세한 단계는 Experience Cloud [게재 가능성 모범 사례 안내서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=ko#list-unsubscribe){target="_blank"}에 설명되어 있습니다.


## SMTP 헤더 추가 {#adding-smtp-headers}

게재에 SMTP 헤더를 추가할 수 있습니다. 이렇게 하려면 게재에서 **[!UICONTROL SMTP]** 탭의 관련 섹션을 사용합니다.

이 창에 입력한 스크립트는 **name:value** 형식의 줄당 하나의 헤더를 참조해야 합니다.

필요한 경우 값이 자동으로 인코딩됩니다.

>[!IMPORTANT]
>
>추가 SMTP 헤더 삽입을 위한 스크립트 추가는 고급 사용자를 위해 예약되어 있습니다.
>
>이 스크립트의 구문은 다음과 같은 이 콘텐츠 형식의 요구 사항을 준수해야 합니다: 사용하지 않은 공간, 빈 줄 등이 없음.

![](assets/email-smtp-headers.png)


## 미러 페이지 생성 {#generating-mirror-page}

미러 페이지는 웹 브라우저를 통해 온라인으로 액세스할 수 있는 HTML 페이지입니다. 콘텐츠는 이메일과 동일합니다. 받은 편지함에서 전자 메일을 보려고 할 때 수신자에게 렌더링 문제가 발생하거나 이미지가 손상된 경우 유용합니다.

[이 섹션](mirror-page.md)에서 미러 페이지에 대한 링크를 삽입하는 방법을 알아봅니다.
