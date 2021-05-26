---
solution: Campaign v8
product: Adobe Campaign
title: Campaign v8 시작
description: 주요 기능, 사용자 인터페이스 및 글로벌 지침을 살펴보십시오
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 43%

---

# Adobe Campaign 시작{#gs-ac-v8}

Adobe Campaign은 크로스 채널 고객 경험을 디자인하고 시각적 캠페인 운영, 실시간 상호 작용 관리 및 크로스 채널 실행을 위한 환경을 제공할 수 있는 플랫폼을 제공합니다.

Campaign을 사용하여 다음을 수행할 수 있습니다.

* **** 고객이 액세스할 수 있는 단일 뷰를 통해 개인화 및 참여를 유도합니다
* **** 이메일, 모바일, 온라인 및 오프라인 채널을 고객 여정에 통합
* **** 의미 있고 시기 적절한 메시지 및 오퍼의 게재를 자동화합니다

![](assets/ac-capabilities.png)

## Integrated customer profile {#integrated-customer-profile}

강력한 클라우드 데이터베이스에서 프로필이 중앙 집중화되었습니다. 프로필을 가져오고 이 데이터베이스를 빌드하는 데 사용할 수 있는 메커니즘은 웹 양식을 통한 온라인 수집, 텍스트 파일 수동 또는 자동 가져오기, 회사 데이터베이스 또는 기타 정보 시스템을 사용한 복제와 같이 다양합니다. Adobe Campaign을 사용하면 마케팅 기록, 구매 정보, 환경 설정, CRM 데이터 및 관련 PII 데이터를 통합 뷰에 통합하여 분석하고 조치를 취할 수 있습니다.

Adobe Campaign에서 수신자는 게재(전자 메일, SMS 등)를 보낼 타겟팅된 기본 프로필입니다. 데이터베이스에 저장된 수신자 데이터 덕분에 주어진 게재를 받을 대상을 필터링하고 게재 콘텐츠에 개인화 데이터를 추가할 수 있습니다. 데이터베이스에 다른 유형의 프로필이 있습니다. 다양한 용도로 디자인되어 있습니다. 예를 들어 최종 대상으로 전송되기 전에 시드 프로필을 테스트하여 게재를 테스트합니다.

[!DNL :bulb:] 프로필 관리 기본 사항은  [이 섹션에 설명되어 있습니다](audiences.md).

[!DNL :bulb:]  [이 섹션](import.md)에서 Campaign에 프로필을 추가하는 방법을 배웁니다.

## 타겟팅된 세분화 {#targeted-segmentation}

Adobe Campaign은 고도로 타겟팅되고 차별화된 오퍼를 만들 수 있는 강력하고 사용자 친화적인 세분화 및 타겟팅 기능을 제공합니다. 설명 분석 기능을 사용하면 마케팅 캠페인의 업스트림 및 다운스트림에 대한 정보를 분석할 수 있으며 필터 관리 및 그래픽 쿼리 편집기 기능을 사용하면 구독자 모집단을 필터링하고 기준을 제한 없이 대상 그룹을 샘플링하거나 만들 수 있습니다.

고급 데이터 관리 기능은 데이터 처리 기능을 확장합니다. 데이터 마트에서 모델링되지 않은 데이터를 포함하여 타겟팅 프로세스를 단순화하고 최적화합니다.

[!DNL :bulb:]  [이 섹션](audiences.md)에서 세그멘테이션, 대상 만들기 및 개인화에 대해 자세히 알아보십시오 .

## 크로스 채널 캠페인 오케스트레이션 {#cross-channel-campaign-orchestration}

Adobe Campaign을 사용하면 타겟팅되고 개인화된 캠페인을 전자 메일, DM, SMS, 푸시 알림과 같은 다양한 채널에 디자인 및 오케스트레이션 할 수 있습니다. 단일 인터페이스는 모든 캠페인 및 커뮤니케이션을 일정 계획, 오케스트레이션, 구성, 개인화, 자동화, 실행 및 측정하는 데 필요한 모든 기능을 제공합니다.

[!DNL :bulb:]  [이 섹션](campaigns.md)에서 캠페인을 디자인, 예약 및 실행하는 방법을 알아봅니다.

## 워크플로우

