---
title: Campaign 및 Microsoft Dynamics 작업
description: Campaign 및 Microsoft Dynamics 작업 방법 알아보기
feature: Microsoft CRM Integration
role: Admin, User
level: Beginner, Intermediate, Experienced
exl-id: 4f9e8f74-27dc-482c-a83c-25623b53560f
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1364'
ht-degree: 3%

---

# Campaign 및 Microsoft Dynamics 365 작업{#crm-ms-dynamics}

크로스 채널 통신에서 CRM 데이터 활성화: 연락처 전달 방법 알아보기 **Microsoft Dynamics 365** Adobe Campaign으로 이동하고 Adobe Campaign에서 Microsoft Dynamics 365로 캠페인 성과 데이터(전송, 열기, 클릭 수 및 반송)를 다시 공유합니다.

구성이 완료되면 전용 워크플로우 활동을 통해 시스템 간의 데이터 동기화가 수행됩니다. [자세히 알아보기](crm-data-sync.md)

>[!NOTE]
>
>지원되는 Microsoft Dynamics 버전은 Campaign에 자세히 설명되어 있습니다 [호환성 매트릭스](../start/compatibility-matrix.md).

Microsoft Dynamics 365 데이터를 Adobe Campaign으로 가져오고 내보내도록 전용 외부 계정을 구성하려면 아래 단계를 따르십시오.

각 시스템에 대해 관리자가 이러한 단계를 수행해야 합니다.

>[!CAUTION]
> 이 설명서의 단계는 권한 및/또는 관리자 액세스 권한을 지정하는 것과 관련된 통합/등록을 만드는 과정을 안내합니다. 이러한 단계는 수행하기 전에 회사 정책을 준수하고 신중하게 수행해야 합니다.

## Microsoft Dynamics 365 구성 {#config-crm-microsoft}

