---
title: 업그레이드 시작하기
description: 업그레이드 시작하기
feature: Cross Channel Orchestration
role: User
level: Beginner
exl-id: b5a6c845-13a7-4746-b856-a08a3cf80b66
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 100%

---

# 캠페인 시작하기{#gs-ac-campaigns}

Adobe Campaign은 온라인과 오프라인의 모든 채널에서 캠페인을 개인화하고 게재할 수 있는 다양한 솔루션을 제공합니다. 마케팅 캠페인을 생성, 구성, 실행 및 분석할 수 있습니다. 모든 마케팅 캠페인은 통합 제어 센터에서 관리할 수 있습니다. 이 섹션에서 마케팅 캠페인을 검색하고 만드는 방법을 알아봅니다.

캠페인에는 작업(게재) 및 프로세스(파일 가져오기 또는 추출)와 리소스(마케팅 문서, 게재 아웃라인)가 포함됩니다. 마케팅 캠페인에서 사용됩니다. 캠페인은 프로그램의 일부이며 프로그램은 캠페인 플랜에 포함됩니다.

## 크로스 채널 캠페인 오케스트레이션{#cross-channel-orchestration}

Adobe Campaign을 사용하면 타기팅되고 개인화된 캠페인을 이메일, DM, SMS, 푸시 알림과 같은 다양한 채널에 디자인 및 오케스트레이션 할 수 있습니다. 단일 인터페이스는 모든 캠페인 및 커뮤니케이션을 일정 계획, 오케스트레이션, 구성, 개인화, 자동화, 실행 및 측정하는 데 필요한 모든 기능을 제공합니다.

![](assets/campaign-tab.png)

### 핵심 개념{#ac-core-concepts}

마케팅 캠페인을 구현하기 전에 다음 개념에 익숙해야 합니다.

* **마케팅 캠페인**:캠페인은 게재, 타기팅 규칙, 비용, 파일 내보내기, 관련 문서 등 마케팅 캠페인과 관련된 모든 요소를 중앙에서 관리합니다. 각 캠페인은 프로그램에 첨부됩니다.

* **프로그램**: 프로그램을 사용하여 일정 기간에 대해서 론칭, 캔버스, 충성도 등 마케팅 작업을 정의할 수 있습니다. 각 프로그램에는 전체 보기를 제공하는 달력에 연결된 캠페인이 포함되어 있습니다.

* **플랜**: 마케팅 플랜에는 여러 프로그램이 포함될 수 있습니다. 일정 기간과 연결되며 예산이 할당되어 문서 및 목표에 연결할 수도 있습니다.

* **캠페인 워크플로우**: 캠페인 워크플로에는 캠페인 로직을 세우는 활동이 포함됩니다. 캠페인 워크플로우를 사용하여 대상을 정의하고 사용 가능한 모든 채널에 대한 게재를 만들 수 있습니다.

* **반복 캠페인**: 반복 캠페인은 실행할 워크플로우 템플릿 및 실행 일정을 정의하는 특정 템플릿에서 만들어집니다.

* **정기 캠페인**: 정기 캠페인은 템플릿의 실행 일정에 따라 자동으로 생성되는 캠페인입니다.

## 마케팅 캠페인 작업 영역{#ac-workspace}

Adobe Campaign을 사용하면 통합 제어 센터에서 모든 마케팅 캠페인을 생성, 구성, 실행 및 분석할 수 있습니다.

![](assets/calendar.png)

[이 섹션](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=ko){target="_blank"}에서는 마케팅 캠페인에 액세스하고 구현하는 방법을 알아봅니다.

## 주요 시작 단계{#gs-ac-start}

크로스 채널 마케팅 캠페인을 만들기 위한 주요 단계는 다음과 같습니다.

