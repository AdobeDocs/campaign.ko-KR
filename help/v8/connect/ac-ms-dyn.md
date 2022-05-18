---
title: Campaign 및 Microsoft Dynamics 작업
description: Campaign 및 Microsoft Dynamics 작업 방법 알아보기
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 4f9e8f74-27dc-482c-a83c-25623b53560f
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 3%

---

# Campaign을 Dynamics 365와 함께 사용하기{#crm-ms-dynamics}

채널 간 통신에서 CRM 데이터 활성화: 연락처 전달 방법 알아보기 **Microsoft Dynamics 365** Adobe Campaign에 연결하고 캠페인 성능 데이터(전송, 열기, 클릭 및 바운스)를 Adobe Campaign에서 Microsoft Dynamics 365로 다시 공유합니다.

구성이 완료되면 전용 워크플로우 활동을 통해 시스템 간 데이터 동기화가 수행됩니다. [자세히 알아보기](crm-data-sync.md)

>[!NOTE]
>
>지원되는 Microsoft Dynamics 버전은 Campaign에 자세히 설명되어 있습니다 [호환성 매트릭스](../start/compatibility-matrix.md).

아래 절차에 따라 Microsoft Dynamics 365 데이터를 Adobe Campaign으로 가져오고 내보낼 전용 외부 계정을 구성하십시오.

각 시스템의 경우 관리자가 이러한 단계를 수행해야 합니다.

>[!CAUTION]
> 이 설명서의 단계에서는 권한 및/또는 관리자 액세스 권한을 지정하는 통합/등록을 만드는 과정을 안내합니다. 이러한 단계가 수행 전에 회사 정책을 준수하고 신중하게 수행하는 것은 귀하의 책임입니다.

## Microsoft Dynamics 365 구성 {#config-crm-microsoft}

