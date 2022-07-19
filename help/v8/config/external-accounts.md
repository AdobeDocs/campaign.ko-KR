---
title: Campaign 외부 계정
description: Campaign 외부 계정
feature: Application Settings
role: Data Engineer
level: Beginner
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 59046a11c3e057cf41c322f190a9d8aef310c356
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 5%

---

# 외부 계정 구성

Adobe Campaign에는 미리 정의된 외부 계정 집합이 포함되어 있습니다. 외부 시스템과의 연결을 설정하기 위해 새 외부 계정을 만들 수 있습니다.

외부 계정은 기술 워크플로우 또는 캠페인 워크플로우와 같은 기술 프로세스에서 사용됩니다. 예를 들어 워크플로우 또는 다른 애플리케이션(Adobe Target, Experience Manager 등)과 데이터 교환에서 파일 전송을 설정할 때는 외부 계정을 선택해야 합니다.

Adobe Campaign에서 외부 계정에 액세스할 수 있습니다 **[!UICONTROL Explorer]**: 찾아보기 **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>의 컨텍스트에서 [엔터프라이즈(FFDA) 배포](../architecture/enterprise-deployment.md), 특정 **[!UICONTROL Full FDA]** (ffda) 외부 계정은 Campaign 로컬 데이터베이스와 클라우드 데이터베이스() 간의 연결을 관리합니다[!DNL Snowflake]).
></br>관리되는 Cloud Services 사용자로서, 이 외부 계정은 Adobe에 의해 인스턴스에 대해 구성됩니다. 수정해서는 안 됩니다.

## 캠페인 특정 외부 계정

다음 기술 계정은 Adobe Campaign에서 특정 프로세스를 활성화하고 실행하는 데 사용됩니다.

![](../assets/do-not-localize/speech.png)  관리 Cloud Services 사용자로 Campaign에서 제공하는 모든 외부 계정을 Adobe에서 구성합니다.

### 바운스 메일 {#bounce-mails-external-account}

