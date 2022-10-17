---
title: Campaign 프로세스 및 구성 요소 이해
description: Campaign 프로세스 및 구성 요소 이해
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: 46be0379610a6a4a3491d49ce096c64270ed8016
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 1%

---

# Campaign 프로세스 및 구성 요소 이해 {#components-and-processes}

Adobe Campaign 는 이메일, 모바일, 소셜 및 오프라인 캠페인을 자동화하는 크로스 채널 마케팅 솔루션입니다. Adobe Campaign은 고객 데이터와 프로필에 액세스할 수 있는 중앙 위치를 제공합니다. Adobe Campaign을 사용하여 고객에게 일관된 경험을 조정하고, 채널을 통해 마케팅을 디자인하고, 실행하고, 개인화하는 한편, 모든 장치와 터치포인트에서 고객 경험을 개선합니다. Adobe Campaign을 사용하면 여러 데이터 소스를 관리하고, 대상 세그먼트를 정의하며, 드래그 앤 드롭 시각적 워크플로우 인터페이스를 통해 여러 단계의 크로스 채널 캠페인을 계획 및 실행할 수 있습니다.

Campaign 주요 기능에 대한 자세한 내용은 [이 페이지](../start/get-started.md).

## Campaign 구성 요소 {#ac-components}

Adobe Campaign 구성 요소 및 글로벌 아키텍처는 아래에 설명되어 있습니다.

![](assets/ac-components.png)

### 프레젠테이션 레이어{#presentation-layer}

리치 클라이언트, 씬 클라이언트 또는 API 통합을 통해 Adobe Campaign에 액세스할 수 있습니다.

* 리치 클라이언트

   Campaign Rich 클라이언트는 SOAP 및 HTTP와 같은 표준 인터넷 프로토콜을 통해 Adobe Campaign 애플리케이션 서버와 통신하는 기본 애플리케이션입니다.

   Campaign 클라이언트 콘솔은 모든 기능과 설정을 중앙 집중화하며 로컬 캐시에 의존하므로 최소한의 대역폭을 필요로 합니다. 배포가 편리하도록 설계된 Campaign 클라이언트 콘솔은 인터넷 브라우저에서 배포하고 자동으로 업데이트될 수 있으며 HTTP(S) 트래픽만 생성하므로 특정 네트워크 구성이 필요하지 않습니다.

   ![](../assets/do-not-localize/glass.png) [Campaign 클라이언트 콘솔 자세히 알아보기](../start/connect.md)

* 씬 클라이언트

   Adobe Campaign 웹 액세스 기능을 사용하면 HTML 사용자 인터페이스를 사용하여 웹 브라우저로 Campaign 기능의 하위 세트에 액세스할 수 있습니다. 이 웹 인터페이스를 사용하여 보고서에 액세스하고, 메시지를 제어 및 확인하고, 모니터링 대시보드에 액세스하는 등의 작업을 수행할 수 있습니다.

   ![](../assets/do-not-localize/glass.png) [Campaign 웹 액세스 자세히 알아보기](../start/connect.md)

* API를 사용하는 외부 애플리케이션

   경우에 따라 SOAP 프로토콜을 통해 노출된 웹 서비스 API를 사용하여 외부 애플리케이션에서 시스템을 호출할 수 있습니다.

   ![](../assets/do-not-localize/glass.png) [Campaign API에 대해 자세히 알아보기](../dev/api.md).

### 지속성 계층{#persistance-layer}

Campaign 데이터베이스는 지속성 레이어로 사용되며 Adobe Campaign에서 관리하는 거의 모든 정보 및 데이터를 포함합니다. 여기에는 다음이 포함됩니다. 프로필, 구독, 콘텐츠 등의 기능 데이터 게재 작업 및 로그, 추적 로그 등의 기술 데이터. 및 작업 데이터(구매, 리드)

대부분의 Adobe Campaign 구성 요소가 작업을 수행하기 위해 데이터베이스에 액세스해야 하므로(리디렉션 모듈을 제외하고) 데이터베이스의 신뢰성이 가장 중요합니다.

### 논리 애플리케이션 계층{#logical-app-layer}

Campaign 논리 애플리케이션 계층은 복잡한 비즈니스 요구 사항을 충족하도록 쉽게 구성할 수 있습니다. 개방적이고 확장 가능한 아키텍처를 만들기 위해 결합하는 다양한 애플리케이션을 사용하는 단일 플랫폼으로 Campaign을 사용할 수 있습니다. 각 Campaign 인스턴스는 애플리케이션 레이어의 프로세스 컬렉션으로, 일부는 공유되고 일부는 전용으로 사용됩니다.

## Campaign 관리 Cloud Services{#ac-managed-services}

Adobe Campaign v8이 as a Managed Service으로 배포됩니다. 사용자 인터페이스, 실행 관리 엔진 및 Campaign 데이터베이스를 포함한 Adobe Campaign의 모든 구성 요소는 이메일 실행, 미러 페이지, 추적 서버 및 구독 취소 페이지/기본 설정 센터 및 랜딩 페이지와 같은 외부 웹 구성 요소를 포함하여 Adobe에 의해 완전히 호스팅됩니다.

## Campaign 프로세스

Campaign 웹 서버는 Campaign 웹 프로세스에 대한 액세스를 제어합니다. Javascript는 핵심 제품 기능 및 사용자 지정에 사용되는 서버측 언어입니다. Tomcat은 백엔드 엔진이며 웹 프로세스의 일부로 Campaign 제품에 포함됩니다. Javascript는 JSP 또는 JSSP 페이지에서 동적 컨텐츠를 렌더링하는 데 사용됩니다.

![](assets/ac-processes.png)

Campaign 클라이언트 콘솔은 HTTP를 통해 SOAP XML을 사용하여 웹 서버에 연결합니다. 웹 서버는 보안 계층을 제공하고, Javascript를 사용하여 요청을 응용 프로그램 레이어에 전달하며, Campaign 내부 프로세스는 SQL을 사용하여 데이터베이스에 대한 액세스를 제공합니다.

Campaign 프로세스 간의 전체 통신은 다음 독립형 배포 다이어그램에 설명되어 있습니다. 모든 캠페인 구성 요소가 동일한 컴퓨터에 설치됩니다.

![](assets/ac-standalone.png)

사용자는 HTTP를 사용하여 Campaign 애플리케이션 서버에 연결합니다. 모든 데이터와 정보는 Campaign 데이터베이스에서 관리됩니다. Campaign 개발자가 구성 변경 작업을 수행하면 데이터베이스에 캡처됩니다. 마케터가 새 캠페인을 만드는 경우 이 새 캠페인과 관련된 모든 정보와 데이터도 데이터베이스에서 관리됩니다. 마케터가 캠페인을 실행하면 이메일 게재가 SMTP 서버를 통해 Campaign 서버의 프로필로 전송됩니다. 프로필은 이메일을 여는 등의 이메일 게재와 상호 작용하므로 추적 데이터가 추적 서버로 다시 전송됩니다.

![](../assets/do-not-localize/glass.png) [Campaign 프로세스에 대해 자세히 알아보기](../architecture/general-architecture.md#dev-env).
