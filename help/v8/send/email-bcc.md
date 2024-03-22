---
title: BCC 주소로 메시지 사본 보내기
description: Adobe Campaign에서 이메일 BCC를 활성화하는 방법 알아보기
feature: Email
role: User
level: Beginner
exl-id: 35702b81-1984-4a62-8f00-c2bc32ab2b42
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 1%

---

# BCC 주소로 메시지 사본 보내기 {#bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

## 이메일 BCC 정보 {#gs-bcc}

플랫폼에서 전송된 이메일 사본을 유지하도록 Adobe Campaign을 구성할 수 있습니다. 이 옵션을 사용하면 외부 시스템을 사용하여 메시지를 처리하고 보관할 수 있는 전용 BCC(숨은 참조) 이메일 주소로 메시지를 보낼 수 있습니다.
Adobe Campaign 자체는 보관된 파일을 관리하지 않습니다. 보낸 이메일에 해당하는 .eml 파일은 SMTP 이메일 서버와 같은 원격 서버로 전송할 수 있습니다.

보관 대상은 선택한 BCC 이메일 주소이며 게재 수신자에게 표시되지 않습니다. BCC 이메일 주소가 정의되면 [게재 템플릿](create-templates.md) 레벨.

>[!NOTE]
>
>관리 Cloud Service 사용자는 [연락처 Adobe](../start/campaign-faq.md#support){target="_blank"} 보관에 사용할 BCC 이메일 주소를 전달합니다.

>[!CAUTION]
>
>개인정보 보호를 위해 BCC 이메일은 PII(개인 식별 정보)를 안전하게 저장할 수 있는 보관 시스템에 의해 처리되어야 합니다.


## 이메일 BCC 활성화 {#enable-bcc}

특정 숨은 참조를 활성화하려면 [게재 템플릿](create-templates.md)을(를) 클릭하고 아래 단계를 수행합니다.

1. 캠페인 탐색기에서 게재 템플릿 폴더를 찾습니다. 기본적으로 게재 템플릿은에 저장됩니다 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** 폴더를 삭제합니다.
1. BCC로 업데이트할 게재 템플릿을 편집합니다.
1. **[!UICONTROL Properties]** 버튼을 클릭합니다.
1. 다음에서 **[!UICONTROL Delivery]** 탭에서 다음을 확인합니다 **[!UICONTROL Email BCC]** 옵션을 선택합니다.

   ![](assets/email-bcc.png)

1. **[!UICONTROL Ok]**&#x200B;을(를) 클릭하여 확인합니다.

이 템플릿을 기반으로 각 게재에 대해 전송된 모든 메시지의 사본은 플랫폼에 대해 구성된 이메일 BCC 주소로 전송됩니다.

## 보호 및 권장 사항 {#recommendations-bcc}

Adobe Campaign에서 이메일 BCC를 사용할 때 다음 보호 기능 및 권장 사항이 적용됩니다.

* 숨은 참조 이메일 주소는 하나만 사용할 수 있습니다.

* BCC 주소에 전송된 모든 이메일을 보관할 수 있는 수신 용량이 충분한지 확인합니다.

* 이메일 BCC <!--with Enhanced MTA--> 는 수신자에게 전달하기 전에 BCC 이메일 주소에 전달합니다. 그러면 원래 게재가 반송되었더라도 BCC 메시지가 전송될 수 있습니다. 바운스에 대한 자세한 내용은 [게재 실패 이해](delivery-failures.md).

* BCC 주소로 전송된 이메일은 의 활동으로 간주되므로 열고 클릭할 수 없습니다. **[!UICONTROL Total opens]** 및 **[!UICONTROL Clicks]** 전송 분석에서 이 잘못 계산될 수 있습니다.

<!--Only successfully sent emails are taken in account, bounces are not.-->
