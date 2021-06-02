---
product: Adobe Campaign
title: campaign 자동화 시작
description: campaign 자동화 시작
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 40b38168a3704f171f1f389e2d232e6a2c6f1d85
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 프로세스 관리 및 자동화

강력한 마케팅 캠페인 자동화 기능을 활용하도록 Campaign을 구성합니다.

다음을 설정할 수 있습니다.

* 워크플로우
* 반복 캠페인
* 종단 간 유효성 검사 주기
* 경고
* 자동 보고서 전송
* 트리거된 이벤트

## 워크플로우 디자인 및 사용{#gs-ac-wf}

Adobe Campaign 워크플로우를 사용하여 세그먼트 만들기 및 메시지 준비에서 게재에 이르기까지 마케팅 캠페인의 모든 측면에 대한 속도와 크기를 향상시킬 수 있습니다.

이러한 [엔드 투 엔드 사용 사례](#end-to-end-uc)에서 워크플로우를 디자인하는 방법을 배웁니다.

워크플로우 사용자 인터페이스 및 Campaign Classic v7 설명서의 실행에 대해 자세히 알아보십시오.

[!DNL :arrow_upper_right:]  [워크플로우 시작](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)
* 워크플로우 활동:
   * [타겟팅 활동](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html):쿼리, 읽기 목록, 데이터 보강, 결합 등
   * [흐름 제어 활동](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html):스케줄러, 포크, 경고, 외부 신호 등
   * [작업 활동](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html):크로스 채널 게재, Javascript 코드, CRM 활동, 업데이트 집계 등
   * [이벤트 활동](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html):파일 전송, 웹 다운로드 등
      [!DNL :arrow_upper_right:]  [마케팅 캠페인 워크플로우에서 대상 만들기](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)

      [!DNL :arrow_upper_right:]  [워크플로우 모범 사례](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html)
      [!DNL :arrow_upper_right:] [기본 제공 기술 워크플로우](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)
      [!DNL :arrow_upper_right:] [워크플로우 실행 모니터링](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html)


## 반복 캠페인 설정

반복 워크플로우를 디자인하고 워크플로우를 실행할 때마다 새 게재 인스턴스를 만듭니다. 예를 들어 워크플로우가 일주일에 한 번 실행되도록 디자인된 경우 1년 후 52개의 게재가 발생합니다. 즉, 로그는 각 게재 인스턴스별로 분리됩니다.

[!DNL :arrow_upper_right:]  [Campaign Classic v7 설명서에서 반복 캠페인을 만드는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns).


## 트리거 이벤트 활용

캠페인 트랜잭션 메시지를 사용하여 정보 시스템에서 트리거된 이벤트에서 생성된 메시지를 자동화합니다. 이러한 트랜잭션 메시지는 예를 들어 송장, 주문 확인, 배송 확인, 암호 변경, 제품 비가용성 알림, 계정 명세서 또는 웹 사이트 계정 생성일 수 있습니다. 이러한 메시지는 개별적으로 또는 이메일, SMS 또는 푸시 알림을 통해 일괄적으로 전송할 수 있습니다.

[!DNL :bulb:] 트랜잭션 메시지 기능에 대한 자세한 내용은  [이 섹션](../send/transactional.md)을 참조하십시오.

Adobe Campaign 및 Adobe Analytics을 연결하여 사용자 작업을 검색하고 거의 실시간으로 개인화된 메시지를 전송할 수 있습니다.

[!DNL :bulb:] 이 섹션에서 Campaign을 다른 솔루션과 통합하는  [방법을 알아봅니다](../start/connect.md)


## 워크플로우 종단 간 사용 사례{#end-to-end-uc}

이 섹션에서는 Campaign 워크플로우 기능을 활용하는 다양한 사용 사례를 찾을 수 있습니다. 이러한 사용 사례는 Adobe Campaign Classic v7에 구축되었으며 Adobe Campaign v8에 적용됩니다.

### 게재 {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

* [A/B 테스트](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html)

   타겟팅 워크플로우를 통해 두 개의 이메일 게재 콘텐츠를 비교하는 방법을 알아봅니다. 메시지와 텍스트는 두 게재에서 동일합니다.레이아웃만 변경됩니다. 타겟팅된 모집단은 다음 세 개로 나누어집니다.두 개의 테스트 그룹과 나머지 모집단. 각 테스트 그룹에 다른 버전의 게재가 전송됩니다.

* [생일 전자 메일 보내기](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html)

   이 사용 사례에서는 생일 날짜의 수신자 목록에 반복 이메일을 전송하는 방법을 설명합니다.

* [게재 콘텐츠 로드](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)

   원격 서버에 있는 HTML 파일에서 게재 콘텐츠를 사용할 수 있는 경우 이 콘텐츠를 Adobe Campaign 게재에 쉽게 로드할 수 있습니다.

* [크로스 채널 게재 워크플로우](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/cross-channel-delivery-workflow.html)

   크로스 채널 게재 워크플로우를 구축하는 방법을 알아봅니다. 목표는 데이터베이스의 수신자로부터 대상자를 다른 그룹으로 세분화하고 첫 번째 그룹에는 전자 메일을 보내고 다른 그룹에는 SMS를 보내는 것입니다.

* [사용자 지정 날짜 필드를 사용한 전자 메일 강화](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html)

   이번 달에 생일을 맞는 프로필에 사용자 정의 데이터 필드가 포함된 이메일을 보내는 방법을 알아봅니다. 이메일에는 생일 1주 전후에 유효한 쿠폰이 포함됩니다.

* [콘텐츠 만들기, 에디션 및 게시 자동화](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html)

   Campaign 콘텐츠 관리 추가 기능을 사용하여 콘텐츠 블록 만들기 및 전달을 자동화하는 방법을 알아봅니다.


### 모니터링 {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [목록으로 보고서 보내기](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html)

   월별 기본 제공 추적 지표 보고서를 PDF 형식으로 생성하여 Campaign 운영자 목록으로 보내는 방법을 알아봅니다.

* [워크플로우 관리](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html)

   &quot;일시 중지됨&quot;, &quot;중지됨&quot; 또는 &quot;오류 발생&quot;인 워크플로우 집합의 상태를 모니터링할 수 있는 워크플로우를 만드는 방법을 알아봅니다.

* [운영자에게 개인화된 경고 보내기](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-personalized-alerts-to-operators.html)

   Newsletter를 열었지만 Newsletter에 포함된 링크를 클릭하지 않은 프로필의 이름을 포함하는 운영자에게 경고를 보내는 방법을 알아봅니다.

### 데이터 관리 {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [데이터 업데이트 조정](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/coordinating-data-updates.html)

   다른 업데이트 작업을 실행하기 전에 업데이트 프로세스가 종료되었는지 확인하는 방법을 알아봅니다. 이렇게 하려면 인스턴스 변수를 설정하고, 인스턴스가 실행 중인지 워크플로우 테스트를 통해 워크플로우 실행을 계속 진행할지 여부를 결정하고 업데이트를 수행합니다.

* [요약 목록 만들기](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/creating-a-summary-list.html)

   파일을 수집한 후 여러 가지 추가 작업을 수행한 후 요약 목록을 만들 수 있는 워크플로우를 만드는 방법을 알아봅니다. 이 예제에서는 스토어에서 구입한 연락처 목록을 기반으로 합니다.

* [데이터 강화](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html)

   점수에 따라 최신 경쟁에 참여한 프로필에 개인화된 게재를 보내는 방법을 알아봅니다.

* [집계 사용](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/using-aggregates.html)

   데이터베이스에 추가된 마지막 수신자를 식별하는 방법을 알아봅니다.

* [증분 쿼리를 사용한 분기별 목록 업데이트](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/quarterly-list-update.html)

   증분 쿼리를 사용하여 수신자 목록을 자동으로 업데이트하는 방법을 알아봅니다.

* [반복 가져오기 워크플로우 설정](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/recurring-import-workflow.html)

   Adobe Campaign 데이터베이스의 CRM에 있는 프로필을 가져올 때 다시 사용할 수 있는 워크플로우를 디자인하는 방법을 알아봅니다.

### {#designing-queries} 타겟팅 

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [수신자 테이블 쿼리](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-recipient-table.html)

   이메일 도메인이 &quot;orange.co.uk&quot;이고 런던에 살지 않는 수신자의 이름과 이메일을 복구하는 방법을 알아봅니다.

* [쿼리 게재 정보](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-delivery-information.html)

   프로필 동작을 검색하기 위해 게재 정보에 대한 쿼리를 정의하는 방법을 알아봅니다.

* [계산 집계](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/performing-aggregate-computing.html)

   성별에 따라 런던에 거주하는 프로필 수를 계산하는 방법을 알아봅니다.

* [다대다 관계를 사용하여 쿼리](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-using-many-to-many-relationship.html)

   지난 7일 동안 연락하지 않은 프로필을 찾는 방법을 알아봅니다.

* [쿼리에서 인스턴스 변수 호출](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/javascript-scripts-and-templates.html?lang=en#example)

   인스턴스 변수를 사용하여 모집단에 적용할 분할 비율을 동적으로 계산하는 방법을 알아봅니다.

