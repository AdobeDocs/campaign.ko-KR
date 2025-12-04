---
title: 메시지 추적 시작
description: Adobe Campaign의 추적 기능에 대해 자세히 알아보기
feature: Monitoring, Email
role: User
level: Beginner
exl-id: f3de901f-519f-42ae-846c-f20c7cb560df
source-git-commit: 90ed82673b893b62a185227dd8cdfe80cc8f1455
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 3%

---

# 메시지 추적 시작 {#get-started-tracking}

추적 기능 덕분에 Adobe Campaign을 사용하면 보낸 메시지를 추적하고 열기, 링크 클릭, 구독 취소 등과 같은 수신자의 동작을 확인할 수 있습니다.

이 정보는 게재 받는 사람 프로필의 **[!UICONTROL Tracking]** 탭에서 검색됩니다. 이 탭에는 목록에서 선택한 수신자가 추적하고 클릭한 모든 URL 링크가 표시됩니다. 게재 화면에 여전히 존재하는 게재에서 추적된 모든 URL의 누적입니다. 목록을 구성할 수 있으며 일반적으로 에는 클릭한 URL, 클릭한 날짜 및 시간, URL이 발견된 문서가 포함됩니다.

**게재 대시보드**&#x200B;는 메시지를 보내는 동안 게재 및 잠재적인 문제를 모니터링하는 주요 도구이기도 합니다.

다음 다이어그램은 사용자와 여러 서버 간의 대화 단계를 보여 줍니다.

<img src="assets/tracking-diagram.png" width="70%">

>[!NOTE]
>
>추적 구성은 Adobe for Managed Cloud Services 배포에서 수행합니다.

## 메시지 추적 {#message-tracking}

**추적된 링크**

메시지 수신 및 메시지 콘텐츠에 삽입된 링크의 활성화를 추적하여 수신자의 동작을 더 잘 이해할 수 있습니다.

[추적된 링크에 대해 자세히 알아보기](tracked-links.md)

**URL 추적**

추적 옵션은 추적된 URL을 활성화하거나 비활성화하여 구성할 수 있습니다.

[URL 추적 옵션에 대해 자세히 알아보기](url-tracking.md)

**추적된 링크 개인화**

Campaign 추적 기능을 사용하면 개인화할 수 있고 추적을 지원하는 이메일에 링크를 추가할 수 있습니다.

[개인화된 링크 추적에 대해 자세히 알아보기](personalized-links.md)

**추적 로그**

**Tracking** 기술 워크플로우는 게재를 보내고 추적을 활성화하면 추적 데이터를 검색합니다. 이 데이터는 게재의 추적 탭에서 찾을 수 있습니다.

[추적 로그에 대해 자세히 알아보기](tracking-logs.md)

**추적 테스트**

추적을 사용하여 메시지를 보내기 전에 미러 페이지, 이메일 로그 및 링크에서 추적을 테스트할 수 있습니다.

[추적 테스트에 대해 자세히 알아보기](testing-tracking.md)

## 추적 보고서 {#tracking-reports}

**추적 통계**

이 보고서는 열기, 클릭 및 트랜잭션에 대한 통계를 제공하며 게재의 마케팅 영향을 추적할 수 있습니다.

[추적 보고서에 대해 자세히 알아보기](../reporting/delivery-reports.md#tracking-indicators)

**URL 및 클릭 스트림**

이 보고서는 게재 후 방문한 페이지 목록을 보여줍니다.

[URL 및 클릭 스트림에 대해 자세히 알아보기](../reporting/delivery-reports.md#urls-and-click-streams)

**개인/사용자 및 수신자**

이 예제를 통해 Adobe Campaign의 사용자/사용자와 수신자 간의 추적 차이를 더 잘 이해할 수 있습니다.

[Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/person-people-recipients.html#reporting){target="_blank"}에서 사용자 및 받는 사람에 대해 자세히 알아보세요.

**지표 추적**

이 보고서는 열기, 클릭스루 비율 및 클릭 스트림과 같은 게재 수신 시 수신자의 동작을 추적하기 위한 주요 지표를 결합합니다.

[지표 추적에 대해 자세히 알아보기](../reporting/delivery-reports.md#tracking-indicators)

**지표 계산**

다른 테이블은 배달 유형에 따라 다른 보고서에서 사용되는 지표 목록과 해당 계산 공식을 제공합니다.

[지표 계산에 대해 자세히 알아보기](../reporting/metrics-calculation.md)


