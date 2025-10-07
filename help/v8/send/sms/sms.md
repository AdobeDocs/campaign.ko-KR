---
title: Adobe Campaign으로 SMS 보내기
description: Campaign에서 SMS 시작
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 110a2cac920ca3087f6fcb3cab8474729f6075be
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 12%

---

# SMS 시작 {#gs-sms-channel}

Adobe Campaign을 사용하여 모바일 장치에서 고객에게 문자 메시지를 보낼 수 있습니다. SMS 편집기에서 텍스트 형식의 메시지를 만들고, 개인화하고, 미리 볼 수 있습니다.

Adobe Campaign을 사용하여 모바일 장치에 SMS를 게재하려면 다음이 필요합니다.

* **[!UICONTROL Mobile (SMS)]** 채널에 구성된 외부 계정입니다. [중간 소싱 인프라](sms-mid-sourcing.md)에서 SMS 채널을 구성하는 방법을 알아봅니다. 이 구성의 경우 [SMPP 외부 계정 매개 변수](smpp-external-account.md) 및 [SMS 채널 특성](sms-channel.md)을 이해해야 합니다.
이 설정 후에 SMPP 연결을 확인하고 필요한 경우 문제를 해결하는 방법을 알아봅니다. [자세히 알아보기](smpp-connection.md)

* 이 외부 계정에 올바르게 연결된 SMS 게재 템플릿입니다.


>[!NOTE]
>
>Adobe Campaign을 사용하여 [푸시 알림](../push.md) 및 [LINE](../line/line.md) 메시지를 모바일 장치로 보낼 수도 있습니다.


<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="create-sms.md">
<img alt="SMS 만들기" src="../../assets/do-not-localize/sms-sending.jpg">
</a>
<div><a href="create-sms.md"><strong>SMS 게재 만들기</strong>
</div>
<p>
</td>
<td>
<a href="sms-content.md">
<img alt="SMS 콘텐츠" src="../../assets/do-not-localize/sms-create.jpeg">
</a>
<div>
<a href="sms-content.md"><strong>SMS 콘텐츠 정의</strong></a>
</div>
<p></td>
<td>
<a href="sms-audience.md">
<img alt="SMS 대상자" src="../../assets/do-not-localize/sms-opt-out.jpg">
</a>
<div>
<a href="sms-audience.md"><strong>대상자 선택</strong></a>
</div>
<p>
</td>
<td>
<a href="smpp-external-account.md">
<img alt="SMS 구성" src="../../assets/do-not-localize/sms-config.jpg">
</a>
<div>
<a href="smpp-external-account.md"><strong>SMS 채널 구성</strong></a>
</div>
<p>
</td>
</tr></table>
