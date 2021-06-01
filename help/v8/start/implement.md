---
product: Adobe Campaign
title: 구현 지침
description: Campaign v8 구현 방법 알아보기
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 84%

---

# Campaign 구현 지침

이 섹션에서는 회사의 요구 사항에 맞게 Adobe Campaign을 조정하는 방법을 알아봅니다. 구현을 구조화하고 조직화하려면 다음 지침을 사용하십시오.

1. **설정 정의**: 액세스 권한 부여, 클라이언트 콘솔 공유, 채널 구성(이메일, 푸시 알림, SMS)
1. **환경 준비**: 프로필 가져오기, 대상 만들기, 워크플로우 및 캠페인 템플릿 디자인하기, 유형 규칙 만들기
1. **인스턴스 사용자 정의하기**: 새 데이터 필드 만들기, 테이블/스키마 추가하기
1. **배포 확장**: Adobe 솔루션, 기타 제품 및 시스템(커넥터, 멀티 솔루션 설정)에 연결하기

>[!CAUTION]
>
>**Campaign 관리 Cloud Services**&#x200B;을(를) 사용하면 라이선스 계약 약관에 따라 환경 및 초기 구성이 Adobe에 의해 설정되었습니다. 설치된 기본 제공 패키지, 기본 제공 스키마 또는 보고서를 수정할 수 없습니다.
>
>Campaign 추가 기능 또는 제공되지 않은 특정 기능을 사용해야 하는 경우 고객 지원 센터 Adobe **에 문의해야 합니다.**

## 시작하기 전

이 섹션에는 실제 구현을 시작하기 전에 검토하고 고려해야 하는 개인 정보 및 보안에 대한 중요한 정보가 포함되어 있습니다.

### 개인 정보

Adobe Campaign에는 적용 가능한 데이터 개인 정보 보호법 및 수신자 기본 설정을 준수하는 Campaign을 사용할 수 있는 프로세스와 설정이 포함되어 있습니다. 다음을 관리할 수 있습니다.

* **데이터 수집**: Adobe Campaign을 사용하면 개인 및 중요 정보를 포함한 데이터를 수집할 수 있습니다. 따라서 수신자로부터 동의를 받고 모니터링하는 것이 중요합니다. 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#data-acquisition)를 참조하십시오

