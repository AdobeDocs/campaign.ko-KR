---
solution: Campaign Classic
product: campaign
title: 마케팅 캠페인 시작
description: 마케팅 캠페인 시작
feature: 대상
role: Data Engineer
level: Beginner
exl-id: b5a6c845-13a7-4746-b856-a08a3cf80b66,c4798c8f-619e-4a60-80d7-29b9e4c61168
translation-type: tm+mt
source-git-commit: d7d026422d43e8baef43b114936366071f7086e5
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 8%

---

# 마케팅 캠페인 시작{#gs-ac-campaigns}

Adobe Campaign은 온라인과 오프라인의 모든 채널에서 캠페인을 개인화하고 전달할 수 있는 다양한 솔루션을 제공합니다. 마케팅 캠페인을 생성, 구성, 실행 및 분석할 수 있습니다. 모든 마케팅 캠페인은 통합 제어 센터에서 관리할 수 있습니다. 이 섹션에서 마케팅 캠페인을 검색하고 만드는 방법을 알아봅니다.

캠페인에는 작업(배달) 및 프로세스(파일 가져오기 또는 추출)와 리소스(마케팅 문서, 배달 외곽선)가 포함됩니다. 마케팅 캠페인에서 사용됩니다. 캠페인은 프로그램의 일부이며 프로그램은 캠페인 계획에 포함됩니다.

## 크로스 채널 캠페인 오케스트레이션

Adobe Campaign을 사용하면 타겟팅되고 개인화된 캠페인을 전자 메일, DM, SMS, 푸시 알림과 같은 다양한 채널에 디자인 및 오케스트레이션 할 수 있습니다. 단일 인터페이스는 모든 캠페인 및 커뮤니케이션을 일정 계획, 오케스트레이션, 구성, 개인화, 자동화, 실행 및 측정하는 데 필요한 모든 기능을 제공합니다.

### 핵심 개념

마케팅 캠페인을 구현하기 전에 다음 개념에 익숙해야 합니다.

* **마케팅 캠페인**:캠페인은 마케팅 캠페인과 관련된 모든 요소를 중앙에서 관리합니다.배달, 타깃팅 규칙, 비용, 파일 내보내기, 관련 문서 등 각 캠페인은 프로그램에 첨부됩니다.

* **프로그램**:프로그램을 사용하여 일정 기간에 대한 마케팅 작업을 정의할 수 있습니다.런칭, 캔버스, 충성도 등 각 프로그램에는 전체 보기를 제공하는 달력에 연결된 캠페인이 포함되어 있습니다.

* **플랜**:마케팅 계획에는 여러 프로그램이 포함될 수 있습니다. 일정 기간과 연결되며 예산이 할당되어 문서 및 목표에 연결할 수도 있습니다.

* **캠페인 워크플로우**:캠페인 워크플로에는 캠페인 논리를 빌드하는 활동이 포함됩니다. 캠페인 워크플로우를 사용하면 대상을 정의하고 사용 가능한 모든 채널에 대한 배달을 만들 수 있습니다.

* **반복 캠페인**:반복 캠페인은 실행할 워크플로우 템플릿 및 실행 일정을 정의하는 특정 템플릿에서 만들어집니다.

* **정기 캠페인**:주기적 캠페인은 템플릿의 실행 일정에 따라 자동으로 생성되는 캠페인입니다.

## 마케팅 캠페인 작업 공간

Adobe Campaign을 사용하면 통합 제어 센터에서 모든 마케팅 캠페인을 생성, 구성, 실행 및 분석할 수 있습니다.

:arrow_upper_right:[이 페이지](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/about-marketing-campaigns/accessing-marketing-campaigns.html?lang=en#orchestrating-campaigns)에서 마케팅 캠페인에 액세스하고 구현하는 방법을 알아봅니다.


## 시작하는 주요 단계

크로스채널 마케팅 캠페인을 만들기 위한 주요 단계는 다음과 같습니다.

1. **마케팅 프로그램 및 캠페인 계획 및 디자인**

   계층 및 일정을 정의하고 예산을 설정하며 리소스를 추가하고 연산자를 선택합니다.

   :arrow_upper_right:[이 페이지](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#creating-plan-and-program-hierarchy)에서 마케팅 계획을 만들고 캠페인을 구성하는 방법에 대해 알아봅니다.

   모든 마케팅 캠페인은 기본 설정 및 기능을 저장하는 템플릿을 기반으로 합니다. 특정 구성이 정의되지 않은 캠페인을 만들기 위해 내장 템플릿이 제공됩니다. 캠페인 템플릿을 만들고 구성한 다음 이러한 템플릿에서 캠페인을 만들 수 있습니다.

   :arrow_upper_right:[이 페이지](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)에서 캠페인 템플릿을 사용하여 작업하는 방법을 알아봅니다.

   :arrow_upper_right:반복 캠페인과 [이 페이지](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns)에서 이를 구성하는 방법을 알아봅니다.

1. **대상 정의**

   워크플로우에서 대상을 만들거나 수신자 목록, 뉴스레터 구독자, 이전 게재의 수신자 또는 필터링 조건 등과 같은 기존 그룹을 선택할 수 있습니다.

   :arrow_upper_right:[이 페이지](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#orchestrating-campaigns)에서 메시지 대상을 정의하는 방법을 알아봅니다.

1. **배달 만들기**

   채널을 선택하고 메시지 컨텐츠를 정의하고 배달을 시작합니다.

   :arrow_upper_right:[이 페이지](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=en#creating-deliveries)에서 마케팅 캠페인 배달을 만들고 시작하는 방법에 대해 알아봅니다.

   다양한 문서를 캠페인에 연결할 수 있습니다.보고서, 사진, 웹 페이지, 다이어그램 등

   :arrow_upper_right:[이 섹션](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-assets.html?lang=en#adding-documents)의 관련 문서에 대한 자세한 내용

1. **승인 프로세스 설정**

   Adobe Campaign을 사용하면 마케팅 캠페인의 주요 단계에 대한 협업 승인 프로세스를 설정할 수 있습니다. 각 캠페인에 대해 게재 타겟, 컨텐츠 및 비용을 승인할 수 있습니다. 승인 담당 Adobe Campaign 운영자에게는 이메일을 통해 통지할 수 있으며 콘솔 또는 웹 연결을 통해 승인을 수락하거나 거부할 수 있습니다.

   :arrow_upper_right:[이 페이지](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=en#orchestrating-campaigns)에서 승인을 설정하고 관리하는 방법에 대해 알아봅니다.


1. 메시지 모니터링:전달 및 실행을 제어합니다. 자세히 알아보기.

1. 캠페인 및 관련 비용을 계획합니다. 자세히 알아보기.

## 승인 및 유효성 검사


## 서비스 및 구독

서비스 만들기 및 구독/구독 취소 관리

## 보고

캠페인에 대한 보고서

: 전구:
