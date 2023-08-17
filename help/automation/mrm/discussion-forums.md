---
product: campaign
title: 토론 포럼
description: Campaign 토론 포럼 사용 방법 알아보기
exl-id: c2336507-beea-4ddb-aa8c-1ec591eb5683
source-git-commit: 72fc29c49fca5767133be4a9927b57b3cfb51a14
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# 토론 포럼{#discussion-forums}

Adobe Campaign 운영자는 토론 포럼을 사용하여 정보를 공유할 수 있습니다. 계획, 프로그램, 캠페인, 마케팅 리소스, 시뮬레이션, 재고 요소에는 각각 고유한 포럼이 있습니다. 각 연산자에는 개인 포럼도 있습니다. 모든 토론은 개인적인 토론회에서도 공개적입니다.

운영자는 포럼에 가입하여 메시지가 게시될 때마다 알림 이메일을 받을 수 있습니다.

## 포럼 액세스 {#accessing-a-forum}

포럼에 액세스하려면 대시보드로 이동하여 **[!UICONTROL Forum]** 오른쪽 상단의 링크입니다.

![](assets/mrm-forum-icon.png)

메시지와 해당 응답이 최신 항목부터 오래된 항목까지 표시됩니다.

새 스레드를 시작하려면 **[!UICONTROL Add a discussion]** 단추를 클릭합니다. 다음 **[!UICONTROL Discussion forum]** 상자가 표시됩니다(아래 참조).

![](assets/mrm-forum-new-thread.png)


에 텍스트를 입력하십시오. **[!UICONTROL Message]** 필드 및 토론 제목 **[!UICONTROL Subject]** 필드.

이 포럼에 이미 메시지를 게시한 운영자는 기본적으로 알림을 받습니다. 통지할 추가 연산자를 선택할 수 있습니다. 여러 연산자에게 알리려면 연산자 그룹을 선택합니다.

다음을 사용하여 메시지에 첨부 파일을 추가할 수 있습니다.  **[!UICONTROL Browse...]** 단추를 클릭합니다. 첨부 파일도 알림 이메일에 포함됩니다. 첨부 파일은 개별적으로 보낼 수만 있습니다. 여러 파일을 보내려면 .zip 파일로 압축해야 합니다.

>[!CAUTION]
>
>메시지가 포럼에 게시되면 더 이상 변경하거나 삭제할 수 없습니다.

## 운영자의 개인 포럼에 게시 {#posting-to-the-personal-forum-of-an-operator}

연산자의 포럼에 메시지를 게시할 수 있습니다. 개인 포럼은 공개되며 모든 운영자가 귀하의 메시지를 볼 수 있습니다. 운영자는 누군가 개인 포럼에 게시할 때마다 이메일 알림을 받습니다.

운영자의 포럼에 액세스하려면 다음을 수행할 수 있습니다.

* 다음으로 이동 **[!UICONTROL Administration > Access management > Operators]** campaign 탐색기의 폴더에서 연산자를 선택하여 대시보드를 연 다음, **[!UICONTROL Forum]** 오른쪽 상단 모서리에 있는 링크입니다.
* Adobe Campaign UI에서 (이 운영자가 포럼에 게시한 메시지를 통해, 해당 운영자에게 할당된 작업) 운영자 이름을 찾고 이를 클릭하여 운영자 대시보드에 액세스합니다.

## 포럼 구독 {#subscribing-to-a-forum}

포럼에 가입하면 모든 토론을 따를 수 있습니다. 구독한 후에는 포럼에 메시지가 게시될 때마다 이메일 알림을 받게 됩니다.

메시지에 응답하려면 이메일 본문을 클릭한 다음 Adobe Campaign 웹 인터페이스에 로그인합니다.

* 포럼에 가입하려면 **[!UICONTROL Follow discussions]** 메시지 목록 위에 있는 오른쪽 상단 섹션의 단추입니다.

  섹션이 파란색으로 바뀌고 포럼에 가입했음을 보여 줍니다.

* 포럼에서 가입을 해지하려면 **[!UICONTROL Unsubscribe]** 단추를 클릭합니다.

* 개인 대시보드에는 구독 중인 포럼이 나열됩니다. 다음을 클릭합니다. **[!UICONTROL Subscription to discussion forums]** 링크를 클릭하여 목록을 표시한 다음, 원하는 항목을 클릭하여 해당 포럼에 액세스합니다.

  ![](assets/forum-subscribed.png)


## 알림 전달 문제 해결 {#checking-notification-delivery}

포럼을 구독한 운영자가 예상대로 알림을 받지 못하는 경우:

* 운영자의 프로필에 이메일 주소를 입력했는지 확인합니다.
* 다음으로 이동 **[!UICONTROL Administration > Production > Technical workflows > Campaign processes]** Campaign 탐색기 폴더 및 **[!UICONTROL Jobs in discussion forums]** 워크플로가 오류 없이 시작됩니다.
* 게재 로그 확인:

   * Adobe Campaign 홈페이지에서 다음 위치로 이동합니다. **[!UICONTROL Campaigns > Navigation > Deliveries]**&#x200B;을(를) 열고 **[!UICONTROL Discussion forum notification]** 게재.
   * Campaign 탐색기에서 **[!UICONTROL Administration > Production > Objects created automatically > Technical deliveries > Workflow notifications]**&#x200B;을 클릭한 다음 을 클릭합니다 **[!UICONTROL Discussion forum notifications]**.

  다음에서 **[!UICONTROL Discussion forum notifications]** 상자에서 게재 로그는 **[!UICONTROL Edit > Delivery]** 탭. 다음을 볼 수도 있습니다. **[!UICONTROL Tracking > Log]** 및 **[!UICONTROL Exclusion causes]** 탭.
