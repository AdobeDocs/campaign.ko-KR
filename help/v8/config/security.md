---
title: Campaign 보안 모범 사례
description: Campaign 보안 모범 사례 시작
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
version: Campaign v8, Campaign Classic v7
source-git-commit: da2274cfd19bb067fcc1e990360093f161d5638a
workflow-type: tm+mt
source-wordcount: '2810'
ht-degree: 52%

---

# Campaign 보안 모범 사례 {#ac-security}

Adobe에서는 디지털 경험에 대한 보안을 매우 중요하게 생각합니다. 보안 관행은 내부 소프트웨어 개발 및 운영 프로세스 및 도구에 깊이 배어있으며, 여러 분야의 다양한 팀이 협력하여 사건을 신속하게 예방, 감지 및 대응합니다.

또한 파트너, 주요 연구원, 보안 연구 기관 및 기타 산업 조직과의 공동 작업을 통해 최신 위협 및 취약점을 최신 상태로 유지할 수 있으며, 고급 보안 기술을 제공하는 제품 및 서비스에 정기적으로 통합합니다.

>[!NOTE]
>
>**Campaign v8 관리 클라우드 서비스:** 인프라(네트워크, 서버, TLS, 패치 작업)는 Adobe에서 관리합니다. 이 페이지에서는 사용자가 제어하는 테넌트 및 애플리케이션 수준 구성(액세스 관리, 인증, 인스턴스 설정, 데이터 보호, 코딩 및 운영 사례)에 중점을 둡니다.

## 보안 검사 목록 {#security-checklist}

이 체크리스트를 사용하여 구성을 권장 보안 기본값으로 맞춥니다.

