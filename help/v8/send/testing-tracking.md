---
title: 메시지 추적 테스트
description: 게재를 보내기 전에 메시지 추적을 테스트하는 방법을 알아봅니다
feature: Monitoring
role: User
level: Beginner
exl-id: 16ad36b7-c13e-4b77-86ca-41c9ef174172
source-git-commit: edbe7ab49a628436dfb4d27ae17122917d7371e9
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 1%

---

# 메시지 추적 테스트 {#testing-tracking}

게재를 전체 대상자에게 보내기 전에 추적 기능을 테스트하여 모든 링크가 올바르게 작동하고 추적 데이터가 제대로 캡처되는지 확인해야 합니다. 이 확인 프로세스를 사용하면 캠페인이 시작되기 전에 추적 문제를 식별하고 수정하여 링크 리디렉션, 추적 픽셀 로드 또는 데이터 수집과 관련된 잠재적 문제를 방지할 수 있습니다.

테스트 추적을 통해 다음을 수행할 수 있습니다.

* 메시지의 모든 링크가 올바르게 추적되고 제대로 리디렉션되는지 확인
* 미러 페이지 링크가 작동 및 추적되는지 확인합니다.
* 열린 추적을 위해 추적 픽셀이 올바르게 로드되는지 확인합니다.
* URL의 개인화된 매개 변수가 정확하게 캡처되는지 확인
* 추적 기술 워크플로우가 데이터를 올바르게 처리하는지 확인

아래 단계에 따라 미러 페이지, 이메일 로그 및 링크에 대한 추적을 테스트할 수 있습니다.

## 1단계: 테스트 게재 만들기 {#create-test-delivery}

1. 테스트에 사용할 새 이메일 게재를 만듭니다. [게재 만드는 방법 알아보기](../start/create-message.md)
1. 추적할 링크를 사용하여 이메일 콘텐츠를 디자인합니다. [전자 메일 콘텐츠 디자인에 대해 알아보기](defining-the-email-content.md)
1. 이메일 콘텐츠에 미러 페이지 개인화 블록을 추가합니다. [개인화 블록에 대해 알아보기](personalization-blocks.md)

   ![](assets/mirror-page-insert.png)

1. 이메일을 받을 사용자를 지정합니다. 이 사용자는 이메일을 열고 이메일에 포함된 링크를 클릭해야 하므로 제어할 테스트 수신자 주소를 선택해야 합니다. [테스트 프로필에 대해 알아보기](../audiences/test-profiles.md)

## 2단계: 테스트 게재 보내기 {#send-test}

1. 게재 설정에서 추적이 활성화되었는지 확인합니다.
   * 게재의 **[!UICONTROL Properties]** 열기
   * **[!UICONTROL Tracking & Images]** 섹션으로 이동
   * **[!UICONTROL Activate tracking]**&#x200B;이(가) 선택되었는지 확인
   * 열기를 추적하려면 **[!UICONTROL Opens tracking]**&#x200B;을(를) 선택해야 합니다.

   ![](assets/s_ncs_user_email_del_tracking_param.png)

[URL 추적 옵션에 대해 자세히 알아보기](url-tracking.md)

1. 테스트 수신자에게 게재를 보냅니다. [게재 전송에 대해 알아보기](configure-and-send.md)

## 3단계: 추적 기능 확인 {#verify-tracking}