>[!NOTE]
>
>POP3 기능에 대한 Microsoft Exchange Online OAuth 2.0 인증은 Campaign v8.3부터 사용할 수 있습니다. 버전을 확인하려면 다음을 참조하십시오 [이 섹션](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

다음 **바운스 메일** 외부 계정은 전자 메일 서비스에 연결하는 데 사용할 외부 POP3 계정을 지정합니다. POP3 액세스를 위해 구성된 모든 서버를 사용하여 반환 메일을 받을 수 있습니다.

의 인바운드 전자 메일에 대해 자세히 알아보기 [이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html)

![](assets/bounce_external_1.png)

를 구성하려면 **[!UICONTROL Bounce mails (defaultPopAccount)]** 외부 계정:

* **[!UICONTROL Server]**

   POP3 서버의 URL입니다.

* **[!UICONTROL Port]**

   POP3 연결 포트 번호입니다. 기본 포트는 110입니다.

* **[!UICONTROL Account]**

   사용자의 이름입니다.

* **[!UICONTROL Password]**

   사용자 계정 암호입니다.

* **[!UICONTROL Encryption]**

   선택한 암호화 유형 **[!UICONTROL By default]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** 또는 **[!UICONTROL POP3S]**.
다음 **바운스 메일** 외부 계정은 전자 메일 서비스에 연결하는 데 사용할 외부 POP3 계정을 지정합니다. POP3 액세스를 위해 구성된 모든 서버를 사용하여 반환 메일을 받을 수 있습니다.

* **[!UICONTROL Function]**

   인바운드 전자 메일 또는 SOAP 라우터

![](assets/bounce_external_2.png)

>[!IMPORTANT]
>
>Microsoft OAuth 2.0을 사용하여 POP3 외부 계정을 구성하기 전에 먼저 Azure 포털에서 응용 프로그램을 등록해야 합니다. 자세한 정보는 이 [페이지](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)를 참조하십시오.

Microsoft OAuth 2.0을 사용하여 POP3 외부 를 구성하려면 다음을 확인합니다. **[!UICONTROL Microsoft OAuth 2.0]** 옵션을 선택하고 다음 필드를 채웁니다.

* **[!UICONTROL Azure tenant]**

   Azure ID(또는 디렉터리(테넌트) ID)는 **핵심 사항** azure 포털에서 애플리케이션 개요의 드롭다운

* **[!UICONTROL Azure Client ID]**

   클라이언트 ID(또는 애플리케이션(클라이언트) ID)는 **핵심 사항** azure 포털에서 애플리케이션 개요의 드롭다운

* **[!UICONTROL Azure Client secret]**:

   클라이언트 암호 ID는 **클라이언트 암호** 열 **인증서 및 기밀** azure 포털에서 응용 프로그램의 메뉴

* **[!UICONTROL Azure Redirect URL]**:

   리디렉션 URL은 **인증** azure 포털에서 응용 프로그램의 메뉴 다음 구문으로 끝나야 합니다 `nl/jsp/oauth.jsp`예: `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

다른 자격 증명을 입력한 후 **[!UICONTROL Setup the connection]** 외부 계정 구성을 완료합니다.

### 라우팅 {#routing}

다음 **[!UICONTROL Routing]** 외부 계정을 사용하면 설치된 패키지에 따라 Adobe Campaign에서 사용할 수 있는 각 채널을 구성할 수 있습니다.

>[!CAUTION]
>
>다음 **[!UICONTROL Internal email delivery routing]** (defaultEmailBulk) 외부 계정 **필수가 아니어야 합니다.** Adobe Campaign v8에서 사용할 수 있습니다.

### 실행 인스턴스 {#execution-instance}

트랜잭션 메시지 컨텍스트에서 실행 인스턴스는 제어 인스턴스에 연결되고 연결됩니다. 트랜잭션 메시지 템플릿은 실행 인스턴스에 배포됩니다.

![](../assets/do-not-localize/glass.png) 의 메시지 센터 아키텍처에 대해 자세히 알아보기 [이 페이지](../architecture/architecture.md#transac-msg-archi).

## 외부 시스템 외부 계정에 대한 액세스

* **외부 데이터베이스(FDA)**

   를 사용하십시오 **외부 데이터베이스** FDA를 통해 외부 데이터베이스에 연결할 외부 계정을 입력합니다.

   Adobe Campaign v8과 호환되는 외부 데이터베이스는 [호환성 매트릭스](../start/compatibility-matrix.md)

   ![](../assets/do-not-localize/glass.png) 에서 FDA(Federated Data Access) 옵션에 대해 자세히 알아보십시오 [이 섹션](../connect/fda.md).

## Adobe 솔루션 통합 외부 계정

* **Adobe Experience Cloud**

   다음 **[!UICONTROL Adobe Experience Cloud]** 외부 계정은 Adobe IMS를 구현하여 Adobe ID을 사용하여 Adobe Campaign 콘솔에 연결하는 데 사용됩니다.

   ![](../assets/do-not-localize/glass.png) 의 IMS(Adobe Identity Management Service)에 대해 자세히 알아보십시오 [이 섹션](../start/connect.md#connect-ims).

* **웹 분석**

   를 사용하십시오 **[!UICONTROL Web Analytics (Adobe Analytics)]** 외부 계정을 사용하여 Adobe Analytics에서 Adobe Campaign으로 데이터 전송을 구성합니다.

   ![](../assets/do-not-localize/glass.png) Adobe Campaign - Adobe Analytics 통합에 대해 자세히 알아보기 [이 페이지](../connect/ac-aa.md).

   ![](../assets/do-not-localize/speech.png)  관리 Cloud Services 사용자로, [연락처 Adobe](../start/campaign-faq.md#support) Adobe Analytics을 Campaign과 통합하기 위해 사용됩니다.

   * **Adobe Experience Manager**
   다음 **[!UICONTROL AEM]** 외부 계정을 사용하면 Adobe Experience Manager에서 직접 양식을 비롯한 이메일 게재 콘텐츠를 관리할 수 있습니다.

   ![](../assets/do-not-localize/glass.png) Adobe Campaign - Adobe Analytics 통합에 대해 자세히 알아보기 [이 페이지](../connect/ac-aem.md).

   ![](../assets/do-not-localize/speech.png)  관리 Cloud Services 사용자로, [연락처 Adobe](../start/campaign-faq.md#support) Adobe Experience Manager을 Adobe Campaign과 통합하기 위해


## CRM 커넥터 외부 계정

* **Microsoft Dynamics CRM**

   다음 **[!UICONTROL Microsoft Dynamics CRM]** 외부 계정을 사용하여 Microsoft Dynamics 데이터를 Adobe Campaign으로 가져오고 내보낼 수 있습니다.

   ![](../assets/do-not-localize/glass.png) Adobe Campaign - Microsoft Dynamics CRM 통합에서 자세한 내용을 알아보십시오. [이 페이지](../connect/ac-ms-dyn.md).

* **Salesforce.com**

   다음 **[!UICONTROL Salesforce CRM]** 외부 계정을 사용하면 Salesforce 데이터를 Adobe Campaign으로 가져오고 내보낼 수 있습니다.

   ![](../assets/do-not-localize/glass.png) 의 Adobe Campaign - Salesforce.com CRM 통합에 대해 자세히 알아보십시오. [이 페이지](../connect/ac-sfdc.md).

## 데이터 외부 계정 전송

이러한 외부 계정은 데이터를 **[!UICONTROL Transfer file]** 워크플로우 활동.

워크플로우의 파일 전송에 대해 자세히 알아보십시오 [이 페이지](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html)

* **FTP 및 SFTP**

   다음 **FTP** 외부 계정을 사용하면 Adobe Campaign 외부의 서버에 대한 액세스를 구성하고 테스트할 수 있습니다. 파일 전송에 사용되는 SFTP 또는 FTP 서버 898과 같은 외부 시스템과의 연결을 설정하기 위해 자체적인 외부 계정을 만들 수 있습니다.
이렇게 하려면 SFTP 또는 FTP 서버에 연결을 설정하는 데 사용되는 주소와 자격 증명을 이 외부 계정에 지정합니다.

* **Amazon Simple Storage Service (S3)**

   다음 **AWS S3** 커넥터를 사용하여 데이터를 Adobe Campaign으로 가져오거나 내보낼 수 있습니다 **[!UICONTROL Transfer file]** 워크플로우 활동. 이 새 외부 계정을 설정할 때 다음 세부 사항을 제공해야 합니다.

   * **[!UICONTROL AWS S3 Account Server]**: 다음과 같이 채워진 서버 URL:   ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL AWS access key ID]**: 에서 AWS 액세스 키 ID를 찾는 방법을 알아봅니다. [Amazon 설명서](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target=&quot;_blank&quot;}.

   * **[!UICONTROL Secret access key to AWS]**: 에서 AWS에 대한 비밀 액세스 키를 찾는 방법을 알아봅니다 [Amazon 설명서](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target=&quot;_blank&quot;}.

   * **[!UICONTROL AWS Region]**: 의 AWS 지역에 대해 자세히 알아보십시오 [Amazon 설명서](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target=&quot;_blank&quot;}.

   * 다음 **[!UICONTROL Use server side encryption]** 확인란을 통해 파일을 S3 암호화 모드로 저장할 수 있습니다. 에서 액세스 키 ID 및 암호 액세스 키를 찾는 방법을 알아봅니다. [Amazon 설명서](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target=&quot;_blank&quot;}.

* **Azure Blob 스토리지**

   다음 **Azure** 외부 계정은 **[!UICONTROL Transfer file]** 워크플로우 활동. 를 구성하려면 **Azure** Adobe Campaign에서 작업할 외부 계정은 다음 세부 사항을 제공해야 합니다.

   * **[!UICONTROL Server]**: Azure Blob 저장소 서버의 URL입니다.

   * **[!UICONTROL Encryption]**: 암호화 유형 **[!UICONTROL None]** 또는 **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: 를 찾는 방법 알아보기 **[!UICONTROL Access key]** in [Microsoft 설명서](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target=&quot;_blank&quot;}.
