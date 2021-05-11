---
solution: Campaign
product: Adobe Campaign
title: Campaign v8에 연결하는 방법 알아보기
description: Campaign v8에 연결
feature: 대상
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
translation-type: tm+mt
source-git-commit: 1ac6b58e1d5731d4df4d6d7c6a9b25f0f41ff563
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 4%

---

# Adobe Campaign v8{#gs-ac-connect}에 연결

캠페인 클라이언트 콘솔은 캠페인 응용 프로그램 서버에 연결할 수 있는 리치 클라이언트입니다.

시작하기 전에 다음을 수행해야 합니다.

* [호환성 매트릭스](compatibility-matrix.md)에서 Adobe Campaign과 시스템 및 도구 호환성 확인
* 캠페인 서버 URL 가져오기
* 사용자 자격 증명 얻기

## 클라이언트 콘솔 다운로드 및 설치

처음 Campaign을 사용하거나 새로운 버전으로 업그레이드해야 하는 경우 클라이언트 콘솔을 다운로드하여 설치해야 합니다.

두 가지 옵션을 사용할 수 있습니다.

1. 캠페인 관리자는 Adobe [소프트웨어 배포](https://experience.adobe.com/#/downloads/content/software-distribution/encampaign.html)에 연결하고 클라이언트 콘솔 설치 프로그램을 다운로드합니다. 그런 다음 로컬 컴퓨터에 설치할 수 있습니다.

1. 최종 사용자로서 Adobe은 사용자를 위해 콘솔을 배포할 수 있습니다.콘솔이 업데이트되면 팝업 창에서 최신 클라이언트 콘솔 버전을 다운로드하라는 메시지가 표시됩니다.

>[!CAUTION]
>
>Adobe에서는 **[!UICONTROL No longer ask this question]** 옵션을 선택하지 않은 상태에서 새 버전의 콘솔을 사용할 수 있을 때 모든 사용자에게 경고가 표시되는지 확인할 것을 권장합니다.  이 옵션을 선택하면 사용자에게 사용 가능한 새 버전에 대한 정보를 제공하지 않습니다.

## 연결 만들기

클라이언트 콘솔이 새로 설치되면 아래 절차에 따라 응용 프로그램 서버에 연결을 만듭니다.

1. **Adobe Campaign** 프로그램 그룹의 Windows **[!UICONTROL Start]** 메뉴에서 콘솔을 시작합니다.

1. 자격 증명 필드의 오른쪽 상단에 있는 링크를 클릭하여 연결 구성 창에 액세스합니다.

1. **[!UICONTROL Add > Connection]**&#x200B;을 클릭하고 Adobe Campaign 응용 프로그램 서버의 레이블과 URL을 입력합니다.

1. URL을 통해 Adobe Campaign 응용 프로그램 서버에 대한 연결을 지정합니다. 컴퓨터의 DNS 또는 별칭 또는 IP 주소를 사용합니다.

   예를 들어 [`https://<machine>.<domain>.com`](https://myserver.adobe.com) 유형 URL을 사용할 수 있습니다.

1. Adobe Identity Management 시스템(IMS)이 조직에 맞게 구성된 경우 **[!UICONTROL Connect with an Adobe ID]** 옵션을 선택합니다.

1. 설정을 저장하려면 **[!UICONTROL Ok]**&#x200B;을 클릭합니다.

예를 들어 테스트, 스테이지 및 프로덕션 환경에 연결하는 데 필요한 만큼 연결을 추가할 수 있습니다.

>[!NOTE]
>
>**[!UICONTROL Add]** 단추를 사용하면 **[!UICONTROL folders]**&#x200B;을(를) 만들어 모든 연결을 구성할 수 있습니다. 각 연결을 하나의 폴더로 드래그하여 놓으면 됩니다.

## Adobe Campaign에 로그온

기존 인스턴스에 로그온하려면 아래 단계를 수행하십시오.

1. **Adobe Campaign** 프로그램 그룹의 Windows **[!UICONTROL Start]** 메뉴에서 콘솔을 시작합니다.

1. 자격 증명 필드의 오른쪽 상단에 있는 링크를 클릭하여 연결 구성 창에 액세스합니다.

1. 로그인해야 하는 캠페인 인스턴스를 선택합니다.

1. **[!UICONTROL Ok]**&#x200B;을(를) 클릭합니다.

1. 사용자 로그인 자격 증명을 입력하고 **[!UICONTROL LOG IN]**&#x200B;을 클릭합니다.

   ![](assets/sign-in-v8.png)

구성에 따라 자격 증명은 다음과 같습니다.

* 액세스 권한을 부여받은 캠페인 관리자가 제공한 값
* Adobe ID

## 사용자에게 액세스 권한 부여

Adobe Campaign에서는 다양한 연산자에 할당된 권한을 정의하고 관리할 수 있습니다. 다음은 권한을 부여하거나 거부하는 권한 및 제한 세트입니다.

* 특정 기능에 대한 액세스(명명된 권한을 통해),
* 특정 요소에 대한 액세스,
* 요소(배달, 연락처, 캠페인, 그룹 등)를 만들거나 수정 및/또는 삭제합니다.

사용자에 대한 자세한 내용과 권한을 [이 섹션](permissions.md)에서 정의하는 방법에 대해 알아보십시오.

캠페인 관리자는 연산자를 만들고 사용자와 해당 자격 증명을 공유할 책임이 있습니다.

## Adobe ID{#connect-ims}에서 캠페인에 연결

캠페인 사용자는 IMS(Adobe Identity Management System)를 통해 Adobe ID을 사용하여 Adobe Campaign 콘솔에 연결할 수 있습니다. 이 구현은 다음과 같은 이점을 제공합니다.

*  모든 Experience Cloud 솔루션에 동일한 ID를 사용할 수 있습니다.
* 서로 다른 통합으로 Adobe Campaign을 사용하는 경우 연결이 기억됩니다.
* 강력한 암호 관리 정책
* 페더레이션 ID 계정 사용(외부 ID 공급자).

:speech_bal풍선:관리 Cloud Services 사용자는 [Adobe](support.md#support)에 연락하여 캠페인에 Adobe IMS를 구현합니다.

## LDAP 로그인을 사용하여 캠페인에 연결

사용자가 LDAP 인증을 통해 플랫폼에 액세스할 수 있도록 Adobe Campaign을 구성할 수 있습니다.

:speech_bal풍선:관리 Cloud Services 사용자는 [Adobe](support.md#support)에 연락하여 Campaign과 LDAP 통합을 구성합니다.


## 웹 액세스

HTML 사용자 인터페이스를 사용하는 간단한 웹 브라우저를 통해 애플리케이션의 특정 부분에 액세스할 수 있습니다.보고, 배달 승인, 인스턴스 모니터링 등
