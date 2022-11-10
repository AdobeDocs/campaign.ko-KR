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

Adobe Campaign 운영자는 토론 포럼을 사용하여 정보를 공유할 수 있습니다. 다음 요소에는 각각 고유한 포럼이 있습니다. 계획, 프로그램, 캠페인, 마케팅 리소스, 시뮬레이션, 주식. 운영자마다 개인 포럼이 있습니다. 모든 토론은 공개적이고, 심지어 개인 포럼에서도 공개됩니다.

운영자는 메시지가 게시될 때마다 알림 이메일을 받기 위해 포럼에 가입할 수 있습니다.

## 포럼 액세스 {#accessing-a-forum}

포럼에 액세스하려면 대시보드로 이동하여 **[!UICONTROL Forum]** 오른쪽 위 모서리에 연결합니다.

![](assets/mrm-forum-icon.png)

메시지 및 응답 수가 가장 최근 메시지부터 가장 오래된 메시지까지 표시됩니다.

새 스레드를 시작하려면 **[!UICONTROL Add a discussion]** 오른쪽 상단 모서리의 단추. 다음 **[!UICONTROL Discussion forum]** 상자가 표시됩니다(아래 참조).

![](assets/mrm-forum-new-thread.png)


에 텍스트를 입력합니다. **[!UICONTROL Message]** 의 필드 및 토론 제목 **[!UICONTROL Subject]** 필드.

이 포럼에 이미 메시지를 게시한 운영자에게 기본적으로 알림이 표시됩니다. 알릴 추가 연산자를 선택할 수 있습니다. 여러 연산자에게 알리려면 연산자 그룹을 선택합니다.

메시지를 사용하여 메시지에 첨부 파일을 추가할 수 있습니다  **[!UICONTROL Browse...]** 버튼을 클릭합니다. 첨부 파일은 알림 이메일에도 포함됩니다. 첨부 파일은 개별적으로 보낼 수 있습니다. 여러 파일을 보내려면 .zip 파일로 압축해야 합니다.

>[!CAUTION]
>
>포럼에 메시지가 게시되면 더 이상 변경하거나 삭제할 수 없습니다.

## 연산자의 개인 포럼에 게시합니다. {#posting-to-the-personal-forum-of-an-operator}

연산자의 포럼에 메시지를 게시할 수 있습니다. 개인 포럼은 공개적이며 모든 운영자가 메시지를 볼 수 있습니다. 운영자가 개인 포럼에 게시할 때마다 이메일 알림을 받습니다.

운영자 포럼에 액세스하려면 다음을 수행할 수 있습니다.

* 다음 위치로 이동합니다. **[!UICONTROL Administration > Access management > Operators]** 캠페인 탐색기의 폴더에서 연산자를 선택하여 대시보드를 연 다음 **[!UICONTROL Forum]** 오른쪽 상단 모서리에 연결합니다.
* Adobe Campaign UI에서 운영자 이름(이 연산자가 포럼에 게시한 메시지를 통해, 할당되는 작업을 통해)을 찾고 운영자 대시보드에 액세스하려면 이 연산자를 클릭하십시오.

## 포럼 구독 {#subscribing-to-a-forum}

포럼에 가입하면 모든 토론을 따를 수 있습니다. 가입 후 포럼에 메시지가 게시될 때마다 이메일 알림을 받게 됩니다.

메시지에 답하려면 이메일 본문을 클릭한 다음 Adobe Campaign 웹 인터페이스에 로그인합니다.

* 포럼에 가입하려면 **[!UICONTROL Follow discussions]** 메시지 목록 위에 있는 오른쪽 상단 섹션에 있는 단추입니다.

   섹션이 파란색으로 표시되어 포럼에 가입했음을 보여줍니다.

* 포럼에서 구독을 취소하려면 **[!UICONTROL Unsubscribe]** 버튼을 클릭합니다.

* 개인 대시보드에 구독한 포럼이 나열됩니다. 을(를) 클릭합니다. **[!UICONTROL Subscription to discussion forums]** 링크를 클릭하여 목록을 표시한 다음 원하는 항목을 클릭하여 포럼에 액세스합니다.

   ![](assets/forum-subscribed.png)


## 알림 전달 문제 해결 {#checking-notification-delivery}

포럼에 가입한 운영자가 예상대로 알림을 받지 않는 경우:

* 이메일 주소를 운영자 프로필에 입력했는지 확인합니다.
* 다음 위치로 이동합니다. **[!UICONTROL Administration > Production > Technical workflows > Campaign processes]** campaign 탐색기의 폴더를 검색하고 **[!UICONTROL Jobs in discussion forums]** 오류 없이 워크플로우가 시작됩니다.
* 게재 로그를 확인합니다.

   * Adobe Campaign 홈페이지에서 **[!UICONTROL Campaigns > Navigation > Deliveries]**&#x200B;를 열고 **[!UICONTROL Discussion forum notification]** 게재.
   * Campaign 탐색기에서 **[!UICONTROL Administration > Production > Objects created automatically > Technical deliveries > Workflow notifications]**&#x200B;를 클릭한 다음 **[!UICONTROL Discussion forum notifications]**.
   에서 **[!UICONTROL Discussion forum notifications]** 상자에서 게재 로그는 **[!UICONTROL Edit > Delivery]** 탭. 또한 **[!UICONTROL Tracking > Log]** 그리고 **[!UICONTROL Exclusion causes]** 탭.
