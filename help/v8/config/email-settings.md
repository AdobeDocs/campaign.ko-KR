---
title: Campaign 전자 메일 채널 설정
description: Campaign 전자 메일 채널 설정
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: 9457652f62810eb401c4010acd9b5da42d88d796
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 6%

---

# Campaign 전자 메일 채널 설정

## 이메일 BCC {#email-bcc}

>[!NOTE]
>
>이 기능은 Campaign v8.3부터 사용할 수 있습니다. 버전을 확인하려면 [이 섹션](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

플랫폼에서 보낸 이메일 사본을 유지하도록 Adobe Campaign을 구성할 수 있습니다.

Adobe Campaign 자체는 보관된 파일을 관리하지 않습니다. 선택한 메시지를 외부 시스템을 사용하여 처리하고 보관할 수 있는 전용 BCC(Blind Carbon Copy) 이메일 주소로 보낼 수 있습니다. 보낸 전자 메일에 해당하는 .eml 파일을 SMTP 전자 메일 서버와 같은 원격 서버로 전송할 수 있습니다.

>[!CAUTION]
>
>개인 정보 보호를 위해 BCC 이메일은 PII(보안 개인 식별 정보)를 저장할 수 있는 보관 시스템에 의해 처리되어야 합니다.

보관 대상은 선택한 BCC 전자 메일 주소이며 게재 수신자에게는 보이지 않습니다.

![](../assets/do-not-localize/speech.png)  관리 Cloud Services 사용자로, [연락처 Adobe](../start/campaign-faq.md#support)보관에 사용할 숨은 참조 전자 메일 주소를 통신하기 위해 {target=&quot;_blank&quot;}.

BCC 이메일 주소가 정의되면 게재 수준에서 전용 옵션을 활성화해야 합니다.

>[!CAUTION]
>
>새 게재 또는 게재 템플릿을 만들 때, **[!UICONTROL Email BCC]** 은 기본적으로 활성화되지 않습니다. 이메일 게재 또는 게재 템플릿에서 수동으로 활성화해야 합니다.


이렇게 하려면 아래 단계를 수행합니다:

1. 이동 **[!UICONTROL Campaign Management]** > **[!UICONTROL Deliveries]**, 또는 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. 원하는 게재를 선택하거나 기본 제공 게재를 복제합니다 **[!UICONTROL Email delivery]** 템플릿을 선택한 다음 복제한 템플릿을 선택합니다.
1. **[!UICONTROL Properties]** 버튼을 클릭합니다.
1. **[!UICONTROL Delivery]** 탭을 선택합니다. 
1. **[!UICONTROL Email BCC]** 옵션을 선택합니다.

   ![](assets/email-bcc.png)

1. **[!UICONTROL Ok]**&#x200B;을(를) 선택합니다.

이 템플릿을 기반으로 하는 각 게재에 대해 전송된 모든 메시지의 사본은 구성된 이메일 숨은 참조 주소로 전송됩니다.

다음 사양 및 권장 사항을 참조하십시오.

* 숨은 참조 이메일 주소는 하나만 사용할 수 있습니다.

* BCC 주소에 전송되는 모든 이메일을 보관할 수 있는 수신 용량이 충분한지 확인합니다.

* 이메일 BCC <!--with Enhanced MTA--> 은 수신자에게 전달하기 전에 BCC 이메일 주소로 전달하므로 원래 게재가 바운스되었을 수 있어도 BCC 메시지가 전송될 수 있습니다. 바운스에 대한 자세한 내용은 [게재 실패 이해](../send/delivery-failures.md).

* BCC 주소로 전송된 이메일을 열고 클릭스루하는 경우 **[!UICONTROL Total opens]** 및 **[!UICONTROL Clicks]** send analysis에서 계산되지 않을 수 있습니다.

<!--Only successfully sent emails are taken in account, bounces are not.-->

**자세한 내용은 Campaign Classic v7 설명서**&#x200B;를 참조하세요

* [미러 페이지 생성](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page){target=&quot;_blank&quot;}

* [전자 메일 형식 선택](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target=&quot;_blank&quot;}

* [문자 인코딩 선택](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target=&quot;_blank&quot;}

* [바운스 이메일 주소 설정](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target=&quot;_blank&quot;}

* [이메일 게재 템플릿 사용](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=ko){target=&quot;_blank&quot;}

* [게재 실패 이해](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target=&quot;_blank&quot;}
