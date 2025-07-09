---
title: 독립 실행형 인스턴스의 SMS
description: 독립형 인스턴스에서 SMS 게재를 구성하는 방법을 알아봅니다
feature: SMS
role: User
hide: true
hidefromtoc: true
level: Beginner, Intermediate
exl-id: 7cebcde0-c5a8-4b9b-baba-27a62bebde91
source-git-commit: 6f29a7f157c167cae6d304f5d972e2e958a56ec8
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 0%

---

# 독립 실행형 인스턴스의 SMS {#sms-standalone}

>[!IMPORTANT]
>
>이 설명서는 Adobe Campaign v8.7.2 이상에 대한 것입니다.
>
>이전 버전의 경우 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/ko/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up)를 참조하세요.

독립형 인스턴스에서 SMS 게재를 보내려면 다음이 필요합니다.

1. 커넥터와 메시지 유형을 지정하는 **외부 계정**, [자세한 정보](#external-account)

1. 이 외부 계정을 참조하는 **게재 템플릿**, [여기에서 자세히 알아보기](#sms-delivery-template)

## 외부 계정 만들기 {#external-account}

>[!IMPORTANT]
>
>여러 외부 SMS 계정에 동일한 계정과 암호를 사용하면 계정 간에 충돌과 겹칠 수 있습니다. [SMS 문제 해결 페이지](smpp-connection.md#sms-troubleshooting)에 대해 자세히 알아보세요.

SMPP 외부 계정을 만드는 단계는 다음과 같습니다.

1. **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External Accounts]**&#x200B;에서 **[!UICONTROL New]** 아이콘을 클릭합니다

   ![](assets/sms_extaccount.png){zoomable="yes"}

1. 외부 계정의 **[!UICONTROL Label]** 및 **[!UICONTROL Internal name]**&#x200B;을(를) 설정합니다. 계정 유형을 **[!UICONTROL Routing]**(으)로 정의하고 **[!UICONTROL Enabled]** 상자를 선택한 다음 채널의 경우 **[!UICONTROL Mobile (SMS)]**&#x200B;을(를) 선택하고 게재 모드의 경우 **[!UICONTROL Bulk delivery]**&#x200B;을(를) 선택합니다.

   ![](assets/sms_extaccount_new.png){zoomable="yes"}

1. **[!UICONTROL Mobile]** 탭에서 **[!UICONTROL Extended generic SMPP]**&#x200B;을(를) **[!UICONTROL Connector]** 드롭다운 목록에 유지합니다.
기본적으로 **[!UICONTROL Send messages through a dedicated process]** 상자가 선택되어 있습니다.

   ![](assets/sms_extaccount_connector.png){zoomable="yes"}

   연결을 설정하려면 이 양식의 탭을 채워야 합니다. 자세한 내용은 [SMPP 외부 계정에 대해 자세히 알아보세요](smpp-external-account.md#smpp-connection-settings).


## 게재 템플릿 구성 {#sms-delivery-template}

SMS 게재를 쉽게 만들려면 SMPP 외부 계정이 참조되는 SMS 게재 템플릿을 만드십시오.

**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**&#x200B;에서 기존 모바일 게재 템플릿을 마우스 오른쪽 단추로 클릭하고 **[!UICONTROL Duplicate]**&#x200B;을(를) 선택합니다.

![](assets/sms_template_duplicate.png){zoomable="yes"}

템플릿의 **[!UICONTROL Label]** 및 **[!UICONTROL Internal name]**&#x200B;을(를) 쉽게 인식하도록 변경하고 **[!UICONTROL Properties]** 단추를 클릭하십시오.

![](assets/sms_template_name.png){zoomable="yes"}

**[!UICONTROL General]** 탭의 **[!UICONTROL Routing]**&#x200B;에서 SMPP 외부 계정을 선택합니다.

![](assets/sms_template_routing.png){zoomable="yes"}

**[!UICONTROL SMS]** 탭에서 선택적 매개 변수를 템플릿에 추가할 수 있습니다.

![](assets/sms_template_properties.png){zoomable="yes"}

[이 SMS 탭 구성에 대해 자세히 알아보세요](sms-delivery-settings.md).
