---
title: Adobe Campaign으로 DM 보내기
description: Campaign에서 DM 시작
feature: Direct Mail
role: User
level: Beginner
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 11%

---

# DM 게재 만들기

DM 게재는 대상 모집단에서 데이터를 포함하는 추출 파일을 생성할 수 있습니다. 그런 다음 이 파일을 대상 모집단에 메시지를 전달할 공급자와 공유할 수 있습니다.

파일을 생성하는 단계는 다음과 같습니다.

1. 게재 만들기

   템플릿을 기반으로 DM 게재를 만듭니다. 다음을 복제하고 구성할 수 있습니다. **[!UICONTROL Deliver by direct mail (paper)]** 기본 제공 템플릿입니다.

   자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html)를 참조하세요{target="_blank"}

1. 대상자 정의

   수신자 프로필에는 적어도 이름과 우편 주소가 포함되어야 합니다.

   우편 주소는 계산된 필드입니다. 주소는 기본적으로 최대 6줄을 포함할 수 있습니다. 첫 번째 줄에는 이름과 성, 다음 줄에는 우편 주소(도로명 등), 마지막 줄에는 우편 번호 및 구/군/시가 포함됩니다. 기본 계산된 postalAddress 필드의 정의는 nms:recipient 스키마에서 검토할 수 있습니다.

   이름, ZIP/우편 번호 필드 및 구/군/시 필드가 비어 있지 않으면 주소는 완료된 것으로 간주됩니다. 주소가 불완전한 수신자는 DM 게재에서 제외됩니다.

   자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)를 참조하세요{target="_blank"}

1. 파일 내용 정의

   추출 마법사를 사용하여 출력 파일로 내보낼 정보(열)를 정의합니다.

   자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html)를 참조하세요{target="_blank"}

1. 게재 유효성 검사

   분석 결과와 출력 파일의 내용을 확인합니다.

   자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html)를 참조하세요{target="_blank"}

   마케팅 캠페인의 컨텍스트에서 추출 날짜에 추출 파일이 만들어집니다. 추출된 파일의 컨텐츠를 보거나 승인하거나 형식을 변경하고 필요한 경우 추출을 다시 시작할 수 있습니다. 파일이 승인되면 알림 이메일을 라우터로 보낼 수 있습니다. [이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=ko)에서 자세히 알아보기

1. 게재 시작

   추출 파일의 유효성을 검사한 후 **게재 확인** 확인 메시지를 통해 게재를 시작할 수 있습니다.

   확인이 지정된 파일에서 데이터 추출을 시작합니다.

   마케팅 캠페인의 컨텍스트에서 모든 승인이 승인되면 DM 게재가 추출 보류 중일 때 기본 구성에서 자동으로 시작되는 특수 워크플로우를 통해 추출 파일이 만들어집니다. 다음에서 자세히 알아보기 [이 섹션](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=ko)
