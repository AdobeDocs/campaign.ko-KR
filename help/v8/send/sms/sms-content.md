---
title: SMS 콘텐츠 정의
description: SMS 게재의 콘텐츠를 설정하는 방법 알아보기
feature: SMS
role: User
level: Beginner, Intermediate
badge: label="제한 공개" type="Informative"
source-git-commit: a184a29301f2bd739bc3fd1373fc8cfad58f0393
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---


# SMS 콘텐츠 {#sms-content}

SMS 게재의 콘텐츠를 구성하려면:

1. **[!UICONTROL Text content]** 마법사에 메시지 내용 입력

   ![](assets/sms_content.png){zoomable="yes"}

1. 개인화 필드 삽입(예: 이름 추가) 또는 사전 정의된 개인화 블록 삽입(예: 인사 추가)을 통해 메시지를 개인화할 수 있습니다. 개인화 버튼을 클릭하여 다음을 추가할 수 있습니다.

   ![](assets/sms_perso.png){zoomable="yes"}

   **[!UICONTROL Recipient]** > **[!UICONTROL First name]**&#x200B;을(를) 클릭하면 다음과 같은 개인화가 이루어집니다.

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

1. **[!UICONTROL Preview]** 탭에서 **[!UICONTROL Test personalization]** 드롭다운 목록을 클릭하고 **[!UICONTROL Recipient]** 테이블에서 수신자를 선택하여 게재를 미리 볼 수 있습니다.

   ![](assets/sms_preview.png){zoomable="yes"}

   개인화된 SMS를 미리 볼 수 있습니다.

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* SMS 메시지는 Latin-1(ISO-8859-1) 코드 페이지를 사용하는 경우 160자로 제한됩니다. 메시지가 유니코드로 작성되면 70자를 초과할 수 없습니다. 특정 특수 문자는 메시지 길이에 영향을 줄 수 있습니다. 메시지 길이에 대한 자세한 내용은 [SMS 문자 음역](smpp-external-account.md#smpp-channel-settings) 섹션을 참조하세요.
>
>* 개인화 필드 또는 조건부 콘텐츠 필드가 있으면 메시지 크기가 받는 사람마다 다릅니다. 개인화가 수행되면 메시지 길이를 평가해야 합니다.
>
>*분석을 시작할 때 메시지 길이를 확인하고 오버플로 시 경고가 표시됩니다.

게재 콘텐츠를 만든 후 [대상자를 선택](sms-audience.md)할 수 있습니다.