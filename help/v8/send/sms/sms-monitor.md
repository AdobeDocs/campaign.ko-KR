---
title: SMS 모니터링 및 추적
description: SMS 게재 모니터링 및 추적 정보
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 42be45db-3a90-4ad0-896d-f082afff1f8e
TQID: 'https://experienceleague.adobe.com/wETwv6lIEctnfT54WQjulzGxeCPo6lZDF-rxlwBtF4I'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: c4f3ffbf421621fa15b1b4d56480bd0ff9304254
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%
---
# SMS 모니터링 및 추적

마케팅 캠페인이 효율적인지 확인하려면 SMS 게재를 모니터링하는 것이 중요합니다.

다음은 게재를 보낸 후 발생하는 상황을 알고 있어야 하는 가능성입니다

## SMS 게재 대시보드 이해

게재 대시보드는 SMS에 대한 다양한 정보를 제공합니다.

대시보드에 액세스하려면 게재 목록에서 게재를 두 번 클릭합니다.

**[!UICONTROL Summary]** 탭에는 처리된 메시지 수 및 성공 횟수와 같은 기본 데이터가 있습니다.

![전송, 처리 및 성공률, 게재 상태 메시지가 포함된 SMS 게재 대시보드 요약 탭](assets/sms_summary.png){zoomable="yes"}

SMS를 보낸 후에는 변경 시 게재 콘텐츠에 대한 **[!UICONTROL SMS]** 탭에 더 이상 액세스할 수 없습니다.

**[!UICONTROL Delivery]** 탭에는 게재 로그에 대한 정보가 있습니다. 연락한 각 주소에 대해 SMS가 전송되었는지 여부를 확인할 수 있습니다

![연락한 각 주소에 대해 상태 및 이유와 함께 SMS 전송 여부를 표시하는 게재 탭 로그 목록](assets/sms_deliverylogs.png){zoomable="yes"}

**[!UICONTROL Exclusions]** 탭에서 일부 주소가 대상에서 제외되는 이유에 대한 자세한 내용을 볼 수 있습니다.

![이유(예: 차단 목록에 추가된 주소 또는 Double)가 있는 무시된 주소를 나열하는 배달 탭 제외 탭](assets/sms_exclusions.png){zoomable="yes"}

**[!UICONTROL Tracking]** 탭은 추적에 대한 것입니다. 다음은 SMS 콘텐츠에서 추적된 URL의 예입니다.

![SMS 콘텐츠에서 레이블, 유형 및 소스 URL과 함께 추적된 URL을 표시하는 추적 탭 URL 목록](assets/sms_trackinglogs.png){zoomable="yes"}

마지막으로, 게재를 시작하는 동안 모든 세부 정보가 포함된 **[!UICONTROL Audit]** 탭입니다.

![게재를 시작하는 동안 기록된 메시지를 나열하는 감사 탭 로그(날짜 및 메시지 열 포함)](assets/sms_audit.png){zoomable="yes"}

## SMS 오류 이해

SMS에 대한 실패 유형 및 실패 이유는 이메일과 동일합니다.

[게재 실패](../delivery-failures.md)에 대해 자세히 알아보고 특히 [SMS 격리](../delivery-failures.md#sms-quarantines)에 대해 자세히 알아보세요.
