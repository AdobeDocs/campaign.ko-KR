---
title: Campaign 보안 모범 사례
description: Campaign 보안 모범 사례 시작
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '2270'
ht-degree: 68%

---

# Campaign 보안 모범 사례 {#ac-security}

Adobe에서는 디지털 경험에 대한 보안을 매우 중요하게 생각합니다. 보안 관행은 내부 소프트웨어 개발 및 운영 프로세스 및 도구에 깊이 배어있으며, 여러 분야의 다양한 팀이 협력하여 사건을 신속하게 예방, 감지 및 대응합니다.

또한 파트너, 주요 연구원, 보안 연구 기관 및 기타 산업 조직과의 공동 작업을 통해 최신 위협 및 취약점을 최신 상태로 유지할 수 있으며, 고급 보안 기술을 제공하는 제품 및 서비스에 정기적으로 통합합니다.

## 개인 정보 보호

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

서로 다른 가상 사용자가 상호 작용하는 방법을 보여주기 위해 높은 수준의 GDPR 고객 경험을 예로 들어보겠습니다.

이 예에서는 항공사가 Adobe Campaign 고객입니다. 이 회사는 **데이터 컨트롤러**&#x200B;이고 항공사의 모든 클라이언트는 **데이터 주체**&#x200B;입니다. 이 특정 경우에서 Laura는 항공사의 고객입니다.

이 예제에서 사용되는 다양한 가상 사용자는 다음과 같습니다.

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

