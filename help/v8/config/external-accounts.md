---
title: Campaign 외부 계정
description: Campaign 외부 계정
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 4%

---

# 외부 계정 구성

Adobe Campaign에는 미리 정의된 외부 계정 집합이 포함되어 있습니다. 외부 시스템과의 연결을 설정하기 위해 새 외부 계정을 만들 수 있습니다.

외부 계정은 기술 워크플로우 또는 캠페인 워크플로우와 같은 기술 프로세스에서 사용됩니다. 예를 들어 워크플로우 또는 다른 애플리케이션(Adobe Target, Experience Manager 등)과 데이터 교환에서 파일 전송을 설정할 때는 외부 계정을 선택해야 합니다.

Adobe Campaign에서 외부 계정에 액세스할 수 있습니다 **[!UICONTROL Explorer]**: 찾아보기 **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>특정 **[!UICONTROL Full FDA]** (ffda) 외부 계정은 Campaign 로컬 데이터베이스와 클라우드 데이터베이스() 간의 연결을 관리합니다[!DNL Snowflake]).
>
>관리되는 Cloud Services 사용자로서, 이 외부 계정은 Adobe에 의해 인스턴스에 대해 구성됩니다. 수정해서는 안 됩니다.


## 캠페인 특정 외부 계정

다음 기술 계정은 Adobe Campaign에서 특정 프로세스를 활성화하고 실행하는 데 사용됩니다.

![](../assets/do-not-localize/speech.png)  관리 Cloud Services 사용자로 Campaign에서 제공하는 모든 외부 계정을 Adobe에서 구성합니다.

* **바운스 메일(POP3)**

   다음 **바운스 메일** 외부 계정은 전자 메일 서비스에 연결하는 데 사용할 외부 POP3 계정을 지정합니다. POP3 액세스를 위해 구성된 모든 서버를 사용하여 반환 메일을 받을 수 있습니다.

   ![](../assets/do-not-localize/book.png) 의 인바운드 전자 메일에 대해 자세히 알아보기 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html){target=&quot;_blank&quot;}

* **라우팅**

   다음 **[!UICONTROL Routing]** 외부 계정을 사용하면 설치된 패키지에 따라 Adobe Campaign에서 사용할 수 있는 각 채널을 구성할 수 있습니다.

   >[!CAUTION]
   >
   >다음 **[!UICONTROL Internal email delivery routing]** (defaultEmailBulk) 외부 계정 **필수가 아니어야 합니다.** Adobe Campaign v8에서 사용할 수 있습니다.

