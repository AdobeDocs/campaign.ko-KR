---
title: 캠페인 외부 계정
description: 캠페인 외부 계정
feature: Application Settings, External Account
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 4%

---


# 외부 계정 구성 {#config-external-accounts}

Adobe Campaign에는 미리 정의된 외부 계정 집합이 포함되어 있습니다. 외부 시스템과의 연결을 설정하기 위해 새 외부 계정을 만들 수 있습니다.

외부 계정은 기술 워크플로우 또는 캠페인 워크플로우와 같은 기술 프로세스에서 사용됩니다. 예를 들어 워크플로우에서 파일 전송을 설정하거나 다른 애플리케이션(Adobe Target, Experience Manager 등)과의 데이터 교환을 설정할 때 외부 계정을 선택해야 합니다.

Adobe Campaign에서 외부 계정에 액세스할 수 있습니다. **[!UICONTROL Explorer]**: 다음으로 이동 **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>* 관리 Cloud Service 사용자는 Adobe에 의해 인스턴스에 대해 외부 계정이 구성되며 수정해서는 안 됩니다.
>
>* 의 맥락에서 [엔터프라이즈(FFDA) 배포](../architecture/enterprise-deployment.md), 특정 **[!UICONTROL Full FDA]** (ffda) 외부 계정은 Campaign 로컬 데이터베이스와 클라우드 데이터베이스 간의 연결을 관리합니다([!DNL Snowflake]).
>

## 캠페인별 외부 계정 {#ac-external-accounts}

Adobe Campaign에서는 특정 프로세스를 활성화하고 실행하는 데 다음 기술 계정을 사용합니다.

### 바운스 메일 {#bounce-mails-external-account}

>[!NOTE]
>
>POP3 기능에 대한 Microsoft Exchange Online OAuth 2.0 인증은 Campaign v8.3부터 사용할 수 있습니다. 버전을 확인하려면 다음을 참조하십시오. [이 섹션](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).
>

다음 **바운스 메일** 외부 계정은 이메일 서비스에 연결하는 데 사용할 외부 POP3 계정을 지정합니다. POP3 액세스용으로 구성된 모든 서버는 반송 메일을 수신하는 데 사용할 수 있습니다.

에서 인바운드 이메일에 대해 자세히 알아보기 [이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html){target="_blank"}.

![](assets/bounce_external_1.png)

을(를) 구성하려면 다음을 수행하십시오. **[!UICONTROL Bounce mails (defaultPopAccount)]** 외부 계정:

* **[!UICONTROL Server]** - POP3 서버의 URL.

* **[!UICONTROL Port]** - POP3 연결 포트 번호. 기본 포트는 110입니다.

* **[!UICONTROL Account]** - 사용자 이름.

* **[!UICONTROL Password]** - 사용자 계정 암호.

* **[!UICONTROL Encryption]** - 다음 사이에 선택한 암호화 유형: **[!UICONTROL By default]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** 또는 **[!UICONTROL POP3S]**.

  다음 **바운스 메일** 외부 계정은 이메일 서비스에 연결하는 데 사용할 외부 POP3 계정을 지정합니다. POP3 액세스용으로 구성된 모든 서버는 반송 메일을 수신하는 데 사용할 수 있습니다.

* **[!UICONTROL Function]** - 인바운드 이메일 또는 SOAP 라우터

![](assets/bounce_external_2.png)

