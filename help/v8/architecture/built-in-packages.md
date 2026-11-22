---
title: 기본 제공 패키지
description: Campaign v8에 포함된 기본 제공 패키지가 무엇인지, 사용자 지정 데이터 패키지와 어떻게 다른지, 어떤 패키지를 사용할 수 있는지 알아봅니다
feature: Architecture
role: Admin, Developer
level: Beginner
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: bae31391-3416-5fbd-bc4b-2cdcae2922db
    internal-label: Architecture
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e656c701-3899-4db3-989c-de0980ddfffa
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 9f70a309a882347a0df658d00c47127f31d28eb9
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 15%
---
# 기본 제공 패키지 {#built-in-packages}

기본 제공 패키지(표준 패키지라고도 함)에는 Adobe Campaign 기능이 포함되어 있습니다. Campaign v8에서 Adobe은 이러한 패키지를 설치하고 관리합니다. 설치하지 않아도 됩니다.

## 기본 제공 패키지 및 사용자 지정 패키지 {#built-in-vs-custom}

Campaign에서는 두 가지 종류의 패키지를 사용합니다. 올바른 방법으로 작업하십시오.

| | 기본 제공 패키지 | 사용자 정의 패키지 |
|---|---|---|
| 목적 | 채널, 통합 및 추가 기능과 같은 Campaign 기능을 제공합니다. | 자체 구성 및 데이터를 내보내고 가져옵니다(예: 스테이징에서 프로덕션 환경으로). |
| 누가 관리합니까 | Adobe이 설치하고 관리합니다. Managed Cloud Services를 사용하면 설치된 기본 제공 패키지를 수정할 수 없습니다. | 만들고 내보내고 가져옵니다. |
| 자세한 내용 | 이 페이지입니다. | [데이터 패키지를 사용하여 작업](../dev/packages.md) |

## 설치된 패키지 확인 {#check-installed-packages}

