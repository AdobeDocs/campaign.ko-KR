---
title: Campaign의 개인 정보 보호 요청 관리
description: Campaign의 개인 정보 보호 요청을 관리하는 방법 알아보기
feature: Privacy
role: Admin
level: Beginner
exl-id: 0f81d318-dbfd-45c8-b391-b1d14d23e9c8
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 96%

---

# Campaign의 개인 정보 보호 요청 관리 {#privacy}

비즈니스의 성격과 운영되는 관할 구역에 따라 데이터 운영에 법적 개인 정보 보호 규정이 적용될 수 있습니다. 이러한 규정에서는 고객에게 수집된 데이터에 대한 액세스를 요청할 수 있는 권한과 저장된 데이터의 삭제를 요청할 수 있는 권한을 부여하는 경우가 많습니다. 설명서 전체에서 개인 데이터에 대한 이러한 고객 요청을 &quot;개인 정보 보호 요청&quot;이라고 합니다.

 Campaign은 저장된 데이터에 대한 개인 정보 보호 요청을 만들고 처리할 수 있는 도구를 데이터 컨트롤러에 제공합니다. 따라서 요청을 하는 데이터 주체의 ID를 확인하고 요청자에게 반환되는 데이터가 데이터 주체의 정보임을 확인하는 것은 데이터 컨트롤러로서의 책임입니다. [Adobe Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=ko){target="_blank"}의 개인 데이터와 데이터를 관리하는 다양한 엔터티에 대해 자세히 알아봅니다.


Campaign에서 개인 정보 요청을 관리하려면 먼저 [네임스페이스를 정의](#namespaces)해야 합니다. 그러면 개인 정보 요청을 만들고 관리할 수 있습니다. 개인 정보 요청을 수행하려면 **Adobe Privacy Service** 통합을 사용하십시오.  Privacy Service에서 모든 Adobe Experience Cloud 솔루션으로 푸시된 개인 정보 보호 요청은 전용 워크플로우를 통해 Campaign에서 자동으로 처리됩니다. [자세히 알아보기](#create-privacy-request)

에 대해 알아보기 **액세스 권한** 및 **잊혀질 권리** (삭제 요청) 위치 [Adobe Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=ko){target="_blank"}.

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

## 네임스페이스 정의 {#namespaces}

개인 정보 보호 요청을 만들기 전에 사용할 **네임스페이스를 정의**&#x200B;해야 합니다. 네임스페이스는 데이터베이스에서 데이터 주체를 식별하는 데 사용되는 키입니다.

>[!NOTE]
>
>[Adobe Experience Platform 설명서](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=ko){target="_blank"}에서 신원 네임스페이스에 대해 자세히 알아봅니다.

현재 Adobe Campaign에서는 Experience Platform ID 네임스페이스 서비스에서 네임스페이스 가져오기를 지원하지 않습니다. 따라서 ID 네임스페이스 서비스에서 네임스페이스를 만들면 Adobe Campaign 인터페이스에서 해당 네임스페이스를 수동으로 만들어야 합니다. 이렇게 하려면 아래 단계를 수행합니다.

<!--v7?
Three namespaces are available out-of-the-box: email, phone and mobile phone. If you need a different namespace (a recipient custom field, for example), you can create a new one from **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]**.

>[!NOTE]
>
>For optimal performance, it is recommended to use out-of-the-box namespaces.
-->