* 항상 수신자가 커뮤니케이션 수신에 동의하도록 합니다. 이를 위해서는 옵트아웃 요청을 최대한 빨리 준수하고 이중 옵트인 프로세스를 통해 동의를 확인하십시오. 자세한 내용은 [이중 옵트인](https://experienceleague.adobe.com/en/docs/campaign-classic/using/designing-content/web-forms/use-cases-web-forms){target=_blank}을 사용하여 구독 양식 만들기를 참조하십시오.
* 사기성 목록을 가져와서 시드 주소로 사용하여 클라이언트 파일이 부정하게 사용되지 않고 있는지 확인하지 마십시오. 자세한 내용은 [시드 주소 정보](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses){target=_blank}를 참조하십시오.
* 동의 및 권한 관리를 통해 수신자의 환경 설정을 추적할 수 있을 뿐만 아니라 조직 내에서 누가 어떤 데이터에 액세스할 수 있는지를 관리할 수 있습니다. 자세한 내용은 [이 섹션](#consent)을 참조하십시오.
* 수신자의 개인 정보 보호 요청을 간편하게 지원하고 관리할 수 있습니다. 자세한 내용은 [이 섹션](#privacy-requests)을 참조하십시오.

## 개인 정보 보호 관리 {#privacy-management}

개인 정보 관리는 개인 정보 보호 규정(GDPR, CCPA 등)을 준수하는 데 도움이 되는 모든 프로세스 및 도구를 의미합니다.

Adobe Campaign은 개인 정보 관리를 위한 다양한 기능을 제공합니다.
* 동의 관리, 데이터 보존 및 사용자 역할. [이 섹션](#consent)을 참조하십시오.
* 개인 정보 보호 요청(액세스 권한 및 잊혀질 권리). [이 섹션](#privacy-requests)을 참조하십시오.
* 개인 정보 판매 옵트아웃(CCPA별).

Campaign의 주요 개인 정보 보호 기능과 관련된 개인의 예가 [이 섹션](https://helpx.adobe.com/kr/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow)에 나와 있습니다.

### 동의, 보존 및 역할 {#consent}

기본적으로 Adobe Campaign은 다음과 같은 개인 정보에 필수적인 중요한 기능을 제공합니다.

* **동의 관리**: 구독 관리 프로세스를 통해 수신자의 환경 설정을 관리하고 어떤 수신자가 어떤 구독 유형을 옵트인했는지 추적할 수 있습니다. 자세한 내용은 [구독 정보](../../automation/workflow/subscription-services.md)를 참조하십시오.
* **데이터 보존**: 모든 기본 제공 표준 로그 테이블에는 사전 설정된 보존 기간이 있으며 일반적으로 데이터 저장소를 6개월 이하로 제한합니다. 워크플로로 추가 보존 기간을 설정할 수 있습니다. 자세한 내용은 Adobe 컨설턴트나 기술 관리자에게 문의하십시오.
* **권한 관리**: Adobe Campaign은 다양한 사전 설치 또는 사용자 지정 역할을 통해 다양한 캠페인 운영자에게 할당된 권한을 관리할 수 있는 기능을 제공합니다. 이를 통해 회사 내에서 다른 유형의 데이터에 액세스, 수정 또는 내보낼 수 있는 사용자를 관리할 수 있습니다. 자세한 내용은 [액세스 관리 정보](https://experienceleague.adobe.com/en/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management){target=_blank}를 참조하십시오.

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
   * Adobe Experience Cloud 솔루션 간에 **UUID**(Universal Unique IDentifier) 쿠키가 공유됩니다. 새 값이 생성될 때 클라이언트 브라우저에서 사라질 때까지 한 번 설정됩니다. 이 쿠키를 사용하면 웹 사이트를 방문할 때 Experience Cloud 솔루션과 상호 작용하는 사용자를 식별할 수 있습니다. 랜딩 페이지(알 수 없는 고객 활동을 수신자에게 연결)나 게재를 통해 보관할 수 있습니다. 이 쿠키의 설명은 [이 페이지](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html#ec-cookies)에서 사용할 수 있습니다.
   * **nllastdelid** 쿠키(Campaign Classic 20.3에서 도입됨)는 사용자가 링크를 클릭한 마지막 게재의 **deliveryId**&#x200B;가 포함된 영구 쿠키입니다. 이 쿠키는 세션 쿠키가 없을 때 사용될 추적 테이블을 식별하기 위해 사용됩니다.

GDPR(일반 데이터 보호 규정)과 같은 규정에서는 회사가 쿠키를 설치하기 전에 웹 사이트 사용자의 계약을 요구하는 것을 명시합니다.

* 쿠키의 설치를 승인하는 확인란이 포함된 권한 부여 요청(예: 페이지 위로 올라오는 요청)을 통해 사이트가 웹 추적 도구를 갖추고 있음을 사용자에게 알리거나, 첫 번째 랜딩 페이지 등에 배너를 추가해야 합니다.
* 팝업 창은 브라우저에 의해 종종 차단되므로 사용하지 않아야 합니다.

### 메시지 추적 {#message-tracking}

Adobe Campaign을 사용하면 보낸 이메일과 전달받는 사람의 동작(열기, 링크 클릭, 구독 취소 등)을 추적할 수 있습니다. 자세한 내용은 [메시지 정보](../start/gs-message.md)를 참조하세요.

이렇게 하려면 게재 대시보드의 추적 탭에서 게재 및 받는 사람 동작의 영향을 측정하기 위해 추적된 링크를 메시지에 추가합니다. 추적 데이터는 추적 표시기 보고서에 해석되어 있습니다. 추적에 대한 자세한 내용은 [이 페이지](../start/tracking.md)를 참조하세요.

### 웹 추적 {#web-tracking}

또한 Adobe Campaign을 사용하면 수신자가 웹 사이트를 검색하는 방법을 모니터링할 수 있습니다. 추적 태그를 삽입하여 웹 애플리케이션 페이지에서 정보를 수집하고 방문을 측정합니다.

웹 추적 구성은 [이 섹션](../start/tracking.md)에 설명되어 있습니다.

추적을 추가로 관리하기 위해 Adobe Campaign에서는 옵트아웃 배너를 표시하여 행동 추적을 옵트아웃한 최종 사용자의 웹 동작 추적을 중지할 수 있습니다. 자세한 내용은 [웹 애플리케이션 추적 옵트아웃](https://experienceleague.adobe.com/en/docs/campaign-classic/using/designing-content/web-applications/web-application-tracking-opt-out){target=_blank}을 참조하십시오.

<!--
Privacy configuration and hardening is a key element of security optimization. Here are some best practices to follow regarding privacy:

* Protect your customer Personal Information (PI) by using HTTPS instead of HTTP
* Use [PI view restriction](../dev/restrict-pi-view.md) to protect privacy and prevent data from being misused
* Make sure that encrypted passwords are restricted
* Protect the pages that might contain personal information such as mirror pages, web applications, etc.
-->

>[!NOTE]
>
>Adobe은 Managed Cloud Services 사용자의 경우 사용자와 협력하여 환경에 이러한 구성을 구현합니다.


## 액세스 관리

액세스 관리는 보안 강화의 중요한 부분입니다. 다음은 몇 가지 주요 모범 사례입니다.

* 충분한 보안 그룹 만들기
* 각 운영자에게 적절한 액세스 권한이 있는지 확인합니다

[이 섹션](../start/gs-permissions.md)에서 사용 권한에 대해 자세히 알아보기

## 코딩 지침

Adobe Campaign(워크플로우, Javascript, JSSP 등)에서 개발할 때는 항상 다음 지침을 따르십시오.

* **스크립팅**: SQL 문을 사용하지 않도록 하고, 문자열 연결 대신 매개 변수가 있는 함수를 사용하고, 허용 목록에 사용할 SQL 함수를 추가하여 SQL 삽입을 방지하십시오.

* **데이터 모델 보안**: 명명된 권한을 사용하여 연산자 작업을 제한하고 시스템 필터(sysFilter)를 추가하십시오.

* **웹 응용 프로그램에 captcha 추가**: 공개 랜딩 페이지 및 구독 페이지에 captcha를 추가합니다.

자세한 내용은 [Adobe Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}를 참조하세요.


## 개인화

콘텐츠에 개인화된 링크를 추가할 때 잠재적인 보안 차이를 방지하기 위해 항상 URL의 호스트 이름 부분에 개인화를 두지 마십시오. 다음 예제는 모든 URL 특성 &lt;`a href="">` 또는 `<img src="">`에 사용해서는 안 됩니다.

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## 데이터 제한

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


## 액세스 관리

액세스 관리는 보안 강화의 중요한 부분입니다. 다음은 몇 가지 주요 모범 사례입니다.

* 충분한 보안 그룹 만들기
* 각 운영자에게 적절한 액세스 권한이 있는지 확인합니다

[의 사용 권한에 대한 자세한 내용은 이 섹션](../start/gs-permissions.md)을 참조하세요.

## 코딩 지침

Adobe Campaign(워크플로우, Javascript, JSSP 등)에서 개발할 때는 항상 다음 지침을 따르십시오.

* **스크립팅**: SQL 문을 사용하지 않도록 하고, 문자열 연결 대신 매개 변수가 있는 함수를 사용하고, 허용 목록에 사용할 SQL 함수를 추가하여 SQL 삽입을 방지하십시오.

* **데이터 모델 보안**: 명명된 권한을 사용하여 연산자 작업을 제한하고 시스템 필터(sysFilter)를 추가하십시오.

* **웹 응용 프로그램에 captcha 추가**: 공개 랜딩 페이지 및 구독 페이지에 captcha를 추가합니다.

자세한 내용은 [Adobe Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}를 참조하세요.
