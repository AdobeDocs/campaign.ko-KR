---
title: 추적 로그 액세스
description: 추적 로그에 액세스하고 해석하는 방법을 알아봅니다
feature: Monitoring
role: User
level: Beginner
exl-id: df494786-5950-4646-aa9c-4dde45845057
source-git-commit: 5b23be4cb8f0896d2482e525e416713b1a6c4514
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---

# 추적 로그 액세스 {#accessing-the-tracking-logs}

게재를 보내고 추적이 활성화되면 **[!UICONTROL Tracking]** 기술 워크플로우에서 추적 데이터를 검색합니다. 기본적으로 시간별로 실행됩니다.

## 수신자 프로필에서 추적 보기 {#recipient-tracking}

이 정보는 다음 예제와 같이 게재 대상의 받는 사람 프로필의 **[!UICONTROL Tracking]** 탭에 나타납니다.

![](assets/s_ncs_user_select_tracking_tab_from_recipient.png)

이 탭에는 다음을 포함하여 수신자가 추적하고 클릭한 모든 URL이 표시됩니다.

* 클릭한 URL
* 클릭 날짜 및 시간
* URL이 발견된 게재
* 기타 관련 추적 정보

이 정보를 필터링하고 정렬하여 수신자 행동을 분석하고 참여 패턴을 식별할 수 있습니다.

## 게재에서 추적 보기 {#delivery-tracking}

게재의 **[!UICONTROL Tracking]** 탭을 통해 추적 정보에 액세스할 수도 있습니다.

![](assets/s_ncs_user_select_tracking_tab_from_del.png)

이 탭에서 다음을 볼 수 있습니다.

* **[!UICONTROL Tracking statistics]**: 열기, 클릭 수 및 기타 추적 이벤트에 대한 개요를 제공합니다.
* **[!UICONTROL URLs and click streams]**: 클릭한 링크와 횟수를 표시합니다.
* **[!UICONTROL Hot clicks]**: 받는 사람이 메시지에서 클릭한 위치를 시각적으로 표시합니다.
* **[!UICONTROL Tracking logs]**: 상세한 개별 추적 레코드를 제공합니다.

## 추적 문제 해결 {#troubleshooting}

>[!NOTE]
>
>게재의 **[!UICONTROL Tracking]** 탭이 표시되지 않으면 추적이 활성화되지 않은 것입니다. 추적을 구성하는 방법에 대해 알아보려면 [이 섹션](tracked-links.md)을 참조하세요.

### 추적 기술 워크플로우 확인 {#check-tracking-workflow}

추적 데이터를 수집하려면 추적 기술 워크플로우가 실행 중이어야 합니다. **[!UICONTROL Administration > Production > Technical workflows]** 폴더에서 추적 기술 워크플로우를 찾을 수 있습니다.

워크플로우를 확인하려면:

1. **[!UICONTROL Tracking]** 워크플로 열기
1. 마지막 실행 날짜 확인
1. 워크플로우 로그에 오류가 없는지 확인합니다

워크플로우가 실행 중이 아니거나 오류가 있는 경우 시스템 관리자에게 문의하십시오.

## 추적 데이터 수집 확인

추적이 활성화된 게재를 보낸 후:

1. 추적 워크플로우가 실행될 때까지 기다립니다(기본적으로 매 시간).
1. 게재를 열고 **[!UICONTROL Tracking]** 탭으로 이동합니다.
1. 추적 데이터가 나타나는지 확인
1. 데이터가 표시되지 않으면 다음을 확인하십시오.
   * 게재 설정에서 추적이 활성화되었습니다.
   * 추적 기술 워크플로우가 실행 중입니다.
   * 수신자가 이메일을 열고 링크를 클릭함

## 관련 항목 {#related-topics}

* [추적된 링크를 구성하는 방법 알아보기](tracked-links.md)
* [추적 테스트 방법 알아보기](testing-tracking.md)
* [추적 보고서 이해](../reporting/delivery-reports.md#tracking-indicators)

