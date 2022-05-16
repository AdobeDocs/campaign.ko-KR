---
title: 추적 및 모니터링 기능 시작
description: 추적 및 모니터링 기능 시작
feature: Overview
role: Data Engineer
level: Beginner
exl-id: f3de901f-519f-42ae-846c-f20c7cb560df
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 20%

---

# 메시지 추적 및 모니터링{#gs-ac-reports}

## Campaign의 추적 기능

캠페인 추적 기능은 전송된 메시지를 추적하고 수신자의 동작을 분석하는 데 도움이 됩니다. 열기, 링크, 구독/구독 취소 등에 대한 클릭 수. 전용 로그, 보고서 및 지표에 액세스하고 데이터베이스를 쿼리하여 수집된 데이터를 검토할 수 있습니다.

자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#tracking-tab){target=&quot;_blank&quot;}를 참조하십시오.

게재 대시보드는 메시지를 보내는 동안 게재 및 잠재적 문제를 모니터링하는 주요 도구입니다.

자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=en#sending-messages){target=&quot;_blank&quot;}.

Campaign에서 사용할 수 있는 주요 추적 기능은 아래에 나와 있습니다.

### 메시지 추적 {#message-tracking}

<img src="assets/do-not-localize/icon-message-tracking.svg" width="60px">

**추적된 링크**

메시지 수신 및 메시지 콘텐츠에 삽입된 링크의 활성화를 추적하여 수신자의 동작을 더 잘 이해할 수 있습니다.

[자세한 내용은 Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html?lang=en#sending-messages)를 참조하십시오{target=&quot;_blank&quot;}

**URL 추적**

추적된 URL을 활성화하거나 비활성화하여 추적 옵션을 구성할 수 있습니다.

[자세한 내용은 Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/personalizing-url-tracking.html?lang=en#sending-messages)를 참조하십시오{target=&quot;_blank&quot;}


**추적된 링크 개인화**

캠페인 추적 기능을 사용하면 개인화할 수 있고 추적을 지원하는 이메일에 링크를 추가할 수 있습니다.

[자세한 내용은 Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/tracking-personalized-links/tracking-personalized-links.html?lang=en#sending-messages)를 참조하십시오{target=&quot;_blank&quot;}

**추적 로그**

다음 **추적** 기술 워크플로우는 게재가 전송되고 추적이 활성화되면 추적 데이터를 검색합니다. 이 데이터는 게재의 추적 탭에서 찾을 수 있습니다.

[자세한 내용은 Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/accessing-the-tracking-logs.html?lang=en#sending-messages)를 참조하십시오{target=&quot;_blank&quot;}

**추적 테스트**

추적을 통해 메시지를 보내기 전에 미러 페이지, 이메일 로그 및 링크에서 추적을 테스트할 수 있습니다.

[자세한 내용은 Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/testing-tracking.html?lang=en#sending-messages)를 참조하십시오{target=&quot;_blank&quot;}

### 웹 애플리케이션 추적 {#web-application-tracking}

<img src="assets/do-not-localize/icon-web-app.svg" width="60px">

**웹 애플리케이션 추적**

추적 태그가 있는 웹 애플리케이션 페이지에서 방문을 추적하고 측정할 수도 있습니다. 이 기능은 양식 및 온라인 설문 조사와 같은 모든 웹 응용 프로그램 유형에 사용할 수 있습니다.

[자세한 내용은 Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/tracking-a-web-application.html?lang=en#designing-content)를 참조하십시오{target=&quot;_blank&quot;}

**웹 애플리케이션 추적 옵트아웃**

웹 애플리케이션 추적 옵트아웃을 사용하면 행동 추적을 옵트아웃하는 최종 사용자의 웹 행동 추적을 중지할 수 있습니다. 사용자가 옵트아웃할 수 있도록 웹 애플리케이션이나 랜딩 페이지에 배너를 표시하는 기능을 포함할 수 있습니다.

[자세한 내용은 Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/web-application-tracking-opt-out.html?lang=en#designing-content)를 참조하십시오{target=&quot;_blank&quot;}

### 보고서 추적 {#tracking-reports}

<img src="assets/do-not-localize/icon_monitor.svg" width="60px">

**통계 추적**

이 보고서는 열기, 클릭 및 트랜잭션에 대한 통계를 제공하며, 게재의 마케팅 영향을 추적할 수 있도록 해줍니다.

[자세한 내용은 Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/about-message-tracking.html?lang=en#tracking-reports)를 참조하십시오{target=&quot;_blank&quot;}

**URL 및 클릭 스트림**

이 보고서는 게재 후 방문한 페이지 목록을 보여줍니다.

[자세한 내용은 Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=en#urls-and-click-streams)를 참조하십시오{target=&quot;_blank&quot;}

**개인/사용자 및 수신자**

이 예제를 사용하여 Adobe Campaign의 개인/사람과 수신자 간의 추적 차이를 더 잘 이해합니다.

[자세한 내용은 Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/person-people-recipients.html?lang=en#reporting)를 참조하십시오{target=&quot;_blank&quot;}

**지표 추적**

이 보고서는 열기, 클릭스루 비율 및 클릭 스트림과 같은 게재를 받을 때 수신자의 동작을 추적하기 위한 주요 지표를 결합합니다.

[자세한 내용은 Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=en#reporting)를 참조하십시오{target=&quot;_blank&quot;}

**지표 계산**

다른 테이블에서는 게재 유형에 따라 다른 보고서에서 사용된 지표 목록과 계산 공식을 제공합니다.

[자세한 내용은 Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/indicator-calculation.html?lang=en#reporting)를 참조하십시오{target=&quot;_blank&quot;}

## 모니터링 지침

Adobe Campaign은 프로세스와 환경을 모니터링하는 기능 세트를 제공합니다.

### 게재 모니터링

메시지를 게재한 후 마케팅 캠페인이 효율적이고 고객에게 도달하는지 확인하는 데 있어 게재 모니터링은 중요한 단계입니다.

게재를 보낸 후 모니터링할 수 있는 정보에 대해 자세히 알아보고 게재 실패 및 격리를 관리하는 방법을 이해합니다 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages){target=&quot;_blank&quot;}

### 워크플로우 모니터링

에서 워크플로우 실행을 모니터링하는 방법을 알아봅니다.  [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html?lang=en#automating-with-workflows){target=&quot;_blank&quot;}

### 인스턴스 모니터링

인스턴스 모니터링 지침은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/introduction/monitoring-guidelines.html?lang=en#monitoring-campaign-classic){target=&quot;_blank&quot;}

감사 추적 셀프 서비스 인터페이스를 사용하여 인스턴스 내에서 수행된 변경 사항을 모니터링합니다. 감사 추적은 Adobe Campaign 인스턴스 내에서 발생하는 작업 및 이벤트의 포괄적인 목록을 실시간으로 캡처합니다. 데이터 기록에 액세스하여 다음과 같은 질문에 답변할 수 있습니다. 워크플로우가 어떻게 되었고 마지막으로 업데이트한 사람 또는 인스턴스에서 사용자가 수행한 작업이 변경되었습니다.

의 감사 추적에 대해 자세히 알아보십시오  [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/audit-trail.html?lang=en#accessing-audit-trail){target=&quot;_blank&quot;}