* **실행 인스턴스**

   트랜잭션 메시지 컨텍스트에서 실행 인스턴스는 제어 인스턴스에 연결되고 연결됩니다. 트랜잭션 메시지 템플릿은 실행 인스턴스에 배포됩니다.

   ![](../assets/do-not-localize/glass.png) 의 메시지 센터 아키텍처에 대해 자세히 알아보기 [이 페이지](../dev/architecture.md#transac-msg-archi).

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

   ![](../assets/do-not-localize/glass.png) Adobe Campaign - Microsoft Dynamics CRM 통합에서 자세한 내용을 알아보십시오. [이 페이지](../connect/crm.md).

   사용 **[!UICONTROL Web API]** 배포 유형 및 **[!UICONTROL Password credentials]** 인증, 다음 세부 정보를 제공해야 합니다.

   * **[!UICONTROL Account]**: Microsoft CRM에 로그인하는 데 사용되는 계정입니다.

   * **[!UICONTROL Server]**: Microsoft CRM 서버의 URL.

   * **[!UICONTROL Client identifier]**: 클라이언트 ID: **[!UICONTROL Update your code]** 카테고리, **[!UICONTROL Client ID]** 필드.

   * **[!UICONTROL CRM version]**: 다음 사이의 CRM 버전 **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** 또는 **[!UICONTROL Dynamics CRM 2016]**.
   사용 **[!UICONTROL Web API]** 배포 유형 및 **[!UICONTROL Certificate]** 인증, 다음 세부 정보를 제공해야 합니다.

   * **[!UICONTROL Server]**: Microsoft CRM 서버의 URL.

   * **[!UICONTROL Private Key (Base64 encoded)]**: Base64로 인코딩된 개인 키

   * **[!UICONTROL Custom Key identifier]**

   * **[!UICONTROL Key ID]**

   * **[!UICONTROL Client identifier]**: 클라이언트 ID: **[!UICONTROL Update your code]** 카테고리, **[!UICONTROL Client ID]** 필드.

   * **[!UICONTROL CRM version]**: 다음 사이의 CRM 버전 **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** 또는 **[!UICONTROL Dynamics CRM 2016]**.


* **Salesforce.com**

   다음 **[!UICONTROL Salesforce CRM]** 외부 계정을 사용하면 Salesforce 데이터를 Adobe Campaign으로 가져오고 내보낼 수 있습니다.

   Adobe Campaign에서 작동하도록 Salesforce CRM 외부 계정을 구성하려면 다음 세부 정보를 제공해야 합니다.

   * **[!UICONTROL Account]**: Salesforce CRM에 로그인하는 데 사용되는 계정입니다.

   * **[!UICONTROL Password]**: Salesforce CRM에 로그인하는 데 사용되는 암호입니다.

   * **[!UICONTROL Client identifier]**: 에서 클라이언트 식별자를 찾는 방법을 알아봅니다. [이 페이지](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL Security token]**: 에서 보안 토큰을 찾는 방법을 알아봅니다. [이 페이지](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL API version]**: API 버전을 선택합니다. 이 외부 계정의 경우 구성 마법사를 사용하여 Salesforce CRM을 구성해야 합니다.

## 데이터 외부 계정 전송

이러한 외부 계정은 데이터를 **[!UICONTROL Transfer file]** 워크플로우 활동.

![](../assets/do-not-localize/book.png) 워크플로우의 파일 전송에 대해 자세히 알아보십시오 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html){target=&quot;_blank&quot;}

* **FTP 및 SFTP**

   다음 **FTP** 외부 계정을 사용하면 Adobe Campaign 외부의 서버에 대한 액세스를 구성하고 테스트할 수 있습니다. 파일 전송에 사용되는 SFTP 또는 FTP 서버 898과 같은 외부 시스템과의 연결을 설정하기 위해 자체적인 외부 계정을 만들 수 있습니다.
이렇게 하려면 SFTP 또는 FTP 서버에 연결을 설정하는 데 사용되는 주소와 자격 증명을 이 외부 계정에 지정합니다.

* **Amazon Simple Storage Service (S3)**

   다음 **AWS S3** 커넥터를 사용하여 데이터를 Adobe Campaign으로 가져오거나 내보낼 수 있습니다 **[!UICONTROL Transfer file]** 워크플로우 활동. 이 새 외부 계정을 설정할 때 다음 세부 사항을 제공해야 합니다.

   * **[!UICONTROL AWS S3 Account Server]**: 다음과 같이 채워진 서버 URL:   ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL AWS access key ID]**: 에서 AWS 액세스 키 ID를 찾는 방법을 알아봅니다. [Amazon 설명서](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) .

   * **[!UICONTROL Secret access key to AWS]**: 에서 AWS에 대한 비밀 액세스 키를 찾는 방법을 알아봅니다 [Amazon 설명서](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/).

   * **[!UICONTROL AWS Region]**: 의 AWS 지역에 대해 자세히 알아보십시오 [Amazon 설명서](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/).

   * 다음 **[!UICONTROL Use server side encryption]** 확인란을 통해 파일을 S3 암호화 모드로 저장할 수 있습니다. 에서 액세스 키 ID 및 암호 액세스 키를 찾는 방법을 알아봅니다. [Amazon 설명서](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys).

* **Azure Blob 저장소**

   다음 **Azure** 외부 계정은 **[!UICONTROL Transfer file]** 워크플로우 활동. 를 구성하려면 **Azure** Adobe Campaign에서 작업할 외부 계정은 다음 세부 사항을 제공해야 합니다.

   * **[!UICONTROL Server]**: Azure Blob 저장소 서버의 URL입니다.

   * **[!UICONTROL Encryption]**: 암호화 유형 **[!UICONTROL None]** 또는 **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: 를 찾는 방법 알아보기 **[!UICONTROL Access key]** in [Microsoft 설명서](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal).