* **사용자 동의 및 데이터 유지**: 사용자 동의를 얻는 방법, 이중 옵트인 구독 메커니즘을 설정하는 방법, 옵트아웃을 용이하게 하는 방법, 데이터 유지를 구성하는 방법에 대해 [Campaign Classic 개인 정보 보호 문서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#consent)에서 살펴봅니다.

* **개인 정보 보호 및 데이터 보호 규정**: 유럽 연합의 GDPR(General Data Protection Regulation), CCPA(California Consumer Privacy Act) 및 기타 국제 개인 정보 보호 요구 사항에 대한 정보와 이러한 규정이 조직 및 Adobe Campaign에 미치는 영향에 대한 자세한 내용은 [Campaign Classic 개인 정보 보호 문서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html)를 참조하십시오.

### 보안

[Campaign Security 검사 목록](../config/security.md)에서 Adobe Campaign을 사용하는 보안 지침 및 원칙을 알아봅니다.

## 캠페인 설정 정의

### 사용자 추가 및 권한 부여

수동으로 Campaign에 사용자를 추가하고 역할 계층 구조에 맞게 그룹과 연결할 수 있습니다. 그러면 사용자는 로그인하여 자신에게 적합한 데이터와 권한에 액세스할 수 있습니다.

[!DNL :arrow_upper_right:]  [이 섹션](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=ko#getting-started)에서 Adobe Campaign에 사용자를 추가하는 방법을 알아봅니다.

### Campaign 클라이언트 콘솔 설치

애플리케이션의 기본 사용자 인터페이스는 리치 클라이언트입니다. 즉, 표준 인터넷 프로토콜(SOAP, HTTP 등)만 사용하여 Adobe Campaign 애플리케이션 서버와 통신하는 기본 애플리케이션(Windows)입니다. Adobe Campaign 클라이언트 콘솔은 생산성을 높여주는 탁월한 사용자 친화성을 제공하며, 로컬 캐시를 통해 거의 대역폭을 사용하지 않으며, 배포하기 쉽도록 설계되었습니다. 이 콘솔은 인터넷 브라우저에서 배포할 수 있으며 자동으로 업데이트될 수 있으며 HTTP(S) 트래픽만 생성하므로 특정 네트워크 구성이 필요하지 않습니다.

[!DNL :bulb:] [Campaign 클라이언트 콘솔에 대해 자세히 알아보십시오](connect.md).

## 환경 준비

메시지 전송을 시작하고 마케팅 캠페인을 만들기 전에 다음을 수행해야 합니다.

1. 프로필 가져오기 및 대상 만들기

   Campaign을 사용하면 Cloud 데이터베이스에 연락처를 추가할 수 있습니다. 파일을 불러오고, 여러 연락처 업데이트를 예약 및 자동화하고, 웹에서 데이터를 수집하거나, 수신자 표에 직접 프로필 정보를 입력할 수 있습니다.

   [!DNL :bulb:] [프로필 가져오기 방법](import.md)을 알아봅니다.

   대상은 목록으로 그룹화되고 워크플로우를 통해 만들 수 있습니다. 그런 다음 크로스 채널 게재에서 타기팅할 수 있습니다.

   [!DNL :bulb:] [대상을 정의하는 방법](audiences.md)을 알아봅니다.

1. 템플릿 만들기

   캠페인, 게재, 작업 또는 워크플로우는 모두 주요 설정 및 기능을 저장하는 템플릿을 기반으로 합니다. 특정 구성이 정의되지 않은 각 구성 요소에 대해서는 내장 템플릿이 제공됩니다. 템플릿을 요구 사항에 맞게 구성하고 조정하여 최종 사용자가 사용할 수 있도록 해야 합니다.

   [!DNL :arrow_upper_right:] [이메일 템플릿에 대해 자세히 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=ko)

   [!DNL :arrow_upper_right:] 이 페이지에서 캠페인 템플릿으로 작업하는 방법 [을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=ko#orchestrating-campaigns)

   [!DNL :arrow_upper_right:] 이 페이지에서 워크플로우 템플릿을 구성하는  [방법을 알아봅니다](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=ko#workflow-templates)

1. 유형 규칙 구성

   캠페인 유형 규칙을 활용하여 게재 전송을 필터링, 제어 및 모니터링할 수 있습니다. 예를 들어, 피로 규칙은 수신자의 과도한 요청을 방지하기 위해 메시지 빈도와 양을 제어합니다. 구현되면 게재에서 유형 규칙을 참조합니다.

   [!DNL :arrow_upper_right:] [유형화 및 피로도 관리에 대해 자세히 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=ko#orchestrating-campaigns)

1. Campaign의 내장 데이터 모델 익히기

   Adobe Campaign은 사전 정의된 데이터 모델을 제공합니다. 환경을 구현하고 사용자 정의하려면 Adobe Campaign 데이터 모델의 내장된 표와 이러한 데이터 모델이 서로 어떻게 연관되어 있는지 알아야 합니다.

   [!DNL :bulb:] [Campaign 데이터 모델](../dev/datamodel.md)에 대해 자세히 알아봅니다.

## 인스턴스 사용자 정의

Campaign의 다양한 영역과 기능을 사용자 지정할 수 있습니다. 대부분의 고객은 다음 3가지를 맞춤화합니다.

1. **테이블 및 스키마**

   Adobe Campaign에는 수신자, 게재 로그, 구독 등과 같은 데이터를 식별하기 위한 일반적인 스키마가 포함되어 있습니다.

   [!DNL :bulb:][ Campaign 내장 데이터 모델](../dev/datamodel.md)에 대한 자세한 내용은 이 섹션을 참조하십시오.

   [!DNL :bulb:] 기존 스키마를 확장하거나 새 스키마를 처음부터 만들 수 있습니다. [이 페이지](../dev/customize.md)에서 자세히 알아보십시오.

1. **대시보드 및 목록**

   목록을 쉽게 구성하고 필드를 추가 및 제거하고 열을 사용자 정의할 수 있습니다.

   [!DNL :bulb:][ 이 페이지](../dev/customize.md#gs-lists-and-filters)에서 Campaign의 필터 및 목록을 관리하는 방법을 알아봅니다.

   필요에 따라 새 대시보드를 만들어 Campaign 데이터를 표시할 수도 있습니다.

   [!DNL :bulb:][ 이 페이지](../dev/customize.md#gs-custom-dashboards)에서 자세히 알아보십시오.

1. **보고서**

   Campaign은 게재 모니터링, URL 및 클릭 스트림, 추적, 전달 가능성 지표 등에 대한 내장된 보고서 세트를 제공합니다.

   기본 제공 보고서 외에도 Adobe Campaign을 사용하면 다양한 컨텍스트에서 보고서를 생성하여 다양한 요구를 충족할 수 있습니다. 사용 및 구현 모드의 원칙은 이 문서에 자세히 설명되어 있습니다.

   [!DNL :bulb:][ 이 페이지](reporting.md)에서 Campaign의 보고 기능에 대해 자세히 알아보십시오.


## 캠페인 자동화 설정

여러 채널에서 여러 대상에 대해 복잡한 마케팅 캠페인을 통합 관리하려면 Campaign 자동화 기능을 활용하십시오.

* 워크플로우: 프로세스 및 데이터 관리

* 구독 및 랜딩 페이지

* 유형 규칙: 피로 및 제어 관리

## 배포 확장

### 다중 솔루션 구현

다른 Adobe 솔루션을 사용하는 경우 해당 솔루션을 Campaign 환경에 연결하고 기능을 결합할 수 있습니다.

* Campaign - Journey Orchestration
* Campaign - 실시간 CDP
* Campaign - Experience Cloud 트리거
* Campaign - Experience Manager
* Campaign - Target
* Campaign - Audience Manager/인물 핵심 서비스
* Campaign - 자산
* Campaign - Analytics 데이터 커넥터


SSO(Single Sign-On)를 사용하여 Campaign에 연결할 수도 있습니다. [이 페이지](connect.md)에서 자세히 알아보십시오.

[!DNL :bulb:][ 이 페이지](../connect/integration.md)에서 Adobe Campaign과 통합할 수 있는 Adobe 솔루션의 전체 목록을 살펴보십시오.

### 커넥터

Adobe Campaign을 타사 시스템과 연계하여 다양한 기능을 통합하고 프로세스를 자동화할 수 있습니다.

[!DNL :bulb:][ 이 섹션](../connect/integration.md)에서 사용 가능한 커넥터에 대해 자세히 알아봅니다.

**CRM을 Campaign에 연결하기**

Adobe Campaign 플랫폼을 타사 CRM 시스템에 연결하여 연락처, 계정, 구매 등의 데이터를 동기화할 수 있습니다.

[!DNL :bulb:] 이 섹션에서 CRM 시스템을 Campaign에 연결하는  [방법을 알아봅니다](../connect/integration.md#gs-crm-connectors)

**외부 데이터베이스에 연결하기**

FDA(Federated Data Access) 모듈을 통해 Campaign Cloud 데이터베이스를 외부 시스템에 연결할 수 있습니다.

[!DNL :bulb:]  [이 섹션에서 액세스 매개 변수를 정의하도록 Campaign FDA 모듈을 구성하는 방법을 알아봅니다](../connect/integration.md#gs-fda)
