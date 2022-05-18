---
title: Campaign을 Twitter과 함께 사용하기
description: Campaign 환경을 Twitter과 통합하는 방법을 알아봅니다
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 4%

---

# Campaign을 Twitter과 함께 사용하기{#tw-ac-ovv}

다음 **소셜 네트워크 관리(소셜 마케팅)** 모듈을 사용하면 Twitter을 통해 고객과 상호 작용할 수 있습니다. 이 기능을 사용하여 다음을 수행할 수 있습니다.

* 메시지 보내기 - Adobe Campaign Social Marketing을 사용하여 Twitter에 메시지를 게시합니다. 모든 팔로워에게 직접 메시지를 보낼 수도 있습니다.

* 새 연락처 수집 - Adobe Campaign Social Marketing을 사용하면 다음과 같은 새로운 연락처를 쉽게 확보할 수 있습니다. 사용자에게 연락하여 프로필 정보를 공유할지 여부를 묻습니다. Adobe Campaign이 수락하면 타겟팅 캠페인을 수행하고 가능한 경우 크로스 채널 전략을 구현할 수 있는 데이터를 자동으로 복구합니다.

![](../assets/do-not-localize/speech.png)  관리 Cloud Services 사용자로, [연락처 Adobe](../start/campaign-faq.md#support) twitter과 Campaign 연결 다음  **소셜 네트워크 관리(소셜 마케팅)** 모듈은 전용 패키지를 통해 사용자 환경에 설치해야 합니다.


twitter 계정에 트윗을 게시하도록 Adobe Campaign을 구성하려면 이러한 계정에 대해 Adobe Campaign에 대한 쓰기 액세스 권한을 위임하십시오. 방법은 다음과 같습니다.

1. twitter 계정 만들기
1. 증명을 전송할 테스트 Twitter 계정을 만듭니다
1. twitter 애플리케이션 만들기(Twitter 계정당 하나의 앱)
1. 에 대한 새 서비스 만들기 **[!UICONTROL Twitter]** (Twitter 계정당 하나의 서비스)

## twitter에서 테스트 계정 만들기 {#tw-test-account}

twitter 계정 외에 전송에 사용할 수 있는 개인 Twitter 계정을 만듭니다 [트윗 증명](../send/twitter.md#send-tw-proofs). 이렇게 하려면 아래 단계를 수행합니다:

1. 새 Twitter 계정을 만듭니다.
1. 계정 액세스  **설정**.
1. 찾아보기 **개인 정보 및 안전** 및 **대상 및 태깅** 그리고 **트윗 Protect** 선택 사항입니다. 트윗 및 기타 계정 정보는 사용자를 따르는 사용자만 볼 수 있습니다.

![](assets/social_tw_test_page.png)

## twitter 시 애플리케이션 만들기 {#create-an-app-on-twitter}

Adobe Campaign에서 Twitter 계정에 트윗을 게시할 수 있도록 Twitter 애플리케이션을 만듭니다.  이렇게 하려면 아래 단계를 수행합니다:

1. twitter 계정에 로그인합니다.
1. 연결 대상 [Twitter 개발자 포털](https://developer.twitter.com/en/apps).
1. 선택 **앱 만들기**.
1. twitter 도우미가 프로세스를 안내하도록 합니다.

   Adobe Campaign에서 계정에 트윗을 게시하도록 하려면 을(를) 편집합니다 **권한** 응용 프로그램의 탭을 선택하고 을 선택합니다 **읽기 및 쓰기** 대상 **액세스** 섹션을 참조하십시오. 에서 **설정** 탭에서 다음을 수행해야 합니다 **콜백 URL** 필드가 비어 있습니다.

   ![](assets/social_tw_app.png)

>[!NOTE]
>
>twitter 계정당 하나의 애플리케이션이 필요합니다. 따라서 테스트 계정에 증명을 보내려면 다른 테스트 애플리케이션을 만들어야 합니다.

## Campaign에서 Twitter 서비스 만들기 {#create-tw-service}

Campaign 인스턴스를 Twitter 계정에 연결하려면 **Twitter** Campaign에 대한 서비스 및 쓰기 액세스 권한을 위임 합니다.

설정을 입력하려면 Adobe Campaign 콘솔과 Twitter 계정 모두에 액세스해야 합니다.

1. 열기 **Twitter**, 및에서 [프로젝트 및 앱 페이지](https://developer.twitter.com/en/portal/projects-and-apps)에서 이전에 만든 앱을 선택합니다. 액세스 권한 **앱 권한**.

   ![](assets/social_tw_service.png)

   편집 **키 및 토큰** 탭을 사용하여 앱 세부 정보에 액세스합니다.

1. in **Adobe Campaign**&#x200B;로 이동하여 **[!UICONTROL Profiles and targets]** 탭을 선택하고 **[!UICONTROL Services and Subscriptions]** 링크
1. 새 서비스를 만듭니다.
1. 을(를) 선택합니다 **[!UICONTROL Twitter]** 유형.

   >[!NOTE]
   >
   >다음 **[!UICONTROL Synchronize subscriptions]** 옵션은 기본적으로 활성화되어 있습니다. 이 옵션은 Twitter 팔로워의 목록을 자동으로 복원하여 [직접 메시지 보내기](../send/twitter.md#direct-tw-messages). 동기화는 [전용 기술 워크플로우](#synchro-tw-accounts).

1. 서비스의 레이블과 내부 이름을 입력합니다.

   >[!CAUTION]
   >
   >다음 **[!UICONTROL Internal name]** 서비스 이름이 Twitter 계정의 이름과 정확히 같아야 합니다.

   설정을 확인하려면 다음을 수행할 수 있습니다.

   * **[!UICONTROL Save]** 버튼을 클릭합니다.
   * 서비스 개요에서 **Twitter** 방금 만든 서비스입니다.
   * 찾아보기 **[!UICONTROL Twitter page]** 탭: twitter 계정이 표시됩니다.

1. 기본적으로 팔로워는 **[!UICONTROL Visitors]** 폴더를 입력합니다. 에서 다른 위치를 선택할 수 있습니다 **[!UICONTROL Visitor folder]** 필드. [자세히 알아보기](../send/twitter.md#direct-tw-messages)

1. twitter 앱에서 의 콘텐츠를 복사합니다. **[!UICONTROL Consumer Key (API Key)]** 및 **[!UICONTROL Consumer Secret (API Secret)]** 필드에 붙여 넣습니다. **[!UICONTROL Consumer key]** 및 **[!UICONTROL Consumer secret]** 캠페인의 필드 **Twitter** 서비스.

1. twitter 앱에서 의 콘텐츠를 복사합니다. **[!UICONTROL Access Token]** 및 **[!UICONTROL Access Token Secret]** 필드에 붙여 넣습니다. **[!UICONTROL Access token]** 및 **[!UICONTROL Access token secret]** 캠페인의 필드 **Twitter** 서비스.

1. Campaign 클라이언트 콘솔에서 **[!UICONTROL Save]**. 이제 Adobe Campaign에 대한 쓰기 액세스 권한을 위임했습니다.


>[!NOTE]
>
>만들기 **Twitter** twitter 계정당 서비스. 따라서 테스트 계정에 증명을 보내려면 다른 테스트 서비스를 만들어야 합니다.

## twitter 계정 동기화 {#synchro-tw-accounts}

Campaign과 Twitter 간의 동기화는 전용 기술 워크플로우를 통해 관리됩니다. 이러한 워크플로우는 **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** 폴더를 입력합니다.

기본적으로 중지됩니다. 사용을 시작할 때 수동으로 시작해야 합니다 **소셜 마케팅** 모듈.

다음 **[!UICONTROL Twitter account synchronization]** 기술 워크플로우는 Adobe Campaign에서 Twitter 계정을 동기화합니다. 이 워크플로우는 직접 메시지를 보낼 수 있도록 Twitter 팔로워의 목록을 복구합니다. [자세히 알아보기](../send/twitter.md#direct-tw-messages)

기본적으로 이 워크플로우는 매주 목요일 오전 7:30에 트리거됩니다. 를 사용할 수 있습니다 **[!UICONTROL Execute pending task(s) now]** 이 통합을 구현할 때 언제든지 워크플로우를 시작할 수 있는 옵션입니다.  스케줄러를 편집하여 워크플로우 트리거 빈도를 변경할 수도 있습니다. 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/scheduler.html)를 참조하십시오{target=&quot;_blank&quot;}.

>[!CAUTION]
>
>twitter 구독자 목록을 복구하려면 **[!UICONTROL Twitter account synchronization]** 계정에 연결된 서비스에 대해 옵션을 선택해야 합니다. [자세히 알아보기](#create-tw-service)

팔로워는 특정 테이블에 저장됩니다. 방문자 테이블입니다. twitter 팔로워를 표시하려면 **[!UICONTROL Profiles and Targets > Visitors]**.

Adobe Campaign은 각 종동체에 대해 다음 정보를 저장합니다.

* **[!UICONTROL Origin]**: 소셜 네트워크 이름(Twitter)
* **[!UICONTROL External ID]**: 사용자 식별자
* **[!UICONTROL User name]**: 사용자의 계정 이름
* **[!UICONTROL Full name]**: 사용자 이름
* **[!UICONTROL Language]**: 사용자 언어
* **[!UICONTROL Number of friends]**: 팔로워 수
* **[!UICONTROL Time zone]**: 사용자 시간대
* **[!UICONTROL Verified]**: 이 필드는 사용자가 확인된 Twitter 계정을 가지고 있는지 여부를 나타냅니다

이 구성이 완료되면 트윗을 Twitter 계정에 게시하고 팔로워에게 직접 메시지를 보낼 수 있습니다. [자세히 알아보기](../send/twitter.md)
