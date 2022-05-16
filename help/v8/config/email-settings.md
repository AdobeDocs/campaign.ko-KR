---
title: Campaign 전자 메일 채널 설정
description: Campaign 전자 메일 채널 설정
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 6%

---

# Campaign 전자 메일 채널 설정

## 이메일 BCC

플랫폼에서 보낸 이메일 사본을 유지하도록 Adobe Campaign을 구성할 수 있습니다.

>[!NOTE]
>이메일 BCC 기능은 선택 사항입니다. 사용권 계약을 확인하십시오.

Adobe Campaign 자체는 보관된 파일을 관리하지 않습니다. 선택한 메시지를 전용 주소로 전송할 수 있습니다. 여기서 외부 시스템을 사용하여 처리 및 아카이빙할 수 있습니다.

이렇게 하려면 보낸 전자 메일에 해당하는 .eml 파일이 SMTP 전자 메일 서버와 같은 원격 서버로 전송됩니다. 보관 대상은 지정해야 하는 BCC 전자 메일 주소(게재 수신자에게 표시되지 않음)입니다.

참고 사항:

* 만 사용할 수 있습니다 **하나** 숨은 참조 이메일 주소입니다.

* 성공적으로 전송된 이메일만 고려하며 바운스는 고려되지 않습니다.

![](../assets/do-not-localize/speech.png)  관리 Cloud Services 사용자로, [연락처 Adobe](../start/campaign-faq.md#support) campaign에서 이메일 BCC를 활성화하려면 선택한 BCC 이메일 주소는 Adobe 팀이 대신 구성하도록 제공해야 합니다.

이메일 BCC가 구성되면 게재 템플릿이나 을 통한 게재에서 기능이 활성화되어 있는지 확인합니다 **이메일 BCC** 선택 사항입니다.

![](assets/email-bcc.png)


Campaign Classic v7 설명서의 **관련 항목**:


* [미러 페이지 생성](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page){target=&quot;_blank&quot;}

* [전자 메일 형식 선택](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target=&quot;_blank&quot;}

* [문자 인코딩 선택](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target=&quot;_blank&quot;}

* [바운스 이메일 주소 설정](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target=&quot;_blank&quot;}

* [이메일 게재 템플릿 사용](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=ko){target=&quot;_blank&quot;}

* [게재 실패 이해](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target=&quot;_blank&quot;}
