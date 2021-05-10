---
solution: Campaign
product: Adobe Campaign
title: 캠페인 자동화 시작하기
description: 캠페인 자동화 시작하기
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
translation-type: tm+mt
source-git-commit: 2ea953145b645d376d5ea88b89350b45f024ea7d
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 0%

---

# 프로세스 관리 및 자동화

강력한 마케팅 캠페인 자동화 기능을 활용하도록 캠페인을 구성합니다.

다음과 같이 설정할 수 있습니다.

* 워크플로우
* 반복 캠페인
* 완벽한 유효성 검사 주기
* 경고
* 자동 보고서 전송
* 트리거된 이벤트

## 워크플로우 디자인 및 사용{#gs-ac-wf}

Adobe Campaign 워크플로우를 사용하면 세그먼트 생성, 메시지 준비, 전달에 이르기까지 마케팅 캠페인의 모든 측면을 빠르고 확장할 수 있습니다.

다음 섹션의 워크플로우에 대해 자세히 알아보십시오.

* [워크플로우 시작하기](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)
* 워크플로우 활동
   * [타깃팅 활동](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html):쿼리, 목록, 데이터 연계, 통합 등
   * [흐름 제어 활동](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html):스케줄러, 포크, 경고, 외부 신호 등
   * [작업 활동](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html):크로스 채널 전달, Javascript 코드, CRM 활동, 업데이트 집계 등
   * [이벤트 활동](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html):파일 전송, 웹 다운로드 등
* [엔드 투 엔드 활용 사례 보기](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/about-workflow-use-cases.html)
* [마케팅 캠페인 워크플로우에서 대상 만들기](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)
* [워크플로우 모범 사례](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html)
* [내장된 기술 워크플로우](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)
* [워크플로우 실행 모니터링](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html)

## 반복 캠페인 설정

반복을 디자인하고 실행할 때마다 새 배달 인스턴스를 만듭니다. 예를 들어 워크플로우가 일주일에 한 번 실행되도록 설계된 경우 1년 후 52회의 배달이 됩니다. 또한 로그가 각 배달 인스턴스로 구분됩니다.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns)에서 반복 캠페인을 만드는 방법을 알아봅니다.

## 종단 간 유효성 검사 주기 구성

게재의 각 단계에 대한 승인 프로세스를 설정하고 마케팅 캠페인의 다양한 프로세스를 완벽하게 모니터링하고 제어할 수 있습니다.타깃팅, 컨텐츠, 예산, 추출 및 증명 보내기

알림은 Adobe Campaign 운영자에게 승인 요청을 알리기 위해 검토자로 설정된 경우 전송됩니다.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html)에서 승인 프로세스를 설정하고 관리하는 방법에 대해 알아봅니다.


## 알림 보내기

캠페인 운영자는 오류가 발생하면 경고를 받을 수 있습니다.

워크플로우 집합 상태를 모니터링하고 반복 메시지를 감독자에게 보낼 수 있는 워크플로우를 만들 수 있습니다.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html?lang=en#step-1--creating-the-monitoring-workflow)에서 다른 워크플로의 상태를 모니터링하는 워크플로우를 만드는 방법을 알아봅니다.

오류가 발생하면 경고를 받을 수도 있습니다

## 자동 보고서 보내기

:arrow_upper_right:연산자 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html?lang=en#step-1--creating-the-recipient-list)의 목록에 보고서를 자동으로 전송하는 방법을 알아봅니다.


## 트리거 이벤트 활용

캠페인 트랜잭션 메시지를 사용하여 정보 시스템에서 트리거된 이벤트에서 생성된 메시지를 자동화할 수 있습니다. 이러한 트랜잭션 메시지는 송장, 주문 확인, 배송 확인, 암호 변경, 제품 사용 불능 알림, 계정 명세서 또는 웹 사이트 계정 생성일 수 있습니다. 이러한 메시지는 개별적으로 또는 이메일, SMS 또는 푸시 알림을 통해 일괄적으로 보낼 수 있습니다.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=en#transactional-messaging)의 트랜잭션 메시지 기능에 대해 자세히 알아보십시오.


Adobe Campaign 및 Adobe Analytics을 연결하여 사용자 동작을 검색하고 거의 실시간으로 개인화된 메시지를 전송할 수 있습니다.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en#integrating-with-adobe-experience-cloud)에서 Analytics 트리거와 Campaign을 통합하는 방법을 알아봅니다.

: 전구:[이 섹션](../start/connect.md)에서 캠페인을 다른 솔루션과 통합하는 방법을 알아봅니다.
