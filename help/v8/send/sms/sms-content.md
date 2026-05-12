---
title: SMS 콘텐츠 정의 및 개인화
description: SMS 게재 콘텐츠를 정의하고 개인화하는 방법을 알아봅니다
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 71d9376c-86e8-41ec-92dc-863455d40c7a
TQID: https://experienceleague.adobe.com/N4C8Rkg-Kl-82FCZAvJ12KofuRObW170ySJaCHgW5wM
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 254
ht-degree: 1%

---

# SMS 콘텐츠 정의 {#sms-content}

SMS 게재의 콘텐츠를 구성하려면:

1. **[!UICONTROL Text content]** 탭에 메시지 내용을 입력합니다.

   ![](assets/sms_content.png){zoomable="yes"}

1. 개인화 필드 삽입(예: 이름 추가) 또는 사전 정의된 개인화 블록 삽입(예: 인사 추가)을 통해 메시지를 개인화할 수 있습니다. 개인화 버튼을 클릭하여 다음 항목을 추가합니다.

   ![](assets/sms_perso.png){zoomable="yes"}

   예를 들어 **[!UICONTROL Recipient]** > **[!UICONTROL First name]**&#x200B;을(를) 클릭하면 SMS 콘텐츠가 아래와 같이 개인화 필드로 업데이트됩니다.

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

   [이 섹션](../personalize.md)에서 Adobe Campaign의 개인화에 대해 자세히 알아보세요.

1. **[!UICONTROL Preview]** 탭에서 게재 콘텐츠를 미리 볼 수 있습니다. 개인화 설정을 확인하려면 **[!UICONTROL Test personalization]** 드롭다운 목록을 클릭하고 받는 사람을 선택하십시오.

   ![](assets/sms_preview.png){zoomable="yes"}

   개인화를 통해 SMS 미리보기를 확인할 수 있습니다.

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* SMS 메시지는 Latin-1(ISO-8859-1) 코드 페이지를 사용하는 경우 160자로 제한됩니다. 메시지가 유니코드로 작성되면 70자를 초과할 수 없습니다. 특정 특수 문자는 메시지 길이에 영향을 줄 수 있습니다. 메시지 길이에 대한 자세한 내용은 [SMS 문자 음역](smpp-external-account.md#smpp-channel-settings) 섹션을 참조하세요.
>
>* 개인화 필드 또는 조건부 콘텐츠 필드가 있으면 메시지 크기가 받는 사람마다 다릅니다. 개인화가 수행되면 메시지 길이를 평가해야 합니다.
>
>*분석을 시작할 때 메시지 길이를 확인하고 오버플로 시 경고가 표시됩니다.

게재 콘텐츠를 만든 후 [대상자를 선택](sms-audience.md)할 수 있습니다.