1. [신원 네임스페이스 서비스](https://developer.adobe.com/experience-platform-apis/references/identity-service/#tag/Identity-Namespace?lang=ko){target="_blank"}에서 네임스페이스를 만듭니다.

1. 조직에서 사용할 수 있는 [신원 네임스페이스 목록](https://developer.adobe.com/experience-platform-apis/references/identity-service/#operation/getIdNamespaces){target="_blank"}을 만들면 네임스페이스에 다음과 같은 세부 정보가 표시됩니다.

   ```
   {
           "updateTime": 1632903236731,
           "code": "lumanamespace",
           "status": "ACTIVE",
           "description": "new namespace for Luma privacy requests",
           "id": 10998717,
           "createTime": 1632903236731,
           "idType": "Email",
           "namespaceType": "Custom",
           "name": "Luma Namespace",
           "custom": true
   }
   ```

1. Adobe Campaign에서 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]**(으)로 이동한 다음 **[!UICONTROL New]**&#x200B;을(를) 선택합니다.

   ![](assets/privacy-namespaces-new.png)

1. **[!UICONTROL Label]**&#x200B;을(를) 입력합니다.

1. ID 네임스페이스 서비스에서 만든 네임스페이스와 일치하도록 새 네임스페이스 세부 사항을 입력합니다.

   * **[!UICONTROL AEC Namespace ID]**&#x200B;은(는) &quot;id&quot; 속성과 일치해야 합니다.
   * **[!UICONTROL Internal name]**&#x200B;은(는) &quot;code&quot; 속성과 일치해야 합니다.
   * **[!UICONTROL Reconciliation key]**&#x200B;은(는) &quot;idType&quot; 속성과 일치해야 합니다

   ![](assets/privacy-namespaces-details.png)

   **[!UICONTROL Reconciliation key]** 필드는 Adobe Campaign 데이터베이스의 데이터 주체를 식별하는 데 사용됩니다.

1. 대상 매핑 <!--(**[!UICONTROL Recipients]**, **[!UICONTROL Real time event]** or **[!UICONTROL Subscriptions]**)-->을(를) 선택하여 Adobe Campaign에서 네임스페이스가 조정되는 방법을 지정합니다.

   >[!NOTE]
   >
   >여러 대상 매핑을 사용하려면 대상 매핑당 네임스페이스를 하나씩 만듭니다.

1. 변경 내용을 저장합니다.

이제 새 네임스페이스에 따라 개인 정보 보호 요청을 만들 수 있습니다. 여러 네임스페이스를 사용하는 경우 동일한 조정 값에 대해 네임스페이스당 하나의 개인 정보 보호 요청을 만듭니다.

## 개인 정보 보호 요청 생성 {#create-privacy-request}

**[!DNL Adobe Experience Platform Privacy Service]** 통합을 사용하면 단일 JSON API 호출을 통해 다중 솔루션 컨텍스트에서 개인 정보 보호 요청을 자동화할 수 있습니다. Adobe Campaign은 전용 워크플로우를 통해 Privacy Service에서 푸시된 요청을 자동으로 처리합니다.

개인 정보 보호 핵심 서비스에서 개인 정보 보호 요청을 만드는 방법에 대해 알아보려면 [Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ko) 설명서를 참조하십시오.{target="_blank"}

각 **[!DNL Privacy Service]** 작업은 사용 중인 네임스페이스의 수를 기준으로 Adobe Campaign에서 여러 개인 정보 보호 요청으로 분할되며, 하나의 요청은 하나의 네임스페이스에 해당합니다.

또한 하나의 작업은 여러 인스턴스에 대해 실행할 수 있습니다. 따라서 하나의 작업에 대해 여러 파일이 만들어집니다. 예를 들어, 요청에 두 개의 네임스페이스가 있고 세 개의 인스턴스에서 실행 중인 경우 총 6개의 파일이 전송됩니다. 네임스페이스 및 인스턴스당 하나의 파일입니다.

파일 이름의 패턴은 `<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml` 입니다.

* **InstanceName**: 캠페인 인스턴스 이름
* **NamespaceId**: 사용된 네임스페이스의 ID 서비스 네임스페이스 ID
* **조정 키**: 인코딩 조정 키

>[!CAUTION]
>
>사용자 정의 네임스페이스 유형을 사용하여 요청을 제출하려면 [JSON 메서드](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=ko#json){target="_blank"} and add the namespaceId to the request, or use the [API call](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/privacy-jobs.html?lang=ko#access-delete){target="_blank"}를 활용하여 요청을 만듭니다.
>
>표준 네임스페이스 유형을 사용하여 요청을 제출할 때는 [개인 정보 사용자 인터페이스](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=ko#request-builder){target="_blank"}만 사용할 수 있습니다.

### 요청을 처리할 때 검색된 테이블 {#list-of-tables}

Adobe Campaign은 Delete 또는 Access 개인 정보 보호 요청을 수행할 때 수신자 테이블(고유 유형)에 대한 링크가 있는 모든 테이블의 **[!UICONTROL Reconciliation value]**&#x200B;을(를) 기준으로 모든 데이터 주체의 데이터를 검색합니다.

개인 정보 요청을 수행할 때 고려할 기본 제공 테이블 목록은 다음과 같습니다.

* 수신자(recipient)
* 수신자 게재 로그(broadLogRcp)
* 수신자 추적 로그(trackingLogRcp)
* 보관된 이벤트 게재 로그(broadLogEventHisto)
* 수신자 목록 콘텐츠(rcpGrpRel)
* 방문자 오퍼 제안(propositionVisitor)
* 방문자(visitor)
* 구독 내역(subHisto)
* 구독(subscription)
* 수신자 오퍼 제안(propositionRcp)

수신자 테이블(고유 유형)에 대한 링크가 있는 사용자 지정 테이블를 만든 경우, 해당 테이블도 고려됩니다. 예를 들어 수신자 테이블과 연결된 트랜잭션 테이블과 트랜잭션 테이블과 연결된 트랜잭션 세부 정보가 있는 경우, 이 두 가지 모두 고려됩니다.
<!--
>[!CAUTION]
>
>If you perform Privacy batch requests using profile deletion workflows, please take into consideration the following remarks:
>* Profile deletion via workflows do not process children tables.
>* You need to handle the deletion for all the children tables.
>* Adobe recommends that you create an ETL workflow that add the lines to delete in the Privacy Access table and let the **[!UICONTROL Delete privacy requests data]** workflow perform the deletion. We suggest to limit to 200 profiles per day to delete for performance reasons.-->

### 개인 정보 보호 요청 상태 {#privacy-request-statuses}

Adobe Campaign의 개인 정보 보호 요청에 대한 다양한 상태와 이를 해석하는 방법을 아래에서 확인할 수 있습니다.

* **[!UICONTROL New]** / **[!UICONTROL Retry pending]**: 진행 중이며 워크플로우는 아직 요청을 처리하지 않았습니다.
* **[!UICONTROL Processing]** / **[!UICONTROL Retry in progress]**: 워크플로우가 요청을 처리하고 있습니다.
* **[!UICONTROL Delete pending]**: 워크플로우는 삭제하려는 모든 수신자 데이터를 식별했습니다.
* **[!UICONTROL Delete in progress]**: 워크플로우가 삭제를 처리하고 있습니다.
* **[!UICONTROL Complete]**: 요청 처리가 오류 없이 끝났습니다.
* **[!UICONTROL Error]**: 워크플로우에서 오류가 발생했습니다. 이유는 **[!UICONTROL Request status]** 열의 개인 정보 보호 요청 목록에 표시됩니다. 예를 들어 **[!UICONTROL Error data not found]**&#x200B;은(는) 데이터 주체의 **[!UICONTROL Reconciliation value]**&#x200B;와(과) 일치하는 수신자 데이터가 데이터베이스에 없음을 의미합니다.

**Campaign Classic v7 설명서의 관련 항목:**

* [개인 정보 보호 및 동의](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=ko){target="_blank"}

* [개인 정보 관리 시작하기](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=ko){target="_blank"}

* [개인 정보 관리에 관한 규정](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=ko){target="_blank"}(GDPR, CPA, PDPA, LGPD)

* [개인 정보 판매 옵트아웃](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-requests/privacy-requests-ccpa.html?lang=ko){target="_blank"}(CCPA에만 해당)
