---
title: Adobe Campaign으로 DM 보내기
description: Campaign에서 DM 시작
feature: Overview
role: Data Engineer
level: Beginner
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: 5c1ced7972295e79418ac7ff14a6f0888e5ed39a
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 15%

---

# DM 게재 만들기

DM 게재를 사용하면 대상 모집단에 대한 데이터가 포함된 추출 파일을 생성할 수 있습니다. 그런 다음 대상 모집단에게 메시지를 전달할 공급자와 이 파일을 공유할 수 있습니다.

파일을 생성하는 단계는 다음과 같습니다.

1. 게재 만들기

   템플릿을 기반으로 DM 게재를 만듭니다. 을 복제하고 구성할 수 있습니다 **[!UICONTROL Deliver by direct mail (paper)]** 기본 제공 템플릿.

   ![](../assets/do-not-localize/book.png)자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html){target=&quot;_blank&quot;}를 참조하십시오

1. 대상자 정의

   수신자 프로필에는 이름과 우편 주소가 적어도 포함되어야 합니다.

   우편 주소는 계산된 필드입니다. 주소는 기본적으로 최대 6줄을 포함할 수 있습니다. 첫 번째 줄에는 이름과 성, 두 번째 줄에는 우편 주소(도로명 등), 마지막 줄에는 우편 번호 및 구/군/시가 들어갑니다.

   이름, ZIP/우편 번호 필드 및 도시/도시 필드가 비어 있지 않은 경우 주소가 완료된 것으로 간주됩니다.

   ![](../assets/do-not-localize/book.png)자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target=&quot;_blank&quot;}를 참조하십시오

1. 파일의 내용을 정의합니다

   추출 마법사를 사용하여 출력 파일로 내보낼 정보(열)를 정의합니다.

   ![](../assets/do-not-localize/book.png)자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html){target=&quot;_blank&quot;}를 참조하십시오

1. 게재 유효성 검사

   분석 결과와 출력 파일의 내용을 확인합니다.

   ![](../assets/do-not-localize/book.png)자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html){target=&quot;_blank&quot;}를 참조하십시오

   마케팅 캠페인 컨텍스트에서 추출 날짜에 추출 파일이 만들어집니다. 추출된 파일의 컨텐츠를 보거나, 승인하거나, 형식을 변경하고, 필요한 경우 추출을 다시 시작할 수 있습니다. 파일이 승인되면 라우터에 알림 이메일을 보낼 수 있습니다.

   ![](../assets/do-not-localize/book.png)자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html#approving-an-extraction-file){target=&quot;_blank&quot;}를 참조하십시오

1. 게재 시작

   추출 파일의 유효성을 검사했으면 를 클릭합니다 **게재 확인** 확인 메시지를 통해 게재를 시작할 수 있습니다.

   확인이 지정된 파일에서 데이터 추출을 시작합니다.

   마케팅 캠페인 컨텍스트에서 모든 승인이 부여되면 DM 게재가 추출 보류 중일 때 기본 구성에서 자동으로 시작되는 특수 워크플로우를 통해 추출 파일이 만들어집니다.

   ![](../assets/do-not-localize/book.png)자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html#starting-an-offline-delivery){target=&quot;_blank&quot;}를 참조하십시오