Adobe Campaign은 세그먼테이션, 캠페인 실행, 파일 처리 등과 같은 복잡한 프로세스를 디자인할 수 있는 포괄적인 그래픽 환경을 제공합니다. 예를 들어 워크플로우를 사용하여 서버에서 파일을 다운로드하고 압축을 해제한 다음 해당 레코드를 Adobe Campaign 데이터베이스로 가져올 수 있습니다.

워크플로우에는 사용자에게 작업을 할당하거나 사용자가 수행된 작업을 승인하도록 하여 사용자가 포함될 수도 있습니다. 즉, 메시지를 보내기 전에 하나 또는 여러 사용자에게 작업을 할당하여 콘텐츠에서 작업하거나 대상을 지정하고 증명을 승인할 수 있습니다.

워크플로우는 다음과 같이 다른 컨텍스트에서 사용할 수 있습니다.

* 대상을 관리하거나 메시지를 보내기 위한 타겟팅.
* 데이터를 조작하는 ETL(데이터 관리)
* 데이터를 Campaign 데이터베이스로 가져옵니다.
* 데이터베이스 정리, 추적 정보 복구 등의 기술 프로세스

[!DNL :bulb:]  [이 섹션](../config/workflows.md)에서 워크플로우를 디자인하고 실행하는 방법을 배웁니다.

## 보고 및 분석 {#analysis-and-reporting}

Adobe Campaign을 사용하면 데이터와 프로필을 단계적으로 강화하여 고객의 동작을 모니터링하고 해석할 수 있습니다. 보고 및 분석 도구를 사용하면 각각의 새로운 캠페인을 활용할 수 있고, 마케팅 이니셔티브를 더 잘 타겟팅할 수 있으며, 마케팅 활동의 영향과 투자 수익률을 최적화할 수 있습니다.

[!DNL :bulb:] 보고서 및 추적 기능에 대한 자세한 내용은  [이 섹션](reporting.md)을 참조하십시오.

## Adobe Experience Cloud 통합 {#adobe-experience-cloud-integrations}

Adobe Campaign의 게재 기능 및 고급 캠페인 관리 기능과 사용자 경험을 개인화할 수 있도록 만들어진 솔루션 세트를 결합할 수 있습니다. 예를 들어 Adobe Experience Manager, Adobe Analytics, Adobe Target 또는 Adobe Experience Cloud 트리거를 사용할 수 있습니다.

[!DNL :bulb:]  [이 섹션](../connect/integration.md)에서 Adobe 서비스 및 솔루션과 통합하는 방법을 알아봅니다.

## Campaign 기능에 대한 자세한 내용 {#core-capabilities-and-add-ons}

Adobe Campaign은 요구 사항과 아키텍처에 따라 대화형 마케팅 기능을 구현하고 최적화하는 데 도움이 되는 기능의 집합을 제공합니다. 일부는 핵심 기능이며 일부는 구성에 따라 패키지 설치에 따라 다릅니다. 자세한 제품 설명은 다음 위치에서 확인할 수 있습니다.[Adobe Campaign v8 제품 설명](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-classic—product-description.html).

[!DNL :bulb:] 이미 Campaign Classic에 익숙합니까? [이 페이지에서 Campaign Classic과 Campaign v8 간의 주요 차이점을 알아봅니다](capability-matrix.md).

## 작업 공간 및 사용자 지정

Campaign 작업 공간은 [클라이언트 콘솔](../dev/general-architecture.md)을 통해 사용할 수 있습니다.

[!DNL :bulb:] [Campaign 클라이언트 콘솔에 대해 자세히 알아보십시오](../start/connect.md).

Campaign 작업 영역은 필요에 따라 조정할 수 있습니다.

:[!DNL :arrow_upper_right:]: [Campaign Classic v7 설명서에서 Campaign 작업 공간을 사용하는 방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html)

:[!DNL :arrow_upper_right:]: [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html)에서 목록을 사용자 지정하는 방법을 알아봅니다.

웹을 통해 일부 기능에 액세스할 수도 있습니다.

[!DNL :bulb:] [Campaign Web Access에 대해 자세히 알아보십시오](../start/connect.md#web-access).


## 언어

Campaign v8 사용자 인터페이스는 다음 언어로 제공됩니다.

* 영어(영국)
* 영어(미국)
* 프랑스어
* 독일어
* 일본어

설치 프로세스 중에 언어가 선택됩니다.

>[!CAUTION]
>
>인스턴스를 만든 후에는 언어를 변경할 수 없습니다.

언어 영향을 받은 날짜 및 시간 형식. 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=en#date-and-time)를 참조하십시오.