1. 이메일을 수신하면 페이지를 열고 미러 페이지 링크를 클릭합니다. [미러 페이지에 대해 알아보기](mirror-page.md)
1. 이메일의 다양한 링크를 클릭하여 추적 데이터를 생성합니다.
1. 미러 페이지로 올바르게 리디렉션되면 **[!UICONTROL Administration > Production > Technical workflows]** 폴더에 액세스합니다. [워크플로에 대해 알아보기](../config/workflows.md)
1. **[!UICONTROL Tracking]** 워크플로를 엽니다.
1. 워크플로우를 시작하거나 **[!UICONTROL Scheduler]** 활동을 마우스 오른쪽 단추로 클릭하고 **[!UICONTROL Execute pending task now]**&#x200B;을(를) 선택합니다.
1. 워크플로우가 추적 로그를 처리할 때까지 약 30초 정도 기다립니다.
1. 워크플로우의 **[!UICONTROL Audit]** 탭을 선택합니다. 하나 이상의 추적 로그 레코드가 있는지 확인하십시오. 새 로그가 표시되지 않으면 **[!UICONTROL Refresh]**&#x200B;을(를) 클릭합니다.

1. 게재에서 추적 로그 확인:
   * 게재로 돌아가기
   * **[!UICONTROL Tracking]** 탭 선택
   * 클릭한 URL 및 기타 추적 이벤트와 함께 추적 로그 목록이 표시되는지 확인합니다

   ![](assets/s_ncs_user_delivery_tracking_tab.png)

## 4단계: 수신자 추적 탭 확인 {#check-recipient-tracking}

1. 테스트에 사용한 수신자의 프로필 페이지로 이동합니다. [프로필 보기에 대해 알아보기](../audiences/view-profiles.md)
   * 기본적으로 받는 사람의 프로필 페이지가 **[!UICONTROL Profiles and Targets > Recipients]** 폴더에 있습니다.

1. **[!UICONTROL Tracking]** 탭을 선택합니다. [추적 로그에 대해 자세히 알아보기](tracking-logs.md)

   ![](assets/s_ncs_user_select_tracking_tab_from_recipient.png)

1. 추적 레코드가 다음과같이 표시되는지 확인합니다.
   * **[!UICONTROL Mirror Page]** 열의 **[!UICONTROL Type]** 값
   * 전자 메일 열기에 대한 **[!UICONTROL Open]** 열의 **[!UICONTROL Type]** 값
   * 링크 클릭에 대한 **[!UICONTROL Email click]** 열의 **[!UICONTROL Type]** 값

## 추적 테스트 문제 해결 {#troubleshooting-tracking-test}

추적 로그가 표시되지 않는 경우:

1. **게재 설정 확인**: 게재로 이동하여 **[!UICONTROL Properties]**&#x200B;에 액세스하여 **[!UICONTROL Activate tracking]** 및 **[!UICONTROL Opens tracking]** 옵션이 모두 선택되었는지 확인합니다. [URL 추적 옵션에 대해 자세히 알아보기](url-tracking.md)

1. **추적 워크플로우를 확인**: **[!UICONTROL Tracking]** 기술 워크플로우가 오류 없이 실행되고 있는지 확인하십시오. [추적 워크플로우 문제 해결에 대해 알아보기](tracking-logs.md#check-tracking-workflow)

1. **URL 형식 확인**: URL의 형식이 올바르고 구분 기호로 묶여 있는지 확인하십시오. [추적된 링크 구성에 대한 자세한 정보](tracked-links.md)

1. **전자 메일 클라이언트 동작 검토**: 일부 전자 메일 클라이언트는 추적 픽셀을 차단하거나 링크를 수정할 수 있습니다. 다른 이메일 클라이언트로 테스트해 보십시오. [게재 모범 사례에 대해 알아보기](../start/delivery-best-practices.md)

1. **처리 대기**: 추적 워크플로는 기본적으로 매시간 실행됩니다. 수동으로 트리거하는 경우 결과를 확인하기 전에 처리에 필요한 충분한 시간을 허용합니다. [추적 로그에 대해 자세히 알아보기](tracking-logs.md)

## 관련 항목 {#related-topics}

* [추적된 링크를 구성하는 방법 알아보기](tracked-links.md)
* [추적 로그에 액세스하는 방법 알아보기](tracking-logs.md)
* [추적 보고서 이해](../reporting/delivery-reports.md#tracking-indicators)

