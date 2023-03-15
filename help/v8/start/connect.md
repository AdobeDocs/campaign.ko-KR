---
title: Campaign v8에 연결
description: Adobe Campaign v8에 연결하고 더욱 쉽게 액세스할 수 있도록 내 컴퓨터에 콘솔을 설치하는 방법을 알아봅니다.
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 445e62c290466003886f2dc49386d0c1edb80eeb
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 3%

---

# Adobe Campaign v8에 연결{#gs-ac-connect}

Campaign 작업을 시작하려면 클라이언트 콘솔을 설치 및 구성해야 합니다.

클라이언트 콘솔은 SOAP 및 HTTP와 같은 표준 인터넷 프로토콜을 통해 Adobe Campaign 애플리케이션 서버와 통신하는 기본 애플리케이션입니다. Campaign 클라이언트 콘솔은 모든 기능과 설정을 중앙 집중화하며 로컬 캐시에 의존하므로 최소한의 대역폭을 필요로 합니다. 배포가 편리하도록 설계된 Campaign 클라이언트 콘솔은 인터넷 브라우저에서 배포하고 자동으로 업데이트될 수 있으며 HTTP(S) 트래픽만 생성하므로 특정 네트워크 구성이 필요하지 않습니다.

시작하기 전에 다음을 수행해야 합니다.