>[!CAUTION]
>
>Microsoft OAuth 2.0을 사용하여 POP3 외부 계정을 구성하기 전에 먼저 Azure 포털에 애플리케이션을 등록해야 합니다. 자세한 정보는 다음을 참조하십시오. [페이지](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.
>

Microsoft OAuth 2.0을 사용하여 외부 POP3을 구성하려면 **[!UICONTROL Microsoft OAuth 2.0]** 옵션을 선택하고 다음 필드를 채웁니다.

* **[!UICONTROL Azure tenant]** - Azure ID(또는 디렉터리(테넌트) ID)는 **기본 사항** azure 포털에서 애플리케이션 개요 드롭다운

* **[!UICONTROL Azure Client ID]** - 클라이언트 ID(또는 애플리케이션(클라이언트) ID)는 **기본 사항** azure 포털에서 애플리케이션 개요 드롭다운

* **[!UICONTROL Azure Client secret]** - 클라이언트 암호 ID는 **클라이언트 암호** 의 열 **인증서 및 암호** Azure 포털에 있는 애플리케이션의 메뉴.

* **[!UICONTROL Azure Redirect URL]** - 리디렉션 URL은 **인증** Azure 포털에 있는 애플리케이션의 메뉴. 다음 구문으로 끝나야 합니다 `nl/jsp/oauth.jsp`, 예: `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

  다른 자격 증명을 입력한 후 **[!UICONTROL Setup the connection]** 외부 계정 구성을 완료합니다.

### 라우팅 {#routing}

다음 **[!UICONTROL Routing]** 외부 계정을 사용하면 설치된 패키지에 따라 Adobe Campaign에서 사용할 수 있는 각 채널을 구성할 수 있습니다.

### 실행 인스턴스 {#execution-instance}

트랜잭션 메시지의 컨텍스트에서 실행 인스턴스는 제어 인스턴스에 연결되어 있습니다. 트랜잭션 메시지 템플릿이 실행 인스턴스에 배포됩니다. 에서 메시지 센터 아키텍처에 대해 자세히 알아보기 [이 페이지](../architecture/architecture.md#transac-msg-archi).

## 외부 시스템 외부 계정에 액세스 {#external-syst-external-accounts}

* **외부 데이터베이스(FDA)** - **외부 데이터베이스** 유형 외부 계정은 FDA(Federated Data Access)를 통해 외부 데이터베이스에 연결하는 데 사용됩니다. 에서 FDA(Federated Data Access) 옵션에 대해 자세히 알아봅니다. [이 섹션](../connect/fda.md).

  Adobe Campaign v8과 호환되는 외부 데이터베이스는 [호환성 매트릭스](../start/compatibility-matrix.md)

* **X(이전 명칭: Twitter)** - **Twitter** 유형 외부 계정은 Campaign을 X 계정에 연결하여 귀하를 대신하여 메시지를 게시하는 데 사용됩니다. 에서 X 통합에 대해 자세히 알아보기 [이 섹션](../connect/ac-tw.md).

## Adobe 솔루션 통합 외부 계정 {#adobe-integration-external-accounts}

* **Adobe Experience Cloud** - **[!UICONTROL Adobe Experience Cloud]** 외부 계정은 IMS(Adobe Identity Management 서비스)를 구현하여 Adobe Campaign에 연결하는 데 사용됩니다. 에서 Identity Management 서비스(IMS) Adobe에 대해 자세히 알아보기 [이 섹션](../start/connect.md#logon-to-ac).

* **웹 분석** - **[!UICONTROL Web Analytics (Adobe Analytics)]** 외부 계정은 Adobe Analytics에서 Adobe Campaign으로 데이터 전송을 구성하는 데 사용됩니다. Adobe Campaign - Adobe Analytics 통합에 대해 자세히 알아보기 [이 페이지](../connect/ac-aa.md).

* **Adobe Experience Manager** - **[!UICONTROL AEM]** 외부 계정을 사용하면 이메일 게재 콘텐츠와 양식을 Adobe Experience Manager에서 직접 관리할 수 있습니다. Adobe Campaign - Adobe Analytics 통합에 대해 자세히 알아보기 [이 페이지](../connect/ac-aem.md).


## CRM 커넥터 외부 계정 {#crm-external-accounts}

* **Microsoft Dynamics CRM** - **[!UICONTROL Microsoft Dynamics CRM]** 외부 계정을 사용하면 Microsoft Dynamics 데이터를 Adobe Campaign으로 가져오고 내보낼 수 있습니다. Adobe Campaign - Microsoft Dynamics CRM 통합에 대해 자세히 알아보기 [이 페이지](../connect/ac-ms-dyn.md).

* **Salesforce.com** - **[!UICONTROL Salesforce CRM]** 외부 계정을 사용하면 Salesforce 데이터를 Adobe Campaign으로 가져오고 내보낼 수 있습니다. Adobe Campaign에 대해 자세히 알아보기 - Salesforce.com CRM 통합 [이 페이지](../connect/ac-sfdc.md).

## 외부 계정 데이터 전송 {#transfer-data-external-accounts}

이러한 외부 계정은 를 사용하여 데이터를 Adobe Campaign으로 가져오거나 내보내는 데 사용할 수 있습니다. **[!UICONTROL Transfer file]** 워크플로우 활동. 자세히 알아보기 **파일 전송** 의 워크플로우에서 [이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html){target="_blank"}.

* **FTP 및 SFTP** - **FTP** 외부 계정을 사용하여 Adobe Campaign 외부의 서버에 대한 액세스를 구성하고 테스트할 수 있습니다. 파일 전송에 사용되는 SFTP 또는 FTP 서버 898과 같은 외부 시스템과의 연결을 설정하려면 고유한 외부 계정을 만들 수 있습니다.

  이렇게 하려면 이 외부 계정에서 SFTP 또는 FTP 서버에 연결하는 데 사용되는 주소와 자격 증명을 지정합니다.

  >[!NOTE]
  >
  >이제 릴리스 8.5부터 SFTP 외부 계정을 구성할 때 개인 키를 사용하여 안전하게 인증할 수 있습니다. [키 관리에 대해 자세히 알아보기](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html){target="_blank"}.

* **Amazon Simple Storage Service (S3)** - **AWS** 커넥터를 사용하여 Adobe Campaign으로 데이터를 가져오거나 내보낼 수 있습니다. **[!UICONTROL Transfer file]** 워크플로우 활동. 이 새 외부 계정을 설정할 때 다음 세부 사항을 제공해야 합니다.

   * **[!UICONTROL AWS S3 Account Server]**: 다음과 같이 채워진 서버의 URL:   `<S3bucket name>.s3.amazonaws.com/<s3object path>`

   * **[!UICONTROL AWS access key ID]**: 에서 AWS 액세스 키 ID를 찾는 방법에 대해 알아봅니다. [Amazon 설명서](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

   * **[!UICONTROL Secret access key to AWS]**: 에서 AWS에 대한 비밀 액세스 키를 찾는 방법에 대해 알아봅니다. [Amazon 설명서](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}.

   * **[!UICONTROL AWS Region]**: 의 AWS 영역에 대해 자세히 알아봅니다. [Amazon 설명서](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}.

   * 다음 **[!UICONTROL Use server side encryption]** 확인란을 통해 파일을 S3 암호화 모드로 저장할 수 있습니다. 에서 액세스 키 ID 및 비밀 액세스 키를 찾는 방법에 대해 알아봅니다. [Amazon 설명서](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

* **Azure Blob 저장소** - **Azure** 외부 계정을 사용하여 Adobe Campaign으로 데이터를 가져오거나 내보낼 수 있습니다. **[!UICONTROL Transfer file]** 워크플로우 활동. 을(를) 구성하려면 다음을 수행하십시오. **Azure** 외부 계정 Adobe Campaign에서 작업하려면 다음 세부 정보를 제공해야 합니다.

   * **[!UICONTROL Server]**: Azure Blob 스토리지 서버의 URL입니다.

   * **[!UICONTROL Encryption]**: 다음 기간 동안의 암호화 유형 **[!UICONTROL None]** 또는 **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: 를 찾는 방법 알아보기 **[!UICONTROL Access key]** 위치: [Microsoft 설명서](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}.
