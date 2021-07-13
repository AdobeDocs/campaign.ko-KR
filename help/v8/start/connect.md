---
product: Adobe Campaign
title: Campaign v8에 연결
description: Campaign v8에 연결하는 방법 알아보기
feature: 대상자
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 13f3122a830c723fa940290689c8e3a1baa0443a
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 0%

---

# Adobe Campaign v8에 연결{#gs-ac-connect}

Campaign 클라이언트 콘솔은 Campaign 애플리케이션 서버에 연결할 수 있는 리치 클라이언트입니다.

시작하기 전에 다음을 수행해야 합니다.

* [호환성 매트릭스](compatibility-matrix.md)에서 Adobe Campaign과의 시스템 및 도구 호환성을 확인합니다
* Campaign 서버 URL 가져오기
* Adobe ID을 만들거나 회사에서 사용자 자격 증명을 받을 수 있습니다

## 클라이언트 콘솔 다운로드 및 설치

Campaign을 처음 사용하는 경우 또는 최신 버전으로 업그레이드해야 하는 경우 클라이언트 콘솔을 다운로드하여 설치해야 합니다.

다음 두 가지 옵션을 사용할 수 있습니다.

1. Campaign 관리자는 Adobe [소프트웨어 배포](https://experience.adobe.com/#/downloads/content/software-distribution/encampaign.html)에 연결하고 클라이언트 콘솔 설치 프로그램을 다운로드합니다. 그런 다음 로컬 컴퓨터에 설치할 수 있습니다.

1. 최종 사용자는 콘솔 을 배포할 수 있습니다. Console이 업데이트되면 팝업 창에서 최신 Client Console 버전을 다운로드하라는 메시지가 표시됩니다.

>[!CAUTION]
>
>Adobe은 새 버전의 콘솔을 사용할 수 있을 때 모든 사용자에게 경고하도록 **[!UICONTROL No longer ask this question]** 옵션을 선택 취소하도록 권장합니다.  이 옵션을 선택하면 사용자에게 사용 가능한 새 버전에 대한 정보가 표시되지 않습니다.

## 연결 만들기

클라이언트 콘솔이 새로 설치되면 아래 단계에 따라 응용 프로그램 서버에 연결을 만듭니다.

1. Windows **[!UICONTROL Start]** 메뉴의 **Adobe Campaign** 프로그램 그룹에서 콘솔을 시작합니다.

1. 자격 증명 필드의 오른쪽 위 모서리에 있는 링크를 클릭하여 연결 구성 창에 액세스합니다.

1. **[!UICONTROL Add > Connection]** 을 클릭하고 Adobe Campaign 애플리케이션 서버의 레이블과 URL을 입력합니다.

1. URL을 통해 Adobe Campaign 애플리케이션 서버에 대한 연결을 지정합니다. 컴퓨터의 DNS 또는 별칭 또는 IP 주소를 사용합니다.

   예를 들어 [`https://<machine>.<domain>.com`](https://myserver.adobe.com) 유형 URL을 사용할 수 있습니다.

1. 조직에 대해 IMS(Adobe Identity Management 시스템)가 구성된 경우 옵션 **[!UICONTROL Connect with an Adobe ID]** 을 선택합니다.

1. **[!UICONTROL Ok]** 을 클릭하여 설정을 저장합니다.

예를 들어 테스트, 스테이지 및 프로덕션 환경에 연결하는 데 필요한 만큼 연결을 추가할 수 있습니다.

>[!NOTE]
>
>**[!UICONTROL Add]** 버튼을 사용하면 **[!UICONTROL folders]**&#x200B;을 만들어 모든 연결을 구성할 수 있습니다. 각 연결을 폴더로 끌어다 놓으면 됩니다.

## Adobe Campaign에 로그온

기존 인스턴스에 로그인하려면 아래 단계를 수행하십시오.

1. Windows **[!UICONTROL Start]** 메뉴의 **Adobe Campaign** 프로그램 그룹에서 콘솔을 시작합니다.

1. 자격 증명 필드의 오른쪽 위 모서리에 있는 링크를 클릭하여 연결 구성 창에 액세스합니다.

   ![](assets/connectToCampaign.png)

1. 로그인해야 하는 Campaign 인스턴스를 선택합니다.

1. **[!UICONTROL Ok]**&#x200B;를 클릭합니다.

1. 그런 다음 Campaign에 로그인할 수 있습니다.

   ![](assets/adobeID.png)

## 사용자에게 액세스 권한 부여

Adobe Campaign을 사용하면 다양한 운영자에게 할당된 권한을 정의하고 관리할 수 있습니다. 권한을 부여하거나 거부한 권한 및 제한 세트입니다.

* 특정 기능에 대한 액세스(명명된 권한을 통해),
* 특정 요소에 액세스하고
* 요소(게재, 연락처, 캠페인, 그룹 등)를 만들거나 수정하거나 삭제합니다.

사용자 및 [이 섹션](permissions.md)에서 사용자 권한을 정의하는 방법에 대해 자세히 알아보십시오.

Campaign 관리자는 연산자를 만들고 사용자와 해당 자격 증명을 공유할 책임이 있습니다.

## Adobe ID을 통해 Campaign에 연결{#connect-ims}

Campaign 사용자는 IMS(Adobe Identity Management System)를 통해 Adobe ID을 사용하여 Adobe Campaign 콘솔에 연결합니다. 모든 Adobe 솔루션에서 동일한 ID를 사용할 수 있습니다. 다른 솔루션에서 Adobe Campaign을 사용할 때 연결이 저장됩니다.

[이 페이지](https://helpx.adobe.com/enterprise/using/identity.html)에서 Adobe IMS에 대해 자세히 알아보십시오.

## 웹 액세스{#web-access}

HTML 사용자 인터페이스를 사용하여 웹 브라우저를 통해 애플리케이션의 특정 부분에 액세스할 수 있습니다. 보고, 게재 승인, 인스턴스 모니터링 등.

웹 액세스는 콘솔과 유사하지만 기능 세트가 감소된 인터페이스를 제공합니다.

예를 들어 주어진 연산자의 경우 콘솔에 다음과 같은 옵션이 있는 캠페인이 표시됩니다.

![](assets/campaign-from-console.png)

반면에 웹 액세스 기능을 사용하면 주로 볼 수 있습니다.

![](assets/campaign-from-web.png)

웹 액세스는 유효성 검사 프로세스에서도 사용됩니다. 운영자는 승인 요청 이메일을 클릭하고 웹 브라우저를 통해 Campaign에 연결하여 게재 콘텐츠 또는 예산을 유효성 검사하거나 거부할 수 있습니다.

웹에서 Campaign 인스턴스에 액세스하려면 URL은 다음과 같습니다.  `https://<your adobe campaign server>:<port number>/view/home`
