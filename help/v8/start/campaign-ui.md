---
title: Campaign 사용자 인터페이스 검색
description: Campaign 사용자 인터페이스를 찾아보고 사용하는 방법 알아보기
feature: Overview
role: User
level: Beginner
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
source-git-commit: 9d5a2ca1e9858a727377b8afa6bdd7e3761c1b56
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 5%

---

# 사용자 인터페이스 살펴보기 {#ui-client-console}

클라이언트 콘솔 또는 웹 사용자 인터페이스를 통해 Adobe Campaign에 액세스할 수 있습니다. API를 사용하여 데이터를 관리하고 Campaign 플랫폼에서 작업을 수행할 수도 있습니다.

>[!CAUTION]
>
>이 설명서는 Campaign 클라이언트 콘솔 사용에 중점을 두고 있습니다. Campaign 웹 사용자 인터페이스를 사용하는 경우 [이 설명서](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html?lang=ko){target="_blank"}를 참조하세요.

* **클라이언트 콘솔** - Campaign 클라이언트 콘솔은 SOAP 및 HTTP와 같은 표준 인터넷 프로토콜을 통해 Adobe Campaign 애플리케이션 서버와 통신하는 기본 애플리케이션입니다. Campaign 클라이언트 콘솔은 모든 기능과 설정을 중앙 집중화하며 로컬 캐시에 의존하기 때문에 최소한의 대역폭이 필요합니다. 손쉬운 배포를 위해 설계된 Campaign 클라이언트 콘솔은 인터넷 브라우저에서 배포하고 자동으로 업데이트할 수 있으며 HTTP(S) 트래픽만 생성하므로 특정 네트워크 구성이 필요하지 않습니다. [자세히 알아보기](#ui-access)

  [이 섹션](../start/connect.md)에서 Campaign 클라이언트 콘솔을 설치하고 구성하는 방법을 알아봅니다.

* **웹 사용자 인터페이스** - v8.6.1 릴리스를 시작하는 Campaign v8 사용자는 이제 중앙 Adobe Experience Cloud 사용자 인터페이스를 통해 사용할 수 있는 웹 환경에 액세스할 수 있습니다. 그런 다음 웹 브라우저에서 Adobe Campaign에 연결할 수 있습니다. 이 새 인터페이스를 사용하면 주요 마케팅 작업을 생성, 관리 및 실행할 수 있습니다. 그러나 모든 Campaign 기능을 사용할 수는 없습니다. [자세히 알아보기](#ac-web-ui).

  >[!AVAILABILITY]
  >
  >Campaign 웹 사용자 인터페이스는 Adobe ID을 사용하여 Adobe Campaign에 연결하는 사용자만 사용할 수 있습니다. [IMS(Identity Management 시스템) Adobe](https://helpx.adobe.com/kr/enterprise/using/identity.html){target="_blank"}에 대해 자세히 알아보세요.
  >

* **웹 액세스** - Adobe Campaign 웹 액세스 기능을 사용하면 HTML 사용자 인터페이스를 사용하여 웹 브라우저에서 Campaign 기능의 하위 집합에 액세스할 수 있습니다. 이 웹 인터페이스를 사용하여 보고서에 액세스하고, 메시지를 제어 및 검증하고, 모니터링 대시보드에 액세스합니다.  이 섹션](../start/connect.md#web-access)에서 Campaign 웹 액세스 [에 대해 자세히 알아보세요.

* **API** - 더 많은 사용 사례를 해결하기 위해 SOAP 프로토콜을 통해 노출된 웹 서비스 API를 사용하여 외부 응용 프로그램에서 시스템을 호출할 수 있습니다. 이 페이지](../dev/api.md)에서 Campaign API [에 대해 자세히 알아보세요.


## 클라이언트 콘솔 작업 {#ui-access}

Campaign 클라이언트 콘솔은 SOAP 및 HTTP와 같은 표준 인터넷 프로토콜을 통해 Adobe Campaign 애플리케이션 서버와 통신하는 기본 애플리케이션입니다. Campaign 클라이언트 콘솔은 모든 기능과 설정을 중앙 집중화하며 로컬 캐시에 의존하기 때문에 최소한의 대역폭이 필요합니다. 손쉬운 배포를 위해 설계된 Campaign 클라이언트 콘솔은 인터넷 브라우저에서 배포하고 자동으로 업데이트할 수 있으며 HTTP(S) 트래픽만 생성하므로 특정 네트워크 구성이 필요하지 않습니다.  [Campaign 클라이언트 콘솔에 대해 자세히 알아보세요](../start/connect.md). 클라이언트 콘솔 홈 페이지의 전용 카드에서 Campaign 웹 사용자 인터페이스로 전환할 수 있습니다.

![](assets/web-ui.png)


>[!NOTE]
>
>새 액세스 카드가 표시되지 않으면 Adobe Experience Cloud 외부 계정 내에 **서버**, **테넌트**, **콜백 서버** 및 **연결 표시** 필드가 비어 있지 않은지 확인하십시오.


웹 브라우저를 사용하여 Campaign에 액세스할 수도 있습니다. 이 컨텍스트에서는 Campaign 기능의 하위 집합만 사용할 수 있습니다. [자세히 알아보기](#web-browser)

### 인터페이스 찾아보기 {#ui-browse}

Campaign 클라이언트 콘솔에 연결되면 홈 페이지에 액세스합니다. 링크를 열어 기능에 액세스합니다. 인터페이스에서 사용할 수 있는 기능 세트는 옵션 및 권한에 따라 다릅니다.

홈페이지의 중앙 섹션에서 링크를 사용하여 Campaign 도움말 자료, 커뮤니티 및 지원 웹 사이트에 액세스합니다. 중앙 카드를 사용하여 새 Campaign 웹 사용자 인터페이스와 Campaign 컨트롤 패널을 탐색할 수 있습니다.

상단 섹션의 탭을 탐색하여 Campaign 주요 기능에 액세스합니다.

![](assets/overview-home.png)

>[!NOTE]
>
>액세스할 수 있는 핵심 기능 목록은 사용 권한 및 구현에 따라 다릅니다.

각 기능에 대해 **[!UICONTROL Browsing]** 섹션의 주요 기능 집합에 액세스할 수 있습니다. **[!UICONTROL More]** 링크를 사용하여 다른 모든 구성 요소에 액세스할 수 있습니다.

예를 들어 **[!UICONTROL Profiles and targets]** 탭으로 이동할 때 수신자 목록, 구독 서비스, 기존 타겟팅 워크플로 및 이러한 모든 구성 요소를 만들기 위한 바로 가기에 액세스할 수 있습니다.

![](assets/overview-list.png)

화면에서 요소를 선택하면 콘텐츠를 쉽게 찾아볼 수 있도록 새 탭에 로드됩니다.

![](assets/new-tab.png)

### 요소 만들기 {#create-an-element}

화면 왼쪽의 **[!UICONTROL Create]** 섹션에서 바로 가기를 사용하여 새 요소를 추가합니다. 목록 위에 있는 **[!UICONTROL Create]** 단추를 사용하여 현재 목록에 새 요소를 추가할 수도 있습니다.

예를 들어 게재 페이지에서 **[!UICONTROL Create]** 단추를 사용하여 새 게재를 만듭니다.

![](assets/new-recipient.png)

<!--
## Use a web browser {#web-browser}

You can also access a subset of Campaign capabilities through the a web browser.

The web access interface is similar to the console interface. From a browser, you can use the same navigation and display features as in the console, but you can perform only a reduced set of actions on campaigns. For example, you can view and cancel campaigns, but you cannot modify campaigns. 

[Learn more about Campaign web access](../start/connect.md#web-access).-->

### 캠페인 탐색기 액세스 {#ac-explorer-ui}

모든 Adobe Campaign 기능 및 설정에 액세스하려면 캠페인 탐색기를 탐색하십시오.

![](assets/explorer.png)

이 작업 영역을 사용하면 탐색기 트리에 액세스하여 모든 기능과 옵션을 찾아볼 수 있습니다.

* 왼쪽 섹션에는 캠페인 탐색기 트리가 표시되며, 사용자 권한에 따라 인스턴스의 모든 구성 요소와 설정을 검색할 수 있습니다. [이 페이지](../audiences/folders-and-views.md)에 설명된 대로 폴더를 추가하고 사용자 지정할 수 있습니다.

* 상단 섹션에는 현재 폴더의 레코드 목록이 표시됩니다. 이러한 목록은 완전히 사용자 지정할 수 있습니다. [자세히 알아보기](../config/ui-settings.md)

* 아래 섹션에는 선택한 레코드의 세부 정보가 표시됩니다.


## Campaign 웹 사용자 인터페이스 {#ac-web-ui}

v8.6.1 릴리스를 시작하는 Campaign v8 클라이언트 콘솔 사용자는 이제 중앙 Adobe Experience Cloud 사용자 인터페이스를 통해 사용 가능한 웹 환경에 액세스할 수 있습니다. Experience Cloud는 Adobe의 디지털 마케팅 애플리케이션, 제품 및 서비스 통합 제품군입니다. 직관적인 인터페이스에서 클라우드 애플리케이션, 제품 기능, 서비스에 빠르게 액세스할 수 있습니다. 

![Adobe Campaign 웹 사용자 인터페이스 홈 페이지](assets/ac-web-home.png)

>[!AVAILABILITY]
>
>Campaign 웹 사용자 인터페이스는 Adobe ID을 사용하여 Adobe Campaign에 연결하는 사용자만 사용할 수 있습니다. [IMS(Identity Management 시스템) Adobe](https://helpx.adobe.com/kr/enterprise/using/identity.html){target="_blank"}에 대해 자세히 알아보세요.
>

[이 설명서](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html?lang=ko){target="_blank"}에서 새 Campaign 웹 사용자 인터페이스에 대해 자세히 알아보세요. Campaign 웹 사용자 인터페이스 설명서에서 전용 [자주 묻는 질문 페이지](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/faq){target="_blank"}를 방문할 수도 있습니다.

추가 및 고급 기능, 구성 및 설정은 클라이언트 콘솔에서만 사용할 수 있습니다. Campaign 웹 사용자 인터페이스 설명서 [의 두 사용자 인터페이스에서 사용할 수 있는 기능에 대해 자세히 알아보세요](https://experienceleague.adobe.com/docs/campaign-web/v8/start/capability-matrix.html?lang=ko){target="_blank"}.


## 지원 언어 {#languages}

지원되는 언어는 사용자 인터페이스에 따라 다릅니다.

* Campaign v8 클라이언트 콘솔 인터페이스의 경우 지원되는 언어는 다음과 같습니다.

   * 영어(영국)
   * 영어(미국)
   * 프랑스어
   * 독일어
   * 일본어


  >[!CAUTION]
  >
  >언어는 설치 프로세스 중에 선택되며 나중에 변경할 수 없습니다.

* Campaign 웹 사용자 인터페이스가 지원하는 언어에 대해서는 [이 페이지를 참조하세요](https://experienceleague.adobe.com/docs/campaign-web/v8/start/connect-to-campaign.html#language-pref){target="_blank"}.


언어는 날짜 및 시간 형식에 영향을 줍니다.

미국 영어와 영국 영어의 주요 차이점은 다음과 같습니다.

<table> 
 <thead> 
  <tr> 
   <th> 형식<br /> </th> 
   <th> 영어(미국)<br /> </th> 
   <th> 영어(EN)<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 날짜<br /> </td> 
   <td> 주간이 일요일<br />에 시작 </td> 
   <td> 주간이 월요일<br />에 시작 </td> 
  </tr> 
  <tr> 
   <td> 간단한 날짜<br /> </td> 
   <td> <p>%2M/%2D/%4Y</p><p><strong>예: 2018/09/25</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y</p><p><strong>예: 2018/25/09</strong></p> </td> 
  </tr> 
  <tr> 
   <td> 시간이 <br />인 간단한 날짜 </td> 
   <td> <p>%2M/%2D/%4Y %I:%2N:%2S %P</p><p><strong>예: 2018/09/25 오후 10:47:25</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y %2H:%2N:%2S</p><p><strong>예: 2018/25/09 22:47:25</strong></p> </td> 
  </tr> 
 </tbody> 
</table>
