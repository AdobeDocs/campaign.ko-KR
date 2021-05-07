---
solution: Campaign
product: Adobe Campaign
title: 캠페인 이메일 채널 설정
description: 캠페인 이메일 채널 설정
feature: 개요
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---

# 캠페인 이메일 채널 설정

## 이메일 숨은 참조

플랫폼에서 보낸 이메일 복사본을 유지하도록 Adobe Campaign을 구성할 수 있습니다.

그러나 Adobe Campaign 자체에서는 보관된 파일을 관리하지 않습니다. 외부 시스템을 사용하여 처리하고 보관할 수 있는 전용 주소로 원하는 메시지를 보낼 수 있습니다.

이렇게 하려면 보낸 이메일에 해당하는 .eml 파일이 SMTP 이메일 서버와 같은 원격 서버로 전송됩니다. 보관 대상은 지정해야 하는 숨은 참조 이메일 주소(전달 받는 사람에게 보이지 않음)입니다.

참고:

* 숨은 참조 이메일 주소는 하나만 사용할 수 있습니다.

* 전송된 이메일만 고려되므로 바운스 수가 없습니다.

이메일 BCC가 구성되면 배달 템플릿에서 또는 **이메일 BCC** 옵션을 통한 배달에서 해당 기능이 활성화되어 있는지 확인합니다.

:arrow_upper_right:자세한 내용은 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=en#email-bcc)를 참조하십시오.

**참고**:이메일 BCC 기능은 선택 사항입니다. 사용권 계약을 확인하십시오.

:speech_bal풍선:관리 Cloud Services 사용자는 [Adobe](../start/support.md#support)에 연락하여 캠페인의 이메일 BCC를 활성화합니다. 선택한 BCC 이메일 주소는 해당 주소를 구성할 Adobe 팀에 제공해야 합니다.