다음을 통해 Microsoft Dynamics 365를 Adobe Campaign과 함께 작업하도록 연결 **웹 API**, 로그온 대상 [Microsoft Azure 디렉터리](https://portal.azure.com) 사용 **전역 관리자** 자격 증명을 실행하고 아래 단계를 수행합니다.

1. Dynamics 365 응용 프로그램(클라이언트) ID를 가져옵니다. [자세히 알아보기](#get-client-id-microsoft)
1. Microsoft Dynamics 인증서 키 식별자 및 키 ID를 생성합니다. [자세히 알아보기](#config-certificate-key-id)
1. 권한을 구성합니다. [자세히 알아보기](#config-permissions-microsoft)
1. 앱 사용자를 만듭니다. [자세히 알아보기](#create-app-user-microsoft)
1. 개인 키를 인코딩합니다. [자세히 알아보기](#configure-acc-for-microsoftt)


### Dynamics 365 클라이언트 ID 가져오기 {#get-client-id-microsoft}

애플리케이션(클라이언트) ID를 가져오려면 Azure Active Directory에 앱을 등록해야 합니다.

1. 다음으로 이동 **Azure Active Directory > 앱 등록**, 및 선택 **새 등록**.
1. 인스턴스를 식별하는 데 도움이 될 수 있는 고유한 이름을 입력합니다. 예: **adobeccampaign`<instance identifier>`**.

저장하면 Microsoft Azure Directory에 고유한 값이 할당됩니다. **애플리케이션(클라이언트) ID** 앱에 연결합니다. 나중에 Adobe Campaign에서 Dynamics 365를 구성할 때 이 ID가 필요합니다.

다음에서 자세히 알아보기 [Microsoft Dynamics 365 설명서](https://docs.microsoft.com/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory){target="_blank"}.

### Microsoft Dynamics 인증서 키 식별자 및 키 ID 생성 {#config-certificate-key-id}

을(를) 가져오려면 **인증서 키 식별자(customKeyIdentifier)** 및 **키 ID (keyId)**, 인증서를 업로드해야 합니다. 인증서는 토큰을 요청할 때 애플리케이션의 ID를 증명하는 비밀로 사용될 수 있습니다. 공개 키라고도 합니다.

아래의 단계를 수행하십시오.

1. 다음으로 이동 **Azure Active Directory > 앱 등록** 앞에서 만든 응용 프로그램을 선택합니다.
1. 선택 **인증서 및 암호**.
1. 다음에서 **인증서** 탭, 클릭 **인증서 업로드**
1. 공개 인증서를 업로드합니다.
1. 다음으로 이동 **매니페스트** 링크: **인증서 키 식별자(customKeyIdentifier)** 및 **키 ID (keyId)**.

다음 **인증서 키 식별자(customKeyIdentifier)** 및 **키 ID (keyId)** 인증서를 사용하여 Microsoft Dynamics 365 CRM 외부 계정을 구성하려면 Campaign에서 이 작업이 필요합니다 **[!UICONTROL CRM O-Auth type]**.

+++ 공개 인증서를 생성하는 방법

인증서를 생성하려면 openssl을 사용합니다.

예제:

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>여기서 일수를 변경할 수 있습니다. `-days 365`: 더 긴 인증서 유효 기간을 위한 코드 샘플입니다.

그런 다음 base64에서 인증서를 인코딩해야 합니다. 이렇게 하려면 Base64 인코더의 도움을 사용하거나 명령줄을 사용합니다 `base64 -w0 private.key` Linux용

+++

### 권한 구성 {#config-permissions-microsoft}

**1단계**: 구성 **필수 권한** (생성된 앱).

1. 다음으로 이동 **Azure Active Directory > 앱 등록** 앞에서 만든 응용 프로그램을 선택합니다.
1. 클릭 **설정** 왼쪽 위에 있습니다.
1. 날짜 **필수 권한**, 클릭 **추가** 및 **API > Dynamics CRM Online 선택**.
1. 클릭 **선택**, 활성화 **Dynamics 365를 조직 사용자로 액세스** 확인란 및 클릭 **선택**.
1. 그런 다음 앱에서 **매니페스트** 다음 아래에 **관리** 메뉴 아래의 제품에서 사용할 수 있습니다.
1. 다음에서 **매니페스트** 편집기, 설정 `allowPublicClient` 다음에서 속성 `null` 끝 `true` 및 클릭 **저장**.

**2단계**: 관리자 동의 부여

1. 다음으로 이동 **Azure Active Directory > 엔터프라이즈 애플리케이션**.
1. 테넌트 전체 관리자 동의를 부여할 애플리케이션을 선택합니다.
1. 왼쪽 창 메뉴에서 다음을 선택합니다. **권한** 아래에 **보안**.
1. 클릭 **관리자 동의 부여**.

자세한 내용은 다음을 참조하십시오. [Azure 설명서](https://docs.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent#grant-admin-consent-from-the-azure-portal).

### 앱 사용자 만들기 {#create-app-user-microsoft}

>[!NOTE]
>
> 이 단계는 와 함께 선택 사항입니다. **[!UICONTROL Password credentials]** 인증.

앱 사용자는 위에 등록된 애플리케이션이 사용할 사용자입니다. 위에 등록된 앱을 사용하여 Microsoft Dynamics에 대한 모든 변경 작업은 이 사용자를 통해 수행됩니다.

**1단계**: azure active directory에서 비대화형 사용자 만들기

1. 클릭 **Azure Active Directory > 사용자** 및 클릭 **새 사용자**.
1. 사용할 올바른 이름을 지정하십시오. 사용자 이름은 이메일 형식이어야 합니다.
1. 선택 **Dynamics 365 관리자** 다음에서 **디렉터리 역할**.

**2단계**: 생성된 사용자에게 적절한 라이선스 할당

1. 출처: [Microsoft Azure](https://portal.azure.com), 클릭 **관리 앱**.
1. 다음으로 이동 **사용자 > 활성 사용자** 을(를) 클릭하고 새로 생성된 사용자를 클릭합니다.
1. 클릭 **제품 라이선스 편집** 및 선택 **Dynamics 365 고객 참여 계획**.
1. Click **Close**.

**3단계**: Dynamics CRM에서 애플리케이션 사용자 만들기

1. 출처: [Microsoft Azure](https://portal.azure.com), 다음으로 이동 **설정 > 보안 > 사용자**.
1. 드롭다운을 클릭하고 을 선택합니다. **애플리케이션 사용자**, 및 클릭 **신규**.
1. 위의 active directory에서 만든 사용자와 동일한 사용자 이름을 사용합니다.
1. 할당 **애플리케이션 ID** 대상 [이전에 만든 응용 프로그램](#get-client-id-microsoft).
1. 클릭 **역할 관리** 및 선택 **시스템 관리자** 역할을 사용자에게 부여합니다.

## Campaign 구성 {#configure-acc-for-microsoft}

### 연결 만들기{#new-ms-dyn-external-account}

먼저 Microsoft Dynamics 365 외부 계정을 만들어야 합니다.

1. 찾아보기 **[!UICONTROL Administration > Platform > External accounts]** campaign 탐색기의 노드이며 외부 계정을 만듭니다.
1. 선택 **[!UICONTROL Microsoft Dynamics CRM]** 의 외부 계정 **유형** 섹션.
1. 에서 인증 방법 선택 **[!UICONTROL CRM O-Auth type]** 드롭다운 목록입니다.

   ![](assets/ms-dyn-external-account.png)

   1. Adobe Campaign과 연결하도록 Microsoft Dynamics CRM 외부 계정을 구성하려면 **암호 자격 증명**, 다음 세부 정보를 제공합니다.

      * **서버**: Microsoft CRM 서버의 URL Microsoft CRM Server URL을 찾으려면 Microsoft Dynamics CRM 계정에 액세스한 다음 Dynamics 365를 클릭하고 앱을 선택하십시오. 그런 다음 브라우저의 주소 표시줄에서 서버 URL을 찾을 수 있습니다(예: https://myserver.crm.dynamics.com/).
      * **계정**: Microsoft CRM에 로그인하는 데 사용되는 계정입니다.
      * **암호**: Microsoft CRM에 로그인하는 데 사용되는 계정입니다.
      * **클라이언트 식별자**: 코드 범주 업데이트, 클라이언트 ID 필드의 Microsoft Azure 관리 포털에서 찾을 수 있는 애플리케이션(클라이언트) ID.
      * **CRM 버전**: Dynamics CRM 365 CRM 버전을 선택합니다.
   1. Adobe Campaign과 연결하도록 Microsoft Dynamics CRM 외부 계정을 구성하려면 다음을 수행하십시오. **인증서**, 다음 세부 정보를 제공합니다.

      * **서버**: Microsoft CRM 서버의 URL Microsoft CRM Server URL을 찾으려면 Microsoft Dynamics CRM 계정에 액세스한 다음 Dynamics 365를 클릭하고 앱을 선택하십시오. 그런 다음 브라우저의 주소 표시줄에서 서버 URL을 찾을 수 있습니다(예: https://myserver.crm.dynamics.com/).
      * **개인 키**: 다음에 설명된 대로 base64로 인코딩된 개인 키를 복사/붙여넣습니다. [이 섹션](#config-certificate-key-id).
      * **키 ID**: 다음에서 사용할 수 있는 키 **매니페스트** 에 설명된 대로 애플리케이션 탭 [이 섹션](#config-certificate-key-id).
      * **사용자 지정 키 식별자**: 다음에서 사용할 수 있는 식별자 **매니페스트** 에 설명된 대로 애플리케이션 탭 [이 섹션](#config-certificate-key-id).
      * **클라이언트 식별자**: 다음에 설명된 대로 Microsoft Azure 관리 포털에서 찾을 수 있는 애플리케이션(클라이언트) ID [이 섹션](#get-client-id-microsoft).
      * **CRM 버전**: Dynamics CRM 365 CRM 버전을 선택합니다.


1. 다음 항목 선택 **사용** Campaign에서 계정을 활성화하는 옵션입니다.

>[!NOTE]
>
>설정을 승인하려면 로그오프한 후 Adobe Campaign 콘솔로 다시 로그온합니다.

### 동기화할 테이블 선택{#ms-dyn-create-tables}

이제 동기화할 테이블을 구성할 수 있습니다.

1. 다음을 클릭합니다. **[!UICONTROL Microsoft CRM configuration wizard...]**.
1. 동기화할 테이블을 선택하고 프로세스를 시작합니다.
1. 에서 Adobe Campaign에 생성된 스키마를 확인합니다. **[!UICONTROL Administration > Configuration > Data schemas]** 노드.

>[!NOTE]
>
>허용 목록에 추가하다에 서버 URL과 를 추가해야 합니다. `login.microsoftonline.com`. 이렇게 하려면 Adobe 담당자에게 문의하십시오.

## 열거형 동기화{#sfdc-enum-sync}

스키마가 만들어지면 Dynamics 365에서 Adobe Campaign으로 열거형을 자동으로 동기화할 수 있습니다.

1. 에서 도우미를 엽니다.  **[!UICONTROL Synchronizing enumerations...]** 링크를 클릭합니다.
1. Dynamics 365 열거와 일치하는 Adobe Campaign 열거를 선택합니다.
Adobe Campaign 열거형의 모든 값을 CRM의 값으로 바꿀 수 있습니다. 이렇게 하려면 다음을 선택하십시오. **[!UICONTROL Yes]** 다음에서 **[!UICONTROL Replace]** 열.
1. 클릭 **[!UICONTROL Next]** 그런 다음 **[!UICONTROL Start]** 열거형 가져오기를 시작합니다.
1. 찾아보기 **[!UICONTROL Administration > Platform > Enumerations]** 가져온 값을 확인할 노드입니다.

이제 Adobe Campaign 및 Microsoft Dynamics 365가 연결되었습니다. 두 시스템 간에 데이터 동기화를 설정할 수 있습니다.

Adobe Campaign 데이터와 Microsoft CRM 간의 데이터를 동기화하려면 워크플로우를 만들고 다음을 사용합니다. **[!UICONTROL CRM connector]** 활동.

데이터 동기화에 대해 자세히 알아보기 [이 페이지에서](crm-data-sync.md).

### 지원되는 필드 데이터 유형 {#ms-dyn-supported-types}

Microsoft Dynamics 365의 경우 지원되는/지원되지 않는 특성 유형은 다음과 같습니다.


| 속성 유형 | 지원됨 |
| --------------------------------------------------------------------------------- | --------- |
| 기본 유형 : 부울, 날짜/시간, 십진수, 부동 소수점, 더블, 정수, bigint , 문자열 | 예 |
| 금액(두 배로 표시) | 예 |
| memo, entityname , primarykey, uniqueidentifier(문자열로 표시) | 예 |
| 상태, 선택 목록(가능한 값은 열거형으로 저장됨), 상태(문자열) | 예 |
| 소유자(문자열로) | 예 |
| 조회(단일 엔티티 참조 조회만) | 예 |
| 고객 | 아니요 |
| 관련 항목 | 아니요 |
| PartyList | 아니요 |
| ManagedProperty | 아니요 |