인스턴스에 설치된 기본 제공 패키지를 확인하려면 **[!UICONTROL Administration > Configuration > Package management > Installed packages]**(으)로 이동하십시오. Campaign 컨트롤 패널의 인스턴스 모니터링에서도 이를 볼 수 있습니다. 자세한 내용은 [캠페인 모니터링 개요](../start/monitor.md#monitor-instance)를 참조하세요.

제공되지 않은 패키지 또는 추가 기능이 필요한 경우 Adobe 고객 지원 센터 또는 Adobe 전환 관리자에게 문의하십시오.

## 기본 제공 패키지 목록 {#list-of-built-in-packages}

다음 표에는 기본 제공 패키지 정보가 나와 있습니다. 각 패키지의 가용성은 사용권 계약 및 배포 모델에 따라 다릅니다.

| 패키지 | 설명 |
|---|---|
| 게재 | 게재 및 메시지를 보낼 때 발생하는 문제를 모니터링합니다. [자세히 알아보기](../start/monitor.md) |
| 마케팅 캠페인(Campaign) | 커뮤니케이션 및 마케팅 캠페인을 정의, 최적화, 실행 및 분석합니다. [자세히 알아보기](../start/campaigns.md) |
| 마케팅 리소스(MRM) | 작업, 예산 및 마케팅 리소스의 관리 및 추적을 사용하여 공동 작업 모드에서 마케팅 작업을 제어합니다. [자세히 알아보기](../../automation/mrm/about-marketing-resource-management.md) |
| 오퍼 엔진(상호 작용) | 하나 또는 여러 개의 오퍼를 조정하여 연락처와의 상호 작용 중에 실시간으로 응답합니다. [자세히 알아보기](../interaction/interaction.md) |
| 소셜 네트워크(소셜 마케팅) | Adobe Campaign을 X(이전 Twitter)와 동기화합니다. [자세히 알아보기](../connect/ac-tw.md) |
| 트랜잭션 메시지 제어 및 실행(메시지 센터) | 정보 시스템의 이벤트에서 생성된 트리거 메시지를 관리하여 가용성을 높이고 로드 관리를 개선합니다. [자세히 알아보기](../send/transactional.md) |
| LINE 채널 | LINE 채널을 통해 게재를 전송합니다. [자세히 알아보기](../send/line/line.md) |
| DM 채널 | DM 채널을 통해 게재를 전송합니다. [자세히 알아보기](../send/direct-mail.md) |
| 모바일 채널(SMS) | SMS 커넥터 v2(8.9.1 이후 일반적으로 사용 가능)를 포함하여 모바일 채널(SMS)을 통해 게재를 전송합니다. [자세히 알아보기](../send/sms/sms.md) |
| 모바일 앱 채널 | 앱을 통해 iOS 및 Android 디바이스에 개인화된 알림을 보냅니다. [자세히 알아보기](../send/push.md) |
| 콘텐츠 관리자 | 반복 뉴스레터 또는 웹 사이트를 만든 다음 메시지의 유효성을 검사하고 게시합니다. [자세히 알아보기](../../automation/workflow/content-management.md) |
| 온라인 설문 조사(설문 조사 관리자) | 온라인 양식을 만들고 관리하여 프로필 정보를 추가 또는 수정하거나, 구독 또는 구독 취소하거나, 경쟁에 참여합니다. [자세히 알아보기](../dev/surveys/about-surveys.md) |
| 마케팅 분석 | 데이터 분석 및 측정, 통계 계산, 보고서 작성 간소화 [자세히 알아보기](../reporting/gs-reporting.md) |
| 응답 매니저 | 모든 채널에서 마케팅 캠페인 또는 오퍼의 성공 및 수익성을 측정합니다. [자세히 알아보기](../../automation/response/about-response-manager.md) |
| 외부 데이터 액세스(FDA) | Adobe Campaign 데이터의 구조를 변경하지 않고 외부 데이터베이스에 저장된 정보를 처리합니다. [자세히 알아보기](../connect/fda.md) |
| 캠페인 최적화 | 메시지가 고객 요구 사항 및 회사 커뮤니케이션 정책을 충족하도록 게재를 제어, 필터링 및 모니터링합니다. [자세히 알아보기](../../automation/campaign-opt/campaign-typologies.md) |
| 전달성 모니터링(이메일 전달성) | 메시지가 바운스되지 않거나 스팸으로 표시되지 않고 받은 편지함에 도달하는지 측정합니다. [자세히 알아보기](../send/monitoring-deliverability.md) |
| 쿠폰 관리 | 마케팅 오퍼에 추가할 쿠폰 세트를 만듭니다. [자세히 알아보기](../send/personalized-coupons.md) |
| 받은 편지함 렌더링(IR) | 메시지가 수신될 수 있는 컨텍스트에서 메시지를 미리 보고 주요 데스크톱 및 웹 이메일 클라이언트와의 호환성을 확인합니다. [자세히 알아보기](../send/inbox-rendering.md) |
| 중앙/로컬 마케팅(분산 마케팅) | 본사와 같은 중앙주체와 세일즈 포인트와 같은 지역 주체 간 협력 캠페인을 실시한다. [자세히 알아보기](../../automation/distributed-marketing/about-distributed-marketing.md) |
| CRM 커넥터 | Adobe Campaign을 타사 CRM 시스템에 연결합니다. [자세히 알아보기](../connect/crm.md) |
| 웹 분석 커넥터 | Adobe Campaign 및 Adobe Analytics이 상호 작용할 수 있습니다. [자세히 알아보기](../connect/ac-aa.md) |
| AEM 통합 | Adobe Experience Manager에서 이메일 및 양식의 콘텐츠를 관리합니다. [자세히 알아보기](../connect/ac-aem.md) |
| Adobe Experience Cloud 공유 대상자 통합 | [!DNL Adobe CX Enterprise]&#x200B;(이전 Adobe Experience Cloud) 솔루션 및 앱과 대상을 교환하고 공유합니다. [자세히 알아보기](../start/shared-audiences.md) |
| Adobe Experience Cloud와 통합 | [!DNL Adobe CX Enterprise]&#x200B;(이전 Adobe Experience Cloud) 솔루션의 대상을 Adobe Campaign으로 가져오고 내보냅니다. [자세히 알아보기](../connect/integration.md) |
| 개인정보 보호 규정 | 개인정보 규정 준수에 도움이 되는 기능을 추가합니다. [자세히 알아보기](../start/privacy.md) |
| AMP 지원 | 대화형 AMP를 사용하여 다이내믹 이메일을 이메일 형식으로 전송합니다. [자세히 알아보기](../send/defining-interactive-content.md) |


>[!NOTE]
>
>Campaign의 엔터프라이즈(FFDA) 배포 컨텍스트에서는 마케팅 리소스(MRM), 쿠폰 관리 및 온라인 설문 조사 패키지를 사용할 수 없습니다. [기능 가용성](../architecture/enterprise-deployment.md#feature-availability)에서 자세히 알아보세요.

## 관련 항목 {#related-topics}

* [데이터 패키지를 사용하여 작업](../dev/packages.md): 사용자 지정 패키지를 만들고 내보내고 가져옵니다.
* [기술 워크플로우](../../automation/workflow/technical-workflows.md): 기본 제공 기술 워크플로우 및 각 워크플로우를 설치하는 패키지.
* [FFDA 배포에서 기능 사용 가능](enterprise-deployment.md#feature-availability): 엔터프라이즈(FFDA) 배포에서는 사용할 수 없는 기능입니다.
* [지원되지 않는 기능](../start/v7-to-v8.md#gs-removed): v8에서 더 이상 지원되지 않는 Campaign Classic v7 기능입니다.
* [전역 원칙](general-architecture.md): 관리 클라우드 서비스 환경에서 수정할 수 있는 사항과 수정할 수 없는 사항.
* [Campaign v8 시작](../start/get-started.md): 핵심 기능 및 추가 기능에 대한 개요입니다.
