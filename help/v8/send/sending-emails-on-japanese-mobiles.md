---
product: campaign
title: Adobe Campaign으로 일본어 모바일에서 이메일 보내기
description: 일본어 모바일에서 읽을 이메일을 구성, 디자인 및 전송하는 방법에 대해 알아봅니다
feature: Email, Email Design
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 02cca21f-b1ac-4ac2-9761-015f6c7f5567
source-git-commit: 3d562aab2f19b84aad8b484768bf19648145feb3
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 0%

---

# 일본어 모바일에서 이메일 보내기 {#sending-emails-on-japanese-mobiles}

## 일본어 모바일의 이메일 형식 {#email-formats-for-japanese-mobiles}

Adobe Campaign은 모바일에서 이메일에 대한 세 가지 특정 일본어 형식을 관리합니다. **Deco-mail**(DoCoMo 모바일), **Decore 메일**(Softbank 모바일) 및 **Decoration 메일**(KDDI AU 모바일). 이러한 형식에는 특정 코딩, 구조 및 크기 제한이 적용됩니다. [이 섹션](#limitations-and-recommendations)에서 제한 사항 및 권장 사항에 대해 자세히 알아보세요.

받는 사람이 이러한 형식 중 하나로 메시지를 올바르게 받으려면 해당 프로필에서 **[!UICONTROL Deco-mail (DoCoMo)]**, **[!UICONTROL Decore Mail (Softbank)]** 또는 **[!UICONTROL Decoration Mail (KDDI AU)]**&#x200B;을(를) 선택하는 것이 좋습니다.

![](assets/deco-mail_03.png)

그러나 **[!UICONTROL Email format]** 옵션을 **[!UICONTROL Unknown]**, **[!UICONTROL HTML]** 또는 **[!UICONTROL Text]**(으)로 두면 Adobe Campaign은 메시지가 올바르게 표시되도록 사용할 일본어 형식을 자동으로 검색합니다(전자 메일을 보낼 때).

이 자동 검색 시스템은 **[!UICONTROL Management of Email Formats]** 메일 규칙 집합에 정의된 사전 정의된 도메인 목록을 기반으로 합니다. 전자 메일 형식 관리에 대한 자세한 내용은 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/additional-configurations/email-deliverability.html?lang=ko#managing-email-formats)를 참조하세요.

## 제한 사항 및 권장 사항 {#limitations-and-recommendations}

일본 공급업체(Softbank, DoCoMo, KDDI AU)가 운영하는 모바일에서 읽을 이메일 전송에는 특정 수의 제한이 적용됩니다.

따라서 다음을 수행해야 합니다.

* JPEG 또는 GIF 형식의 이미지만 사용
* 10,000바이트보다 엄격히 낮은 텍스트 및 HTML 섹션으로 게재를 만듭니다(KDDI AU 및 DoCoMo의 경우).
* 총 크기(인코딩 전)가 100KB보다 작은 이미지 사용
* 메시지당 20개 이상의 이미지를 사용하지 않음
* 축소된 크기의 HTML 형식 사용(각 연산자에 대해 제한된 수의 태그를 사용할 수 있음)

>[!NOTE]
>
>메시지를 만들 때는 각 연산자에 대한 제한 사항을 고려해야 합니다. 해당 제품 설명서를 참조하십시오.


## 이메일 콘텐츠 테스트 {#testing-the-email-content}

### 메시지 미리 보기 {#previewing-the-message}

Adobe Campaign을 사용하면 메시지 형식이 일본어 모바일로 전송되도록 조정되었는지 확인할 수 있습니다.

콘텐츠를 정의하고 이메일 제목을 입력하면 메시지가 만들어질 때 표시와 서식을 확인할 수 있습니다.

콘텐츠 편집 창의 **[!UICONTROL Preview]** 탭에서 **[!UICONTROL More... > Deco-mail diagnostic]**&#x200B;을(를) 클릭하면 다음 작업을 수행할 수 있습니다.

* HTML 컨텐츠 태그가 일본어 형식 제한 사항을 준수하는지 확인합니다
* 메시지의 이미지 수가 형식에 지정된 제한을 초과하지 않는지 확인합니다(이미지 20개).
* 총 메시지 크기 확인(100kB 미만)

  ![](assets/deco-mail_06.png)

### 유형화 규칙 실행 {#running-typology-rule}

미리 보기 진단 외에 증명 또는 게재를 보낼 때 두 번째 검사를 수행합니다. 분석 중에 특정 유형화 규칙 **[!UICONTROL Deco-mail check]**&#x200B;이(가) 시작됩니다.

>[!IMPORTANT]
>
>이 유형화 규칙은 수신자 중 하나 이상이 **[!UICONTROL Deco-mail (DoCoMo)]**, **[!UICONTROL Decore Mail (Softbank)]** 또는 **[!UICONTROL Decoration Mail (KDDI AU)]** 형식의 전자 메일을 받도록 구성된 경우에만 실행됩니다.

이 유형화 규칙을 사용하면 게재가 일본어 연산자에 의해 정의된 [형식 제약 조건](#limitations-and-recommendations)을 준수하는지 확인할 수 있습니다. 특히 전자 메일의 전체 크기, HTML 및 텍스트 섹션의 크기, 메시지의 이미지 수, HTML 컨텐츠의 태그와 관련하여 그러합니다.

### 교정쇄 보내기 {#sending-proofs}

증명을 전송하여 게재를 테스트할 수 있습니다. 증명을 보낼 때 대체 주소를 사용하고 있다면 사용한 프로필의 이메일 형식에 해당하는 주소를 입력하십시오.

예를 들어, 이 프로필에 대한 이메일 형식이 **[!UICONTROL Decore Mail (Softbank)]**&#x200B;에 미리 정의된 경우 프로필 주소를 test@softbank.ne.jp으로 바꿀 수 있습니다.

![](assets/deco-mail_05.png)

## 메시지 보내기 {#sending-messages}

Campaign을 사용하여 일본어 이메일 형식으로 수신자에게 이메일을 보내려면 다음 두 가지 옵션을 사용할 수 있습니다.

* 일본어 수신자에 대해서만 배달 메시지를 만들고 다른 수신자에 대해 배달 메시지를 만듭니다. [이 섹션](#designing-a-specific-delivery-for-japanese-formats)을 참조하세요.
* 단일 게재를 만들면 Adobe Campaign에서 사용할 형식을 자동으로 검색합니다. [이 섹션](#designing-a-delivery-for-all-formats)을 참조하세요.

### 일본어 형식에 대한 특정 게재 디자인 {#designing-a-specific-delivery-for-japanese-formats}

두 개의 게재, 즉 일본어 모바일에서 읽을 수 있는 게재와 표준 이메일 형식을 사용하는 수신자용 게재를 포함하는 워크플로우를 만들 수 있습니다.

이렇게 하려면 워크플로우에서 **[!UICONTROL Split]** 활동을 사용하고 일본어 전자 메일 형식(Deco-mail, Decoration Mail 및 Decore Mail)을 필터링 조건으로 정의합니다.

![](assets/deco-mail_08.png)

![](assets/deco-mail_07.png)

### 모든 형식에 대한 게재 디자인 {#designing-a-delivery-for-all-formats}

Adobe Campaign에서 도메인(**[!UICONTROL Unknown]**, **[!UICONTROL HTML]** 또는 **[!UICONTROL Text]**(으)로 정의된 전자 메일 형식의 프로필)에 따라 형식을 동적으로 관리하는 경우 모든 수신자에게 동일한 게재를 보낼 수 있습니다.

일본어 모바일의 사용자에게 표준 수신자와 마찬가지로 메시지 연락처가 올바르게 표시됩니다.

>[!IMPORTANT]
>
>각 일본어 전자 메일 형식(데코 메일, 데코 메일 및 데코 메일)과 관련된 특수 기능을 준수해야 합니다. 제한 사항에 대한 자세한 내용은 [이 섹션](#limitations-and-recommendations)을 참조하세요.
