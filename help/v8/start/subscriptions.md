---
solution: Campaign v8
product: Adobe Campaign
title: Campaign에서 구독 및 구독 취소 관리
description: Campaign v8에서 구독 및 구독 취소를 관리하는 방법을 알아봅니다
feature: 개요
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 0%

---

# 구독 및 구독 취소 관리{#optin-optout}

Adobe Campaign을 사용하여 뉴스레터와 같은 정보 서비스를 만들고 모니터링하고 이러한 서비스에 대한 구독/구독을 관리합니다. 다음과 같이 여러 서비스를 동시에 정의할 수 있습니다.특정 제품 카테고리, 테마 또는 웹 사이트의 영역에 대한 전문가 뉴스레터, 다양한 유형의 경고 메시지에 대한 구독 및 실시간 알림입니다. 구독 관리를 참조하십시오.

:arrow_upper_right:[Campaign Classic v7 설명서에서 정보 서비스를 만들고, 뉴스레터를 보내고, 옵트인 및 옵트아웃을 관리하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html)

프로필을 서비스에 구독(옵트인)하려면 다음 옵션을 사용할 수 있습니다.

* 수신자 프로필에 서비스를 수동으로 추가합니다.이렇게 하려면 해당 프로필의 **[!UICONTROL Subscriptions]** 탭에서 **[!UICONTROL Add]** 을(를) 클릭하고 관련 정보 서비스를 선택합니다.

   :arrow_upper_right:자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab)를 참조하십시오

* 서비스에 수신자 집합을 자동으로 구독합니다. 수신자 목록은 필터링 작업, 그룹, 폴더, 가져오기 또는 직접 수동 선택에서 가져올 수 있습니다. 이러한 수신자를 구독하려면 프로필을 선택하고 마우스 오른쪽 단추를 클릭합니다. **[!UICONTROL Actions > Subscribe selection to a service...]** 을 선택하고 관련 서비스를 선택한 다음 작업을 시작합니다.

   :arrow_upper_right:자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab)를 참조하십시오


* 수신자를 가져와 정보 서비스에 자동으로 구독합니다. 이렇게 하려면 가져오기 마법사의 마지막 단계에서 관련 서비스를 선택합니다.

   :arrow_upper_right:자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=en#step-5---additional-step-when-importing-recipients)를 참조하십시오

* 수신자가 서비스에 가입할 수 있도록 웹 양식을 사용하십시오.

   :arrow_upper_right:자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=en#create-a-subscription--form-with-double-opt-in)를 참조하십시오


* 타겟팅 워크플로우를 만들고 **[!UICONTROL Subscription service]** 활동을 사용합니다.

   :arrow_upper_right:자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/subscription-services.html?lang=en#example--subscribe-a-list-of-recipients-to-a-newsletter)를 참조하십시오


서비스에서 프로필을 구독 취소(옵트아웃)하려면 다음 옵션을 사용할 수 있습니다.

**수동 구독 취소**

* 개인화된 구독 취소 링크 또는 웹 양식
* 정보 서비스 수동 삭제
* 특정 구독 서비스에서 수신자의 수동 삭제

**자동 구독 취소**

* 정보 서비스의 기간 제한을 지정합니다.유효 기간이 만료되면 수신자는 자동으로 가입 해지됩니다. 이 기간은 서비스 속성의 편집 탭에 지정됩니다. 그것은 일 단위로 표시된다.
* 모집단에 대한 구독 취소 워크플로우 설정

:arrow_upper_right:자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=en#unsubscribing-a-recipient-from-a-service)를 참조하십시오


>[!CAUTION]
>
>구독 및 구독 취소는 **비동기** 프로세스입니다. 옵트인 및 옵트아웃 요청은 매 시간 처리됩니다. [자세히 알아보기](../dev/new-apis.md#sub-apis)

게재 수신자가 메시지를 친구에게 전달하도록 설정할 수도 있습니다. 이렇게 하려면 관련 링크를 게재에 삽입합니다. 그런 다음 이 공유 프로세스와 관련 페이지에 대한 방문 수를 추적할 수 있습니다.

:arrow_upper_right:이 기능에 대한 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html?lang=en#viral-marketing--forward-to-a-friend)를 참조하십시오.