* 에서 Adobe Campaign과의 시스템 및 도구 호환성을 확인합니다. [호환성 매트릭스](compatibility-matrix.md)
* Campaign 서버 URL 가져오기
* Adobe ID을 만들거나 회사에서 사용자 자격 증명을 받습니다
* 시스템에 Microsoft Edge Webview2 런타임을 설치합니다. [자세히 알아보기](#webview)

## 클라이언트 콘솔 설치{#download-ac-console}

### Microsoft Edge Webview2 런타임 {#webview}

Campaign Classic 8.4 빌드 버전에서 클라이언트 콘솔 설치에 Microsoft Edge Webview 2 런타임이 필요합니다.

웹 보기는 기본적으로 Windows 11 운영 체제의 일부로 설치됩니다. 시스템에 아직 없는 경우 Campaign 클라이언트 콘솔 설치 프로그램에서 다운로드하라는 메시지를 표시합니다 [Microsoft 개발자 웹 사이트](http://www.adobe.com/go/acc-ms-webview2-runtime-download_kr){target="_blank"}. Microsoft에서 지원되지 않으므로 다운로드 링크가 Internet Explorer 11 브라우저에서 작동하지 않습니다. 링크에 액세스하려면 다른 브라우저를 사용해야 합니다.

### 콘솔 다운로드{#install-ac-console}

Campaign을 처음 사용하는 경우 클라이언트 콘솔을 다운로드하여 설치해야 합니다.

클라이언트 콘솔을 다운로드할 수 있는 두 가지 옵션이 있습니다.

1. Campaign 관리자는 Adobe에 연결합니다 [소프트웨어 배포](https://experience.adobe.com/#/downloads/content/software-distribution/ko/campaign.html){target="_blank"}.

1. 최종 사용자의 경우 Campaign 관리자가 대신 클라이언트 콘솔을 배포하고 전용 URL을 통해 사용할 수 있도록 합니다.

클라이언트 콘솔 설치 프로그램이 다운로드되면 로컬 컴퓨터에 설치합니다.

클라이언트 콘솔 언어가 설치되면 변경할 수 없습니다.

## 연결 만들기{#create-your-connection}

클라이언트 콘솔이 설치되면 아래 단계에 따라 응용 프로그램 서버에 연결을 만듭니다.

1. 콘솔을 시작하고 오른쪽 모서리에서 링크를 검색하여 연결 구성 화면에 액세스합니다.

1. 클릭 **[!UICONTROL Add > Connection]** Adobe Campaign 애플리케이션 서버의 레이블 및 URL을 입력합니다.

1. URL을 통해 Adobe Campaign 애플리케이션 서버에 대한 연결을 지정합니다. 컴퓨터의 DNS 또는 별칭 또는 IP 주소를 사용합니다.

   예를 들어 [`https://<machine>.<domain>.com`](https://myserver.adobe.com) URL을 입력합니다.

1. 옵션을 선택합니다 **[!UICONTROL Connect with an Adobe ID]**.

1. 클릭 **[!UICONTROL Ok]** 설정을 저장하려면 을 클릭합니다.

예를 들어 테스트, 스테이지 및 프로덕션 환경에 연결하는 데 필요한 만큼 연결을 추가할 수 있습니다.

>[!NOTE]
>
>다음 **[!UICONTROL Add]** 버튼을 사용하면 만들 수 있습니다. **[!UICONTROL folders]** 를 입력하여 모든 연결을 구성할 수 있습니다. 각 연결을 폴더로 끌어다 놓으면 됩니다.

## Adobe Campaign에 로그온 {#logon-to-ac}

Campaign 사용자는 IMS(Adobe Identity Management System)를 통해 Adobe ID을 사용하여 Adobe Campaign 콘솔에 연결합니다. 모든 Adobe 솔루션에서 동일한 ID를 사용할 수 있습니다. 다른 솔루션에서 Adobe Campaign을 사용할 때 연결이 저장됩니다. 의 Adobe IMS에 대해 자세히 알아보십시오 [이 페이지](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"}.

인스턴스에 로그온하려면 아래 단계를 수행하십시오.

1. 콘솔을 시작하고 오른쪽 모서리에서 링크를 검색하여 연결 구성 화면에 액세스합니다.

   ![](assets/connectToCampaign.png)

1. 로그인해야 하는 Campaign 인스턴스를 선택합니다.

1. **[!UICONTROL Ok]**&#x200B;를 클릭합니다.

그런 다음 [Adobe ID](#connect-ims).

![](assets/adobeID.png)

>[!NOTE]
>
>Microsoft Edge Webview2는 프록시 자격 증명을 저장하지 않으므로 첫 번째 연결에서 두 번 인증하도록 콘솔에 요청할 수 있습니다.

## 클라이언트 콘솔 업그레이드{#upgrade-ac-console}

시스템이 최신 릴리스로 업그레이드되면 클라이언트 콘솔을 동일한 버전으로 업데이트해야 합니다. 이는 모범 사례이며 일부 릴리스의 경우 이 업그레이드는 필수입니다. 이 경우, [릴리스 노트](release-notes.md).

관리되는 Cloud Services 사용자로, Adobe이 자동으로 클라이언트 콘솔을 배포합니다. 업그레이드된 환경에 연결하면 팝업 창에서 최신 Client Console 버전을 다운로드하라는 메시지가 표시됩니다. 이 업그레이드를 수락하고 필요에 따라 클라이언트 콘솔을 업데이트해야 합니다.

>[!CAUTION]
>
>Adobe은 옵션을 그만두는 것이 좋습니다 **[!UICONTROL No longer ask this question]** Console의 새 버전을 사용할 수 있을 때 경고가 표시되는지 확인하기 위해 선택하지 않습니다. 이 옵션을 선택하면 사용자에게 콘솔 업그레이드가 필요하다는 메시지가 표시되지 않습니다.


## 사용자에게 액세스 권한 부여{#grant-access}

Adobe Campaign을 사용하면 다양한 운영자에게 할당된 권한을 정의하고 관리할 수 있습니다.

Campaign 관리자는 연산자를 만들고 사용자와 해당 자격 증명을 공유할 책임이 있습니다.

사용자 및 사용 권한을 정의하는 방법에 대해 자세히 알아보십시오 [이 섹션](gs-permissions.md).


## 웹 액세스{#web-access}

HTML 사용자 인터페이스를 사용하여 웹 브라우저를 통해 애플리케이션의 특정 부분에 액세스할 수 있습니다. 보고, 게재 승인, 인스턴스 모니터링 등.

웹 액세스는 콘솔과 유사하지만 기능 세트가 감소된 인터페이스를 제공합니다.

예를 들어 주어진 연산자의 경우 콘솔에 다음과 같은 옵션이 있는 캠페인이 표시됩니다.

![](assets/campaign-from-console.png)

반면에 웹 액세스 기능을 사용하면 주로 볼 수 있습니다.

![](assets/campaign-from-web.png)

웹 액세스는 유효성 검사 프로세스에서도 사용됩니다. 운영자는 승인 요청 이메일을 클릭하고 웹 브라우저를 통해 Campaign에 연결하여 게재 콘텐츠 또는 예산을 유효성 검사하거나 거부할 수 있습니다.

웹에서 Campaign 인스턴스에 액세스하려면 URL은 다음과 같습니다.  `https://<your adobe campaign server>:<port number>/view/home`.
