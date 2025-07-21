---
title: SMS 게재 설정
description: SMS 게재를 설정하는 방법 알아보기
feature: SMS
role: User
level: Beginner, Intermediate
exl-id: c4d500ef-2339-491f-9ae2-9bfaf72088a9
source-git-commit: ea51863bdbc22489af35b2b3c81259b327380be4
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 1%

---

# SMS 게재 설정 {#sms-settings}

>[!AVAILABILITY]
>
>이 기능은 모든 Campaign FDA 환경에서 사용할 수 있습니다. Campaign FFDA 배포에 **사용할 수 없음**. 이 설명서는 Adobe Campaign v8.7.2 이상에 적용됩니다. 기존 SMS 커넥터에서 새 SMS 커넥터로 전환하려면 이 [기술 정보](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/sms-migration){target="_blank"}를 참조하세요.
>
>이전 버전의 경우 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/ko/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}를 참조하세요.

SMS 게재에 필요한 기술 설정은 다음과 같습니다.

* 메시지 라우팅을 위한 SMPP 외부 계정입니다. [자세히 알아보기](smpp-external-account.md#smpp-connection-settings)
* SMS 탭을 구성합니다. [방법 알아보기](#sms-tab)

각 SMS 게재 만들기에 대한 설정을 수행하지 않도록 게재 템플릿에서 이러한 모든 것을 설정할 수 있습니다.

## SMS 탭 구성 {#sms-tab}

![](assets/send_settings.png){zoomable="yes"}

여기 이 양식에 기입해야 할 정보가 있습니다. 각 필드는 아래에 설명되어 있습니다.

* **[!UICONTROL Sender address]**

  이 필드는 선택 사항입니다. 이를 통해 발신자 주소(oADC)를 재정의할 수 있습니다. 이 필드의 내용은 SUBMIT_SM PDU의 *source_addr* 필드에 있습니다.

  필드는 SMPP 사양에 따라 21자로 제한되지만 일부 공급자는 더 긴 값을 허용할 수 있습니다. 일부 국가에서는 매우 엄격한 제한(길이, 콘텐츠, 허용되는 문자 등)이 적용될 수 있으므로 여기에 배치하는 콘텐츠가 합법적인지 다시 확인해야 합니다. 개인화된 필드를 사용할 때는 특히 주의하십시오.

  이 필드를 비워 두면 외부 계정에 정의된 Source 번호 필드의 값이 대신 사용됩니다. 두 값이 모두 비어 있으면 *source_addr* 필드가 비어 있게 됩니다.

* **[!UICONTROL Service or program ID]**

  >[!NOTE]
  >
  >이 기능을 사용하는 것은 권장되지 않습니다. 선택적 SMPP 매개 변수는 훨씬 더 유연한 구현을 제공합니다.
  >
  >두 기능을 동시에 사용할 수는 없습니다.

  일치하는 외부 계정 설정과 결합하여 각 MT에 하나의 선택적 매개 변수를 보낼 수 있습니다. 이 필드는 TLV의 값 부분을 정의합니다.

* **[!UICONTROL Transmission mode]**

  이 필드는 전송할 SMS 종류를 나타냅니다(모바일 또는 SIM 카드에 저장된 일반 또는 플래시 메시지). 이 설정은 SUBMIT_SM PDU의 dest_addr_subunit 선택 필드에서 전송됩니다.

   * **Flash**&#x200B;이(가) 값을 1로 설정합니다. 이 메시지는 모바일에 표시되며 메모리에 저장되지 않는 플래시 메시지를 보냅니다.
   * **보통**&#x200B;은 값을 0으로 설정합니다. 정상적인 메시지를 보냅니다.
   * **모바일에 저장**&#x200B;에서 값을 2로 설정합니다. SMS를 내부 메모리에 저장하도록 전화기에 알립니다.
   * **터미널에 저장**&#x200B;에서 값을 3으로 설정합니다. SMS를 SIM 카드에 저장하도록 전화기에 알려줍니다.

* **[!UICONTROL Priority, Communication type]**

  확장 SMPP 커넥터에서는 이러한 필드를 무시합니다.

* **[!UICONTROL Maximum number of SMS per message]**

  이 설정은 메시지 페이로드 설정이 비활성화된 경우에만 작동합니다(자세한 내용은 외부 계정 설정 참조). 메시지에 이 값보다 많은 SMS가 필요한 경우 오류가 트리거됩니다.

  SMS 프로토콜은 SMS를 255부분으로 제한하지만 일부 휴대폰에서는 10부분 이상의 긴 메시지를 함께 작성하는 데 문제가 있습니다(제한은 정확한 모델에 따라 다름). 안전을 원한다면 메시지당 5부분을 넘지 않도록 하세요.

  Adobe Campaign에서 개인화된 메시지가 작동하는 방식으로 인해 메시지 크기가 달라질 수 있으므로 매우 긴 메시지가 많으면 전송 비용이 많이 증가할 수 있습니다. 이 값을 적절한 값으로 설정하면 이러한 비용을 제어하는 데 도움이 됩니다.

  0을 지정하면 제한이 비활성화됩니다.

* **[!UICONTROL Optional SMPP parameters (TLV)]**
선택적 SMPP 매개 변수(TLV)로 전송할 추가 필드를 지정할 수 있습니다. 이러한 추가 필드는 각 MT와 함께 전송되고 개인화된 필드는 각 MT에 대해 다른 값을 가질 수 있습니다.
표에는 각 메시지와 함께 보낼 선택적 매개 변수가 나와 있습니다. 열에는 다음 정보가 포함됩니다.
   * **레이블**: 자유 형식의 선택적 레이블입니다. 공급자에게 전송되지 않습니다. 매개 변수에 대한 텍스트 설명을 제공할 수 있습니다.
   * **태그**: 태그 값의 10진수 형식(예: 12345) 또는 0x 접두사가 있는 16진수 형식(예: 0x12ab). 태그는 0에서 65535 사이일 수 있습니다. SMPP 서비스 공급자에게 지원하는 태그를 요청하십시오.
   * **값**: 선택적 매개 변수를 전송할 값입니다. 이는 개인화된 필드입니다.
   * **형식**: 매개 변수에 사용된 인코딩입니다. 지원되는 텍스트 인코딩이나 가장 일반적인 이진 형식을 선택할 수 있습니다. SMPP 서비스 공급자에게 필요한 형식을 문의하십시오.
   * **최대 길이**: 이 매개 변수의 최대 바이트 수입니다. 이진 필드의 크기가 고정되어 있으므로 이진 필드에서는 무시됩니다.

* **[!UICONTROL Using binary formats for TLV]**

  Campaign에서는 TLV를 이진 형식으로 보낼 수 있습니다. 바이너리는 전송 숫자로 제한됩니다.

  개인화된 필드는 항상 텍스트를 출력하므로 개인화된 필드에는 숫자의 십진수 표현이 포함되어야 합니다(숫자만 포함된 경우에는 어떤 문자열이든 상관없다). 값은 서명되거나 서명될 수 있으며 개인화 엔진은 값을 올바른 이진 표시로 변환합니다.

  이진 형식을 사용할 때 특수 값 &#39;&#39;(빈 문자열), &#39;null&#39; 및 &#39;undefined&#39;는 오류를 표시하지 않고 필드를 완전히 비활성화합니다. 이 3가지 특별한 경우에는 태그가 전혀 전달되지 않습니다. 이렇게 하면 개인화 필드에서 정교하게 제작된 Javascript를 사용할 때 일부 메시지에 대해서만 특정 TLV를 전달할 수 있습니다.

  >[!NOTE]
  >
  >이진 형식은 항상 big-endian 형식으로 인코딩됩니다.