1. **마케팅 프로그램 및 캠페인의 계획 및 디자인**

   계층 및 일정을 정의하고 예산을 설정하며 리소스를 추가하고 운영자를 선택합니다.

   [이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-create.html?lang=ko){target="_blank"}에서는 마케팅 계획을 세우고 캠페인을 구성하는 방법을 알아봅니다.

   모든 마케팅 캠페인은 기본 설정 및 기능을 저장하는 템플릿을 기반으로 합니다. 특정 구성이 정의되지 않은 캠페인을 만들기 위해 내장 템플릿이 제공됩니다. 캠페인 템플릿을 만들고 구성한 다음 그 템플릿에서 캠페인을 만들 수 있습니다.

   [이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-templates.html?lang=ko){target="_blank"}에서 캠페인 템플릿으로 작업하는 방법을 알아봅니다.

   [이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html?lang=ko){target="_blank"}에서 반복 캠페인과 해당 캠페인을 구성하는 방법을 알아봅니다.

1. **대상 정의**

   워크플로우에서 대상을 만들거나 수신자 목록, 뉴스레터 구독자, 이전 게재의 수신자 또는 필터링 조건 등과 같은 기존 그룹을 선택할 수 있습니다.

   ![](assets/campaign-wf.png)

   [이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=ko){target="_blank"}에서 메시지 대상자를 정의하는 방법을 알아봅니다.

1. **게재 만들기**

   채널을 선택하고 메시지 컨텐츠를 정의하고 게재를 시작합니다.

   ![](assets/campaign-dashboard.png)

   [이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=ko){target="_blank"}에서는 마케팅 캠페인 게재를 만들고 시작하는 방법을 알아봅니다.

   보고서, 사진, 웹 페이지, 다이어그램 등 다양한 문서를 캠페인에 연결할 수 있습니다.

   [이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-assets.html?lang=ko){target="_blank"}에서는 관련 문서에 대해 자세히 알아봅니다.

1. **승인 프로세스 설정**

   Adobe Campaign을 사용하면 마케팅 캠페인의 주요 단계에 대한 협업 승인 프로세스를 설정할 수 있습니다. 각 캠페인에 대해 게재 대상, 콘텐츠 및 비용을 승인할 수 있습니다. 승인을 담당하는 Adobe Campaign 운영자는 이메일로 통보를 받을 수 있으며 콘솔 또는 웹 연결을 통해 승인을 수락하거나 거부할 수 있습니다.

   [이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=ko#campaign-orchestration){target="_blank"}에서는 승인 설정 및 관리 방법을 알아봅니다.


## 분산 마케팅 추가 기능{#distributed-marketing-add-on}

Adobe Campaign에서는 **분산 마케팅** 추가 기능을 제공하는데, 이 기능은 중앙 엔터티(본사, 마케팅 부서 등)와 지역(상점, 지역 등) 간의 협력 캠페인을 실시합니다. 이러한 협력은 공유 작업 공간(**[!UICONTROL List of campaign packages]**)을 기반으로 하는데, 중앙 엔티티에 의해 설계된 캠페인 템플릿이 로컬 엔티티에 제공됩니다.

>[!NOTE]
>
>이 기능은 Campaign v8.3부터 사용할 수 있습니다. 버전을 확인하려면 [이 섹션](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)을 참조하세요.

[이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/distributed-marketing/about-distributed-marketing.html?lang=ko){target="_blank"}에서는 캠페인 분산 마케팅 기능을 구성하고 사용하는 방법을 알아봅니다.

## 응답 관리 추가 기능{#response-manager-add-on}

Adobe Campaign에서는 마케팅 캠페인의 성공 및 수익성을 측정하거나 커뮤니케이션 채널 간에 제안을 제공하는 **응답 관리** 추가 기능을 제공합니다.

>[!NOTE]
>
>이 기능은 Campaign v8.3부터 사용할 수 있습니다. 버전을 확인하려면 [이 섹션](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)을 참조하세요.

[](../assets/do-not-localize/book.png)[Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/response-manager/about-response-manager.html?lang=ko){target="_blank"}에서 캠페인 응답 매니저를 구성하고 사용하는 방법을 알아봅니다.