를 통해 Adobe Campaign에서 작업할 수 있도록 Microsoft Dynamics 365를 연결하려면 **웹 API**, 로그온 [Microsoft Azure 디렉토리](https://portal.azure.com) 사용 **글로벌 관리자** 자격 증명을 실행하고 아래 단계를 수행합니다.

1. Dynamics 365 응용 프로그램(클라이언트) ID를 가져옵니다. [자세히 알아보기](#get-client-id-microsoft)
1. Microsoft Dynamics 인증서 키 식별자 및 키 ID를 생성합니다. [자세히 알아보기](#config-certificate-key-id)
1. 권한을 구성합니다. [자세히 알아보기](#config-permissions-microsoft)
1. 앱 사용자를 만듭니다. [자세히 알아보기](#create-app-user-microsoft)
1. 개인 키를 인코딩합니다. [자세히 알아보기](#configure-acc-for-microsoftt)


### Dynamics 365 클라이언트 ID 가져오기 {#get-client-id-microsoft}

응용 프로그램(클라이언트) ID를 가져오려면 Azure Active Directory에서 앱을 등록해야 합니다.

1. 찾아보기 **Azure Active Directory > 앱 등록**, 을(를) 선택하고 을(를) 선택합니다. **새 등록**.
1. 다음과 같이 인스턴스를 식별하는 데 도움이 되는 고유한 이름을 입력합니다 **adobecampaign`<instance identifier>`**.

저장하면 Microsoft Azure Directory에 고유한 가 할당됩니다 **애플리케이션(클라이언트) ID** 참조하십시오. 이 ID는 나중에 Adobe Campaign에서 Dynamics 365 구성에서 필요합니다.

추가 정보 [Microsoft Dynamics 365 설명서](https://docs.microsoft.com/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory){target=&quot;_blank&quot;}.

### Microsoft Dynamics 인증서 키 식별자 및 키 ID 생성 {#config-certificate-key-id}

를 가져오려면 **인증서 키 식별자(customKeyIdentifier)** 그리고 **키 ID(keyId)**, 인증서를 업로드해야 합니다. 토큰을 요청할 때 인증서를 기밀로 사용하여 응용 프로그램의 ID를 증명할 수 있습니다. 공개 키라고도 할 수 있습니다.

아래의 단계를 수행하십시오.

1. 찾아보기 **Azure Active Directory > 앱 등록** 그리고 이전에 생성된 응용 프로그램을 선택합니다.
1. 선택 **인증서 및 암호**.
1. 에서 **인증서** 탭에서 **인증서 업로드**
1. 공개 인증서를 업로드합니다.
1. 다음 위치로 이동합니다. **매니페스트** 링크를 클릭하여 **인증서 키 식별자(customKeyIdentifier)** 그리고 **키 ID(keyId)**.

다음 **인증서 키 식별자(customKeyIdentifier)** 그리고 **키 ID(keyId)** 인증서를 사용하여 Microsoft Dynamics 365 CRM 외부 계정을 구성하려면 Campaign에 이 필요합니다 **[!UICONTROL CRM O-Auth type]**.

+++ 공개 인증서를 생성하는 방법

인증서를 생성하기 위해 openssl을 사용할 수 있습니다.

예제:

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>여기에서 일 수를 변경할 수 있습니다 `-days 365`를 채울 수 있습니다.

그런 다음 base64에서 인증서를 인코딩해야 합니다. 이렇게 하려면 Base64 인코더의 도움을 받거나 명령줄을 사용할 수 있습니다 `base64 -w0 private.key` Linux용

+++

### 권한 구성 {#config-permissions-microsoft}

**1단계**: 구성 **필수 권한** 생성된 앱의 경우

1. 다음으로 이동 **Azure Active Directory > 앱 등록** 그리고 이전에 생성된 응용 프로그램을 선택합니다.
1. 클릭 **설정** 왼쪽 위에 있습니다.
1. 설정 **필수 권한**&#x200B;를 클릭합니다. **추가** 및 **API > Dynamics CRM Online 을 선택합니다.**.
1. 클릭 **선택**, 활성화 **조직 사용자로 Dynamics 365에 액세스** 확인란을 선택하고 **선택**.
1. 그런 다음 앱에서 를 선택합니다 **매니페스트** 아래에 **관리** 메뉴 아래의 제품에서 사용할 수 있습니다.
1. 에서 **매니페스트** 편집기, 설정 `allowPublicClient` 속성 `null` to `true` 을(를) 클릭합니다. **저장**.

**2단계**: 관리자 동의 부여

1. 다음으로 이동 **Azure Active Directory > 엔터프라이즈 응용 프로그램**.
1. 임차인 전체 관리자 동의를 부여할 애플리케이션을 선택합니다.
1. 왼쪽 창 메뉴에서 **권한** 아래에 **보안**.
1. 클릭 **관리자 동의 부여**.

자세한 내용은 [Azure 설명서](https://docs.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent#grant-admin-consent-from-the-azure-portal).

### 앱 사용자 만들기 {#create-app-user-microsoft}

>[!NOTE]
>
> 이 단계는 **[!UICONTROL Password credentials]** 인증.

앱 사용자는 위에 등록된 애플리케이션이 사용할 사용자입니다. 위에 등록된 앱을 사용하여 Microsoft Dynamics에 변경한 내용은 이 사용자를 통해 수행됩니다.

**1단계**: Azure active directory에서 비대화형 사용자 만들기

1. 클릭 **Azure Active Directory > 사용자** 을(를) 클릭합니다. **새 사용자**.
1. 사용할 이름을 지정하고 사용자 이름은 이메일 형식이어야 합니다.
1. 선택 **Dynamics 365 관리자** 에서 **디렉터리 역할**.

**2단계**: 생성된 사용자에게 적절한 라이센스 할당

1. From [Microsoft Azure](https://portal.azure.com)를 클릭하고 **관리 앱**.
1. 이동 **사용자 > 활성 사용자** 새로 만든 사용자를 클릭합니다.
1. 클릭 **제품 라이선스 편집** 을(를) 선택하고 을(를) 선택합니다. **Dynamics 365 고객 참여 계획**.
1. Click **Close**.

**3단계**: Dynamics CRM에서 응용 프로그램 사용자 만들기

1. From [Microsoft Azure](https://portal.azure.com), 다음 위치로 이동합니다. **설정 > 보안 > 사용자**.
1. 드롭다운을 클릭하고 을 선택합니다. **애플리케이션 사용자**&#x200B;를 클릭하고 **새로 만들기**.
1. 위의 active directory에서 만든 사용자와 동일한 사용자 이름을 사용하십시오.
1. 을(를) 지정합니다. **애플리케이션 ID** 대상 [이전에 만든 애플리케이션](#get-client-id-microsoft).
1. 클릭 **역할 관리** 그리고 **시스템 관리자** 사용자에게 역할.

## Campaign 구성 {#configure-acc-for-microsoft}

### 연결 만들기{#new-ms-dyn-external-account}

먼저 Microsoft Dynamics 365 외부 계정을 만들어야 합니다.

1. 찾아보기 **[!UICONTROL Administration > Platform > External accounts]** 노드 아래에 배치하여 외부 계정을 만듭니다.
1. 선택 **[!UICONTROL Microsoft Dynamics CRM]** 의 외부 계정 **유형** 섹션을 참조하십시오.
1. 에서 인증 방법을 선택합니다 **[!UICONTROL CRM O-Auth type]** 드롭다운 목록.

   ![](assets/ms-dyn-external-account.png)

   1. Adobe Campaign과 연결하도록 Microsoft Dynamics CRM 외부 계정을 구성하려면 **암호 자격 증명**&#x200B;에서 다음 세부 정보를 제공합니다.

      * **서버**: Microsoft CRM 서버의 URL. Microsoft CRM 서버 URL을 찾으려면 Microsoft Dynamics CRM 계정에 액세스한 다음 Dynamics 365를 클릭하고 앱을 선택합니다. 그런 다음 브라우저의 주소 표시줄에 서버 URL(예: https://myserver.crm.dynamics.com/)을 찾을 수 있습니다.
      * **계정**: Microsoft CRM에 로그인하는 데 사용되는 계정입니다.
      * **암호**: Microsoft CRM에 로그인하는 데 사용되는 계정입니다.
      * **클라이언트 식별자**: 코드 범주 업데이트, 클라이언트 ID 필드의 Microsoft Azure 관리 포털에서 찾을 수 있는 애플리케이션(클라이언트) ID입니다.
      * **CRM 버전**: Dynamics CRM 365 CRM 버전을 선택합니다.
   1. Adobe Campaign과 연결하도록 Microsoft Dynamics CRM 외부 계정을 구성하려면 **인증서**&#x200B;에서 다음 세부 정보를 제공합니다.

      * **서버**: Microsoft CRM 서버의 URL. Microsoft CRM 서버 URL을 찾으려면 Microsoft Dynamics CRM 계정에 액세스한 다음 Dynamics 365를 클릭하고 앱을 선택합니다. 그런 다음 브라우저의 주소 표시줄에 서버 URL(예: https://myserver.crm.dynamics.com/)을 찾을 수 있습니다.
      * **개인 키**: 에 설명된 대로 인코딩된 base64의 개인 키 복사/붙여넣기 [이 섹션](#config-certificate-key-id).
      * **키 ID**: 에서 사용할 수 있는 키 **매니페스트** 에 설명된 대로 애플리케이션의 탭입니다. [이 섹션](#config-certificate-key-id).
      * **사용자 지정 키 식별자**: 에서 사용할 수 있는 식별자 **매니페스트** 에 설명된 대로 애플리케이션의 탭입니다. [이 섹션](#config-certificate-key-id).
      * **클라이언트 식별자**: 에 설명된 대로 Microsoft Azure 관리 포털에서 찾을 수 있는 애플리케이션(클라이언트) ID [이 섹션](#get-client-id-microsoft).
      * **CRM 버전**: Dynamics CRM 365 CRM 버전을 선택합니다.


1. 을(를) 선택합니다 **활성화** campaign에서 계정을 활성화하는 옵션.

>[!NOTE]
>
>설정을 승인하려면 로그오프했다가 Adobe Campaign 콘솔에 다시 로그온합니다.

### 동기화할 테이블 선택{#ms-dyn-create-tables}

이제 동기화할 테이블을 구성할 수 있습니다.

1. 을(를) 클릭합니다. **[!UICONTROL Microsoft CRM configuration wizard...]**.
1. 동기화할 테이블을 선택하고 프로세스를 시작합니다.
1. Adobe Campaign에서 생성된 스키마를 **[!UICONTROL Administration > Configuration > Data schemas]** 노드 아래에 있어야 합니다.

>[!NOTE]
>
>다음 두 URL을 허용 목록에 추가하다에 추가해야 합니다. 서버 URL 및 `login.microsoftonline.com`. 이렇게 하려면 Adobe 담당자에게 문의하십시오.

## 열거형 동기화{#sfdc-enum-sync}

스키마가 만들어지면 Dynamics 365에서 Adobe Campaign으로 열거형을 자동으로 동기화할 수 있습니다.

1. 에서 도우미를 엽니다.  **[!UICONTROL Synchronizing enumerations...]** 링크를 클릭합니다.
1. Dynamics 365 열거와 일치하는 Adobe Campaign 열거형을 선택합니다.
Adobe Campaign 열거형의 모든 값을 CRM의 값으로 바꿀 수 있습니다. 이렇게 하려면 을(를) 선택합니다. **[!UICONTROL Yes]** 에서 **[!UICONTROL Replace]** 열.
1. 클릭 **[!UICONTROL Next]** 그리고 **[!UICONTROL Start]** 열거형 가져오기를 시작하려면
1. 찾아보기 **[!UICONTROL Administration > Platform > Enumerations]** 노드 를 사용하여 가져온 값을 확인합니다.

이제 Adobe Campaign 및 Microsoft Dynamics 365가 연결됩니다. 두 시스템 간에 데이터 동기화를 설정할 수 있습니다.

Adobe Campaign 데이터와 Microsoft CRM 간에 데이터를 동기화하려면 워크플로우를 만들고 **[!UICONTROL CRM connector]** 활동.

데이터 동기화에 대해 자세히 알아보기 [이 페이지에서](crm-data-sync.md).

### 지원되는 필드 데이터 유형 {#ms-dyn-supported-types}

Microsoft Dynamics 365의 경우 지원/지원되지 않는 속성 유형이 아래에 나와 있습니다.


| 속성 유형 | 지원됨 |
| --------------------------------------------------------------------------------- | --------- |
| 기본 유형 : 부울, datetime, decimal, float, double, 정수, bigint, 문자열 | 예 |
| 금액(이중) | 예 |
| 메모, entityname , primarykey, uniqueidentifier (as string) | 예 |
| 상태, picklist(가능한 값을 열거형에 저장함), 상태(문자열) | 예 |
| 소유자(문자열로) | 예 |
| 조회(단일 엔티티 참조 조회만) | 예 |
| 고객 | 아니요 |
| 관련 | 아니요 |
| PartyList | 아니요 |
| ManagedProperty | 아니요 |