* [액세스 관리](#access-management): 보안 그룹 만들기, 적절한 권한 할당, 관리자 사용 제한, 사용자당 운영자 한 명, 정기적으로 검토
* [인증 및 세션](#authentication-and-session): Adobe IMS, 강력한 ID 정책, 세션 시간 제한 사용
* [인스턴스 및 네트워크 보안](#instance-and-network-security): Campaign 컨트롤 패널을 통한 IP 허용 목록, URL 권한, GPG 키
* [데이터 및 PII 보호](#data-and-pii-protection): HTTPS, PII 보기 제한, 암호 제한, 중요 페이지 보호
* [코딩 지침](#coding-guidelines): 하드 코딩된 암호가 없습니다. 입력, 매개 변수가 있는 SQL, captchas의 유효성을 검사합니다.
* [데이터 제한](#data-restriction): 외부 계정의 암호 및 암호 필드에 대한 액세스를 제한합니다.
* [운영 및 규정 준수](#operational-and-compliance): 이 기준선과 정기적으로 비교하려면 감사 추적을 사용하십시오

## 개인 정보

개인 정보를 올바로 처리하고 개인 데이터를 관리하기 위해 운영하는 지역에 적용되는 법규 내에서 작업하십시오. Adobe Campaign의 기능을 통해 [이 페이지](../start/privacy.md)에 나열된 규정을 준수할 수 있습니다.

### Adobe Experience Cloud 개인 정보 보호 {#experience-cloud-privacy}

Adobe Campaign은 Adobe Experience Cloud 솔루션의 일부입니다. Campaign에서 개인 정보를 처리하는 방식은 다음과 같은 Experience Cloud 일반 원칙을 따릅니다.

* **Adobe Experience Cloud 사용 시 수집되는 정보**

  Adobe Experience Cloud 솔루션을 사용하는 회사는 수집할 정보를 선택하고 Adobe Experience Cloud 계정으로 보냅니다. 수집할 수 있는 정보의 유형에는 웹 검색 활동, IP 주소, 모바일 디바이스의 위치 정보, 캠페인 성공률, 장바구니에서 구매 또는 장바구니로 배치된 항목 등이 있습니다.

  >[!NOTE]
  >
  >모든 Adobe 제품에 대해 Campaign은 앱 및 웹 사이트 사용자에 대한 정보를 수집합니다. 자세한 내용은 [Adobe 개인정보 처리방침](https://www.adobe.com/kr/privacy/policy.html)을 참조하십시오.

* **Adobe Experience Cloud을 정보를 수집하는 데 사용하는 방법**

   * Adobe Experience Cloud 솔루션은 사용자가 정보를 수집할 수 있도록 쿠키 및 웹 비콘(태그 또는 픽셀로도 알려져 있음)과 같은 유사한 기술을 사용합니다. Adobe Campaign의 쿠키 및 추적 기능에 대한 자세한 내용은 [이 섹션](#tracking-capabilities)을 참조하십시오.
   * 또한 모바일 앱에서 Adobe Experience Cloud 기술을 사용할 수 있습니다. Campaign으로 모바일 게재를 보내는 방법에 대한 자세한 내용은 [SMS 채널](../send/sms/sms-channel.md) 및 모바일 앱 채널을 참조하십시오.

* **Adobe Experience Cloud 사용에 대한 사용자의 개인 정보 보호 선택**

  Adobe는 고객에게 다음과 같은 내용을 설명하는 개인정보 처리방침을 제공하도록 요구합니다.

   * Adobe Experience Cloud과 관련된 개인 정보 보호 사례
   * 사용자가 Adobe Experience Cloud과 관련하여 자신의 정보를 수집하거나 사용하는 것에 대한 환경 설정을 하는 방법

  >[!NOTE]
  >
  >모든 Adobe 제품에서 Campaign 사용자는 앱 및 웹 사이트를 통해 수집된 정보의 공유를 옵트아웃할 수 있습니다. 자세한 내용은 [Adobe Experience Cloud 사용 정보 FAQ](https://www.adobe.com/kr/privacy/experience-cloud-usage-info-faq.html)를 참조하십시오.

Adobe Experience Cloud 개인 정보 보호에 대한 자세한 내용은 [이 페이지](https://www.adobe.com/kr/privacy/marketing-cloud.html)를 참조하십시오.

## 개인 데이터 및 가상 사용자 {#personal-data}

개인 정보 관리 시 누가 어떤 데이터를 주의 깊게 처리할지를 정의하는 것이 중요합니다.
* **개인 데이터**&#x200B;는 살아있는 개인을 직접 또는 간접적으로 식별할 수 있는 정보입니다.
* **중요한 개인 데이터**&#x200B;는 노동조합 멤버십뿐 아니라 개인의 인종, 정치적 관점, 종교적 신념, 범죄 기록, 유전자 정보, 건강 정보, 성적 선호도, 생체 인식 정보 등과 관련된 정보입니다.

[Adobe Analytics](../connect/ac-aa.md), [Experience Cloud 대상](../start/shared-audiences.md), Campaign Standard 또는 [CRM 커넥터](../../automation/workflow/crm-connector.md)를 통한 다른 솔루션과 같이 대상을 다른 시스템으로 전송할 수 있는 다른 Experience Cloud 솔루션과 Campaign을 통합하면 개인 데이터 보호를 위해 추가 비용을 지불해야 합니다.

[기본 규정](#privacy-regulations)은 다음과 같이 데이터를 관리하는 서로 다른 엔터티를 의미합니다.

* **데이터 컨트롤러**&#x200B;는 개인 데이터를 수집, 사용 및 공유하는 방법과 목적을 결정하는 인증 기관입니다.

* **데이터 프로세서**&#x200B;는 데이터 컨트롤러의 지시에 따라 개인 데이터를 수집, 사용 또는 공유하는 개인 또는 주체입니다.

* **데이터 주체**&#x200B;는 개인 데이터를 수집, 사용 또는 공유하며 해당 개인 데이터를 참조해서 직접 또는 간접적으로 식별할 수 있는 살아있는 개인입니다.

따라서 개인 데이터를 수집 및 공유하는 회사는 데이터 컨트롤러이며 클라이언트는 데이터 주체이고 Adobe Campaign은 데이터 프로세서의 역할을 합니다. [개인 정보 보호 요청](#privacy-requests)을 관리할 때와 같이 데이터 주체와의 관계를 처리하는 것은 데이터 컨트롤러로서의 책임입니다.

### 사용 사례 시나리오 {#use-case-scenario}

서로 다른 페르소나가 상호 작용하는 방법을 보여주기 위해 높은 수준의 GDPR 고객 경험을 예로 들어보겠습니다.

이 예에서는 항공사가 Adobe Campaign 고객입니다. 이 회사는 **데이터 컨트롤러**&#x200B;이고 항공사의 모든 클라이언트는 **데이터 주체**&#x200B;입니다. 이 특정 경우에서 Laura는 항공사의 고객입니다.

이 예제에서 사용되는 다양한 페르소나는 다음과 같습니다.

* **Laura**&#x200B;는 **데이터 주체**&#x200B;입니다. Laura는 항공사로부터 메시지를 받는 수신자입니다. Laura는 정기적인 고객이지만, 어떤 시점에서는 항공사로부터 개인화된 광고나 마케팅 메시지를 받고 싶지 않다고 결정할 수 있습니다. Laura는 항공사의 절차에 따라 정기 고객 번호를 삭제하도록 요구할 겁니다.

* **Anne**&#x200B;는 항공사의 **데이터 컨트롤러**&#x200B;입니다. Laura의 요청을 받고 데이터 주체를 식별하기 위해 요청한 유용한 ID를 검색한 다음 Adobe Campaign에서 요청을 제출합니다.

* **Adobe Campaign**&#x200B;은 **데이터 프로세서**&#x200B;입니다.

![](assets/privacy-gdpr-flow.png)

이 사용 사례의 일반적인 흐름은 다음과 같습니다.

1. **데이터 주체**(Laura)는 이메일, 고객 지원 센터 또는 웹 포털을 통해 **데이터 컨트롤러**&#x200B;에게 GDPR 요청을 보냅니다.

1. **데이터 컨트롤러**(Anne)는 인터페이스를 통해서나 API를 사용하여 GDPR 요청을 Campaign으로 푸시합니다.

1. **데이터 프로세서**(Adobe Campaign)이 정보를 수신하면 GDPR 요청에 대해 조치를 취하여 **데이터 컨트롤러**(Anne)에게 응답이나 승인을 보냅니다.

1. 그런 다음 **데이터 컨트롤러**(Anne)가 정보를 검토하고 다시 **데이터 주체**(Laura)로 보냅니다.

## 데이터 확보 {#data-acquisition}

Adobe Campaign을 사용하면 개인 및 중요한 정보를 포함한 데이터를 수집할 수 있습니다. 따라서 수신자로부터 동의를 받고 모니터링하는 것이 중요합니다.

* 항상 수신자가 커뮤니케이션 수신에 동의하도록 합니다. 이를 위해서는 옵트아웃 요청을 최대한 빨리 준수하고 이중 옵트인 프로세스를 통해 동의를 확인하십시오. 자세한 내용은 [이중 옵트인](https://experienceleague.adobe.com/ko/docs/campaign-classic/using/designing-content/web-forms/use-cases-web-forms){target=_blank}을 사용하여 구독 양식 만들기를 참조하십시오.
* 사기성 목록을 가져와서 시드 주소로 사용하여 클라이언트 파일이 부정하게 사용되지 않고 있는지 확인하지 마십시오. 자세한 내용은 [시드 주소 정보](https://experienceleague.adobe.com/ko/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses){target=_blank}를 참조하십시오.
* 동의 및 권한 관리를 통해 수신자의 환경 설정을 추적할 수 있을 뿐만 아니라 조직 내에서 누가 어떤 데이터에 액세스할 수 있는지를 관리할 수 있습니다. 자세한 내용은 [이 섹션](#consent)을 참조하십시오.
* 수신자의 개인 정보 보호 요청을 간편하게 지원하고 관리할 수 있습니다. 자세한 내용은 [이 섹션](#privacy-requests)을 참조하십시오.

## 개인 정보 보호 관리 {#privacy-management}

개인 정보 관리는 개인 정보 보호 규정(GDPR, CCPA 등)을 준수하는 데 도움이 되는 모든 프로세스 및 도구를 의미합니다.

Adobe Campaign은 개인 정보 관리를 위한 다양한 기능을 제공합니다.
* 동의 관리, 데이터 보존 및 사용자 역할. [이 섹션](#consent)을 참조하십시오.
* 개인 정보 보호 요청(액세스 권한 및 잊혀질 권리). [이 섹션](#privacy-requests)을 참조하십시오.
* 개인 정보 판매 옵트아웃(CCPA별).

Campaign의 주요 개인 정보 보호 기능과 여기에 관련된 페르소나의 예가 [이 섹션](https://helpx.adobe.com/kr/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow)에 제시되어 있습니다.

### 동의, 보존 및 역할 {#consent}

기본적으로 Adobe Campaign은 다음과 같은 개인 정보에 필수적인 중요한 기능을 제공합니다.

* **동의 관리**: 구독 관리 프로세스를 통해 수신자의 환경 설정을 관리하고 어떤 수신자가 어떤 구독 유형을 옵트인했는지 추적할 수 있습니다. 자세한 내용은 [구독 정보](../../automation/workflow/subscription-services.md)를 참조하십시오.
* **데이터 보존**: 모든 기본 제공 표준 로그 테이블에는 사전 설정된 보존 기간이 있으며 일반적으로 데이터 저장소를 6개월 이하로 제한합니다. 워크플로로 추가 보존 기간을 설정할 수 있습니다. 자세한 내용은 Adobe 컨설턴트나 기술 관리자에게 문의하십시오.
* **권한 관리**: Adobe Campaign은 다양한 사전 설치 또는 사용자 지정 역할을 통해 다양한 캠페인 운영자에게 할당된 권한을 관리할 수 있는 기능을 제공합니다. 이를 통해 회사 내에서 다른 유형의 데이터에 액세스, 수정 또는 내보낼 수 있는 사용자를 관리할 수 있습니다. 자세한 내용은 [액세스 관리 정보](https://experienceleague.adobe.com/ko/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management){target=_blank}를 참조하십시오.

### 개인 정보 보호 요청 {#privacy-requests}

Adobe Campaign은 특정 개인 정보 보호 요청에 대해 데이터 컨트롤러로서 사용자의 준비를 용이하게 하는 데 도움이 되는 추가 기능을 제공합니다.

* **액세스 권한**&#x200B;은 데이터 주체가 데이터 주체의 확인을 통해 데이터 주체의 개인 데이터가 처리 중인지 여부, 처리 장소 및 그 이유를 알 수 있는 권리입니다.

* **잊혀질 권리**(삭제 요청)는 데이터 주체가 자신의 개인 데이터를 삭제하도록 권한을 부여합니다.

**액세스** 및 **삭제** 요청은 [이 섹션](../start/privacy.md)에서 다루고 있습니다.

이러한 요청을 만드는 구현 단계는 [이 섹션](../start/privacy.md)에 자세히 설명되어 있습니다.

## 추적 기능 {#tracking-capabilities}

### 쿠키 {#cookies}

추적 기능 덕분에 Adobe Campaign을 사용하면 3가지 유형의 쿠키를 사용하여 전달받는 사람의 검색을 추적할 수 있습니다.

* **session** 쿠키: **nlid** 쿠키에는 연락처로 보낸 전자 메일의 식별자&#x200B;**broadlogId**)와 메시지 템플릿의 식별자(**deliveryId**)가 포함됩니다. 이 URL은 연락처가 Adobe Campaign이 보낸 전자 메일에 포함된 URL을 클릭할 때 추가되며, 이를 통해 웹에서 해당 동작을 추적할 수 있습니다. 브라우저를 닫으면 이 세션 쿠키가 자동으로 지워집니다. 연락처는 브라우저가 쿠키를 거부하도록 구성할 수 있습니다.

* **영구** 쿠키 2개:
   * Adobe Experience Cloud 솔루션 간에 **UUID**(Universal Unique IDentifier) 쿠키가 공유됩니다. 새 값이 생성될 때 클라이언트 브라우저에서 사라질 때까지 한 번 설정됩니다. 이 쿠키를 사용하면 웹 사이트를 방문할 때 Experience Cloud 솔루션과 상호 작용하는 사용자를 식별할 수 있습니다. 랜딩 페이지(알 수 없는 고객 활동을 수신자에게 연결)나 게재를 통해 보관할 수 있습니다. 이 쿠키의 설명은 [이 페이지](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html?lang=ko#ec-cookies)에서 사용할 수 있습니다.
   * **nllastdelid** 쿠키(Campaign Classic 20.3에서 도입됨)는 사용자가 링크를 클릭한 마지막 게재의 **deliveryId**&#x200B;가 포함된 영구 쿠키입니다. 이 쿠키는 세션 쿠키가 없을 때 사용될 추적 테이블을 식별하기 위해 사용됩니다.

GDPR(일반 데이터 보호 규정)과 같은 규정에서는 회사가 쿠키를 설치하기 전에 웹 사이트 사용자의 계약을 요구하는 것을 명시합니다.

* 팝업 창은 브라우저에 의해 종종 차단되므로 사용하지 않아야 합니다.

### 메시지 추적 {#message-tracking}

Adobe Campaign을 사용하면 보낸 이메일과 전달받는 사람의 동작(열기, 링크 클릭, 구독 취소 등)을 추적할 수 있습니다. 자세한 내용은 [메시지 정보](../start/gs-message.md)를 참조하세요.

이렇게 하려면 게재 대시보드의 추적 탭에서 게재 및 받는 사람 동작의 영향을 측정하기 위해 추적된 링크를 메시지에 추가합니다. 추적 데이터는 추적 표시기 보고서에 해석되어 있습니다. 추적에 대한 자세한 내용은 [이 페이지](../send/tracking.md)를 참조하세요.

### 웹 추적 {#web-tracking}

>[!AVAILABILITY]
>
>웹 추적은 Campaign v8에서 사용할 수 없습니다. [이 페이지](../start/v7-to-v8.md#gs-unavailable-features)에서 사용할 수 없는 기능에 대해 자세히 알아보세요.

## 데이터 및 PII 보호 {#data-and-pii-protection}

개인 정보 보호 구성 및 강화는 보안 최적화의 핵심 요소입니다. 다음 모범 사례를 따르십시오.

* **모든 끝점에 HTTPS 사용** - Campaign에서 사용하는 모든 끝점(추적, 미러 페이지, 웹 응용 프로그램, API)이 HTTPS를 통해 제공되는지 확인합니다.
* **PII 보기 제한** - 권한이 있는 운영자만 스키마와 화면에서 중요한 필드(예: 이메일, 휴대폰)를 볼 수 있도록 [PII 보기 제한](../dev/restrict-pi-view.md)을 사용합니다.
* **암호화된 암호에 대한 액세스 제한** - 관리자 또는 최소 운영자 집합만 볼 수 있도록 외부 계정 및 기타 스키마의 암호 및 암호 필드에 대한 액세스를 제한합니다. 아래의 [데이터 제한](#data-restriction)을 참조하세요.
* **중요한 페이지 보호** - PII를 표시하거나 수집하는 미러 페이지, 웹 응용 프로그램 및 랜딩 페이지에 대한 액세스를 제한하고, 연산자 및 폴더 권한을 사용하며, 적절한 경우 captchas 및 동의를 사용합니다.

>[!NOTE]
>
>Adobe은 Managed Cloud Services 사용자의 경우 사용자와 협력하여 환경에 이러한 구성을 구현합니다.

## 액세스 관리 {#access-management}

액세스 관리는 보안 강화의 중요한 부분입니다. 주요 모범 사례는 다음과 같습니다.

* **충분한 보안 그룹을 만듭니다** - 역할과 일치하는 연산자 그룹을 정의하고 각 역할에 필요한 권한만 할당합니다.
* **각 연산자에게 적절한 액세스 권한이 있는지 확인** - 최소 권한의 원칙을 적용합니다. 기본적으로 ADMINISTRATION 또는 기타 광범위한 권한을 부여하지 마십시오.
* **관리자 연산자를 사용하지 말고 관리자 그룹에 연산자가 너무 많지 않도록 하십시오** - 기본 제공 관리자 계정을 공유하지 마십시오. 책임 및 감사를 위해 실제 사용자당 한 명의 연산자를 만드십시오.
* **실제 사용자당 한 명의 연산자** - 계정을 공유하지 않습니다. 감사 추적 및 로그가 부여되도록 1인당 1개의 Campaign 운영자(Adobe ID)를 만듭니다.
* **높은 권한으로 명명된 권한 제한** - 신뢰할 수 있는 소수의 연산자에게만 **관리**, **프로그램 실행**(createProcess) 및 **SQL**&#x200B;을 부여합니다. 해당 연산자의 이름과 이유를 문서화합니다.
* **정기적으로 액세스 검토** - 운영자, 운영자 그룹 및 폴더 권한을 정기적으로 검토합니다. 역할이 변경되거나 사용자가 나가면 액세스를 제거하거나 줄이세요.
* **제품 프로필을 일관되게 사용** - Admin Console에서 제품 프로필(운영자 그룹)에 사용자를 할당하는 것을 선호하고, 이름을 일관되게 유지합니다(예: `campaign - <instance> - <group>`). [사용 권한 시작](../start/gs-permissions.md)을 참조하세요.
* **Campaign 컨트롤 패널 액세스** - Campaign v8에서 이름에 &quot;admin&quot;이 포함된 제품 프로필 또는 명명된 권한은 Campaign Campaign 컨트롤 패널에 대한 액세스 권한을 부여할 수 있습니다. 해당 사용자에게 Campaign 컨트롤 패널 액세스 권한이 있어야 하는 경우가 아니면 프로필 또는 그룹 이름에 &quot;admin&quot;을 사용하지 마십시오.

[이 섹션](../start/gs-permissions.md)에서 권한에 대해 자세히 알아보십시오.

## 인증 및 세션 {#authentication-and-session}

* **Adobe IMS 사용** - 모든 사용자는 Adobe ID(IMS)로 로그인해야 합니다. 일상적인 연산자를 위해 기존 로그인/암호를 사용하지 마십시오.
* **강력한 ID 및 암호 정책 사용** - MFA 및 암호 정책에 대해 Admin Console 또는 ID 공급자를 사용합니다. 인증된 사용자만 Campaign 제품 프로필에 할당되도록 하십시오.
* **세션 시간 제한 구성** - 구성 가능한 경우(예: 클라이언트 콘솔) 적절한 세션 시간 제한을 설정하고 워크스테이션에서 나갈 때 화면을 잠급니다.

## 인스턴스 및 네트워크 보안 {#instance-and-network-security}

Campaign v8 제품 관리자는 [Campaign Campaign 컨트롤 패널](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ko){target="_blank"}을(를) 사용하여 인스턴스 수준 보안을 관리합니다.

* **IP 허용 목록** - 인스턴스 액세스에 대한 IP 허용 목록을 관리합니다. 알려진 네트워크(예: 사무실, VPN)로 제한하고 가능한 경우 범위가 너무 넓어지지 않도록 합니다.
* **URL 권한** - 서버측 요청 남용 위험을 줄이기 위해 인스턴스가 호출해야 하는 도메인(API, 추적, 외부 서비스)에 대해 URL 권한을 제한합니다.
* **GPG 키** - 파일 전송 또는 기타 사용 사례에 암호화를 사용하는 경우 Campaign 컨트롤 패널을 통해 GPG 키를 관리하고 보안 정책에 따라 키를 회전합니다.

## 코딩 지침 {#coding-guidelines}

Adobe Campaign(워크플로우, Javascript, JSSP 등)에서 개발할 때는 항상 다음 지침을 따르십시오.

* **스크립팅** - 원시 SQL을 사용하지 마십시오. 문자열 연결 대신 매개 변수가 있는 함수를 사용하십시오. 허용 목록에 필요한 SQL 함수만 추가하여 SQL 삽입을 방지합니다.
* **데이터 모델 보안** - 명명된 권한을 사용하여 연산자 작업을 제한하고 시스템 필터(sysFilter)를 추가하십시오.
* **웹 응용 프로그램에 CAPTCHA 추가** - 공용 랜딩 페이지 및 구독 페이지에 CAPTCHA를 추가합니다.
* **암호를 하드코딩하지 마십시오** - 워크플로, JavaScript 또는 JSSP의 암호, API 키 또는 토큰을 하드코딩하지 마십시오. 외부 계정 또는 보안 구성을 사용하십시오.
* **입력 유효성 검사 및 기밀 유지** - 웹 응용 프로그램 및 워크플로 매개 변수의 사용자 입력 유효성 검사 및 기밀 유지를 통해 주입 및 XSS 위험을 줄일 수 있습니다.
* **SQL용 허용 목록 사용** - SQL 또는 스크립트 실행이 필요한 경우 허용된 SQL 함수에 허용 목록을 사용하고 문자열 연결을 통해 사용자 입력에서 쿼리를 작성하지 마십시오.

자세한 내용은 [Adobe Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=ko#installing-campaign-classic){target="_blank"}를 참조하세요.


## 개인화

콘텐츠에 개인화된 링크를 추가할 때 잠재적인 보안 차이를 방지하기 위해 항상 URL의 호스트 이름 부분에 개인화를 두지 마십시오. 다음 예제는 모든 URL 특성 &lt;`a href="">` 또는 `<img src="">`에 사용해서는 안 됩니다.

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## 데이터 제한 {#data-restriction}

권한이 낮은 인증된 사용자가 암호화된 암호에 액세스할 수 없도록 해야 합니다. 이를 위해 두 가지 기본 방법이 있습니다. 암호 필드에만 또는 전체 엔터티에 대한 액세스를 제한합니다.

이 제한 사항을 사용하면 암호 필드를 제거할 수 있지만 모든 사용자의 인터페이스에서 외부 계정에 액세스할 수 있는 상태를 유지합니다. [이 페이지](../dev/restrict-pi-view.md)에서 자세히 알아보십시오.

1. **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**&#x200B;에서 이동합니다.

1. 새 **[!UICONTROL Extension of a schema]** 만들기

1. **[!UICONTROL External Account]**(extAccount)을 선택합니다.

1. 마지막 화면에서는 새 srcSchema를 편집하여 모든 암호 필드에 대한 액세스를 제한할 수 있습니다.

   주 요소(`<element name="extAccount" ... >`)를 다음과 같이 바꿀 수 있습니다.

   ```
   <element name="extAccount">
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
       <element name="s3Account">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
       </element>
       <element name="wapPush">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
       <element name="mms">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
   </element>
   ```

   이렇게 확장된 srcSchema는 다음과 같이 표시됩니다.

   ```
   <...>
       <element name="extAccount">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
           <element name="s3Account">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
           </element>
           <element name="wapPush">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
           <element name="mms">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
       </element>
   <...> 
   ```

   >[!NOTE]
   >
   >`$(loginId) = 0 or $(login) = 'admin'`을(를) `hasNamedRight('admin')`(으)로 바꾸면 관리자 권한이 있는 모든 사용자가 이러한 암호를 볼 수 있습니다.

## 운영 및 규정 준수 {#operational-and-compliance}

* **보안 기준선과 비교** - 연산자 그룹, 명명된 권한 및 폴더 권한을 주기적으로 이 페이지의 권장 사항과 비교하여(해당하는 경우 [향상된 보안 추가 기능](enhanced-security.md)) 권장 보안 기본값에 맞춥니다.
* **감사 추적 사용** - 중요한 변경 사항(예: 워크플로우, 게재, 주요 구성)에 대해서는 Campaign의 감사 추적을 사용합니다. 규정 준수 및 보존 정책에 따라 로그를 유지하고 검토합니다.
