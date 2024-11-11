---
title: 게재 모범 사례
description: Adobe Campaign을 사용하여 게재를 디자인하고 전송할 때의 모범 사례에 대해 알아봅니다
feature: Email, Push, SMS, Direct Mail
role: User
level: Beginner
exl-id: cb6094eb-0010-4c62-9589-3b52fd60c2c2
source-git-commit: 768ebf4b350da61f0076eb9e43a16246be3b2628
workflow-type: tm+mt
source-wordcount: '2936'
ht-degree: 2%

---

# 게재 모범 사례 {#delivery-best-practices}

Campaign 게재 기능을 사용한 다음 모범 사례를 살펴보십시오.

## 게재 최적화 {#optimize-delivery}

게재 만들기를 시작하기 전에 전송 프로세스 업스트림을 보호하고 최적화하는 몇 가지 작업을 수행할 수 있습니다. 다음 섹션에서는 Adobe Campaign의 최적 구성을 위한 모범 사례 및 권장 절차에 대해 설명합니다.

### 플랫폼 성능

서버 성능에 직접적인 영향을 주고 Campaign 플랫폼을 느리게 하는 몇 가지 요인이 있습니다.

* [개인화](../send/personalize.md) 요소의 수와 유형: 전자 메일의 개인화는 각 수신자의 데이터를 데이터베이스에서 가져옵니다. 개인화 요소가 많은 경우 게재를 준비하는 데 필요한 데이터의 양이 더 많습니다. 이로 인해 플랫폼이 느려질 수 있습니다. [이 섹션](../send/personalize.md#perso-guardrails)에서 개인화 가드레일에 대해 자세히 알아보세요.

* 서버 로드: 마케팅 서버가 여러 작업을 동시에 처리할 때 성능이 저하될 수 있습니다. 마케팅 서버는 모든 게재에 대해 들어오는 모든 데이터와 나가는 데이터를 조정하여 데이터가 정확하고 정시에 도착하는지 확인해야 합니다.
이를 방지하려면 팀의 다른 멤버와 게재 일정을 조정하여 최상의 성능을 보장하십시오.

* 워크플로우 실행: 플랫폼 성능 문제를 방지하려면 워크플로우를 모니터링해야 합니다. 이 문서의 [에 나열된 지침](../../automation/workflow/workflow-best-practices.md#execution-and-performance)을(를) 따르십시오.

* [Campaign Campaign 컨트롤 패널 기능](https://experienceleague.adobe.com/en/docs/control-panel/using/discover-control-panel/key-features){target="_blank"}에 연결하여 [성능 모니터링](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/about-performance-monitoring){target="_blank"} 기능을 사용하여 플랫폼을 모니터링합니다.

#### 격리 관리 {#quarantine-management}

좋은 방역 관리 프로세스를 유지하는 것이 최선의 이익입니다.

새 플랫폼에서 이메일을 보내기 시작할 때 정규화된 주소가 아닌 주소 목록을 사용할 수 있습니다. 잘못된 주소 또는 허니팟 주소(스패머를 속이기 위해 만들어진 사서함)로 보내는 경우 플랫폼의 신뢰도가 떨어지기 시작합니다. 훌륭한 격리 관리 프로세스는 주소 품질을 유지하고, 인터넷 액세스 제공업체의 차단 목록에 추가하다를 피하고, 오류율을 낮추어 게재 및 처리 속도를 높이는 데 도움이 됩니다.


[Adobe 전달성 모범 사례 안내서](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/ac-starting-new-platform){target="_blank"}에서 새 플랫폼을 시작하는 방법에 대해 자세히 알아보세요.

기술 권장 사항은 [이 섹션](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations){target="_blank"}에 나열되어 있습니다.


+++ **모범 사례 몇 가지 읽기**

* Adobe 잘못된 주소 목록이 있는 경우 **[!UICONTROL Administration]** > **[!UICONTROL Campaign Management]** > **[!UICONTROL Non deliverables Management]** > **[!UICONTROL Non deliverables and addresses]**&#x200B;을(를) 통해 격리 테이블로 가져오는 것이 좋습니다.

* 주소가 격리된 수신자는 기본적으로 게재 분석 중에 제외됩니다. 이 수신자는 타겟팅되지 않습니다. 이렇게 하면 오류율이 게재 속도에 중요한 영향을 미치므로 게재 속도가 빨라집니다. 예를 들어 받은 편지함이 가득 찼거나 주소가 없는 경우 이메일 주소를 격리할 수 있습니다.
Adobe Campaign은 반환된 오류 유형에 따라 잘못된 주소를 관리합니다. [격리에 대해 자세히 알아보기](../send/quarantines.md)

* 일부 인터넷 액세스 공급자는 잘못된 주소의 비율이 너무 높은 경우 이메일을 자동으로 스팸으로 간주합니다. 따라서 이러한 공급자에 의해 차단 목록에 추가하다에 추가되는 것을 피할 수 있습니다.

+++



### 이중 옵트인 메커니즘 {#double-opt-in}

잘못된 주소로 메시지를 보내지 않도록 하고 부적절한 통신을 제한하며 보낸 사람의 평판을 향상시키기 위해 Adobe은 구독 후 확인을 위해 이중 옵트인 메커니즘을 구현하는 것을 권장합니다. 이렇게 하면 수신자가 의도적으로 가입했는지 확인하는 데 도움이 됩니다.

## 템플릿 사용 {#use-templates}

게재 템플릿은 가장 일반적인 유형의 활동에 대해 준비된 시나리오를 제공하여 효율성을 높입니다. 마케터는 템플릿을 사용하여 짧은 시간 내에 최소한의 사용자 지정으로 새 캠페인을 배포할 수 있습니다. [게재 템플릿에 대해 자세히 알아보기](../send/create-templates.md).

### 하위 도메인 및 브랜딩 {#subdomains-and-branding}

Adobe Campaign에서 여러 브랜드를 관리할 때, Adobe은 브랜드당 하나의 하위 도메인을 사용하는 것을 권장합니다. 예를 들어 은행은 각 지역 기관에 해당하는 여러 하위 도메인을 가질 수 있습니다. 은행이 bluebank.com 도메인을 소유하는 경우 해당 하위 도메인은 @ny.bluebank.com, @ma.bluebank.com, @ca.bluebank.com 등이 될 수 있습니다. 하위 도메인당 하나의 게재 템플릿을 사용하면 각 브랜드에 대해 항상 올바른 사전 구성된 매개 변수를 사용할 수 있으므로 오류를 방지하고 시간을 절약할 수 있습니다. [Campaign Campaign 컨트롤 패널 설명서](https://experienceleague.adobe.com/en/docs/control-panel/using/subdomains-and-certificates/subdomains-branding){target="_blank"}에서 하위 도메인 브랜딩에 대해 자세히 알아보세요.

### 주소 구성 {#configure-addresses}

다음 지침을 적용하십시오.

* 이메일을 보낼 수 있도록 하려면 발신자 주소가 필수입니다. 일부 ISP(인터넷 서비스 공급자)는 메시지를 수락하기 전에 보낸 사람 주소의 유효성을 확인합니다.
* 잘못된 형식의 주소는 수신 서버에서 거부될 수 있습니다. 주소가 정확한지 확인해야 합니다.
* 주소는 발신자를 명시적으로 식별해야 합니다. 도메인은 발신자가 소유하고 등록해야 합니다.
* Adobe은 게재 및 회신에 대해 지정된 주소에 해당하는 이메일 계정을 만들 것을 권장합니다. 메시징 시스템 관리자에게 문의하십시오.

+++ **Campaign UI에서 주소를 구성하는 단계**

Campaign 인터페이스에서 주소를 구성하려면 아래 단계를 따르십시오.

1. [게재 템플릿](../send/create-templates.md)에서 **[!UICONTROL From]** 링크를 클릭합니다. **[!UICONTROL Email header parameters]** 창에서 설정을 입력합니다.

1. **[!UICONTROL Sender address]** 필드에서 주소 도메인이 Adobe에게 위임한 하위 도메인과 동일한지 확인합니다. &#39;@&#39; 앞 부분은 변경할 수 있지만 도메인 주소는 변경할 수 없습니다.

1. **[!UICONTROL From]** 필드에서 브랜드 이름과 같이 수신자가 쉽게 식별할 수 있는 이름을 사용하여 게재의 열람률을 높입니다. 수신자의 경험을 더 개선하기 위해 개인 이름을 추가할 수 있습니다(예: &quot;Megastore의 Emma&quot;).

1. **[!UICONTROL Reply address text]** 필드에서는 보낸 사람의 주소가 기본적으로 회신에 사용됩니다. 그러나 Adobe은 브랜드의 고객 지원 센터와 같은 기존 실제 주소를 사용하는 것을 권장합니다. 이 경우 수신자가 회신을 보내면 고객 지원 센터에서 이를 처리할 수 있습니다.

### 컨트롤 그룹 설정 {#set-up-control-group}

게재가 전송되면 제외된 수신자의 행동을 게재를 받은 수신자와 비교할 수 있습니다. 그런 다음 캠페인의 효율성을 측정할 수 있습니다. 컨트롤 그룹 [이 섹션](../../automation/campaigns/marketing-campaign-target.md#add-a-control-group)에 대해 자세히 알아보세요.

### 유형화를 사용하여 필터 또는 제어 규칙 적용 {#create-typologies}

유형화에는 메시지를 보내기 전에 분석 단계 중에 적용되는 확인 규칙이 포함되어 있습니다.

필요한 경우 템플릿 속성의 **[!UICONTROL Typology]** 탭에서 사용자 지정 유형화를 선택할 수 있습니다.

예를 들어 아웃바운드 트래픽을 더 잘 제어하기 위해 하위 도메인당 하나의 선호도를 정의하고 선호도당 하나의 유형화를 만들어 사용할 수 있는 IP 주소를 정의할 수 있습니다. 관심도는 인스턴스의 구성 파일에 정의됩니다. Adobe Campaign 관리자에게 문의하십시오.

유형화에 대한 자세한 내용은 [이 섹션](../../automation/campaign-opt/campaign-typologies.md)을 참조하세요.

## 콘텐츠 최적화 {#optimize-content}

### 개인화된 콘텐츠 작성 {#perso-content}

메시지를 개인화하기 위해 데이터베이스에 저장되거나 추적, 랜딩 페이지, 구독 등을 통해 수집된 수신자의 데이터를 사용할 수 있습니다. Personalization 기본 사항은 [이 섹션](../send/personalize.md)에 나와 있습니다.

+++ **모범 사례 몇 가지 읽기**

* 개인화 설정 확인 - 메시지 콘텐츠가 개인화와 관련된 오류를 방지하기 위해 제대로 디자인되었는지 확인하십시오. Adobe Campaign 개인화 태그에는 항상 `<%=table.field%>` 형식이 있습니다. 개인화 블록에서 매개 변수를 잘못 사용하면 문제가 될 수 있습니다. 예를 들어 JavaScript의 변수는 다음과 같이 사용해야 합니다.

  ``
  <%
  var brand = "xxx"
  %>
  ``

  개인화 블록에 대한 자세한 내용은 [이 섹션](../send/personalization-blocks.md)을 참조하세요.

* 개인화 데이터 준비 - 워크플로우에서 개인화 데이터를 준비하여 게재 준비 분석을 개선할 수 있습니다. 개인화 데이터가 FDA(Federated Data Access)를 통해 외부 테이블에서 제공되는 경우 특별히 사용해야 합니다. 이 옵션은 이 [이 섹션](../send/personalization-data.md#optimize-personalization)에 설명되어 있습니다.
+++

### 최적화된 컨텐츠 작성 {#build-optimized-content}

이메일을 작성할 때 이메일 콘텐츠에 대한 일반적인 모범 사례를 적용합니다.

+++ **모범 사례 몇 가지 읽기**

* 디자인 간소화

* 모바일 사용자를 염두에 두십시오

* 전체 이미지 기반 이메일 방지

* 전자 메일 전용 글꼴 사용

* 특수 문자 인코딩

+++


### 제목 줄  {#subject-line-check}

열람률을 향상시키려면 전자 메일 [제목 줄](../send/personalization-fields.md#personalization-fields-uc)을 사용하세요.


+++ **모범 사례 몇 가지 읽기**


* 너무 긴 과목은 피하세요. 최대 50자 사용

* 스팸으로 간주될 수 있는 &quot;무료&quot; 또는 &quot;오퍼&quot;와 같은 단어를 반복적으로 사용하지 마십시오

* 대문자는 피하십시오.

* &quot;!&quot;, &quot;-&quot;, &quot; €&quot;, &quot;$&quot;와 같은 특수 문자를 사용하지 마십시오.

+++

### 페이지 미러링 {#mirror-page-check}

항상 미러 페이지 링크를 포함하십시오. 기본 위치는 이메일의 상단입니다. [이 페이지](../send/mirror-page.md)에서 미러 페이지에 대해 자세히 알아보기

### 구독 취소 링크 {#unsub-link-check}

구독 취소 링크는 필수입니다. 표시 및 유효해야 하며 양식이 제대로 작동해야 합니다. 기본적으로 메시지를 분석할 때 기본 제공 **[!UICONTROL Unsubscription link approval]** [유형화 규칙](../../automation/campaign-opt/control-rules.md)이(가) 옵트아웃 링크가 포함되어 있는지 확인하고 누락된 경우 경고를 생성합니다.

이 섹션](../send/personalization-blocks.md)에서 옵트아웃 링크 [을(를) 삽입하는 방법을 알아봅니다.

+++ **이 모범 사례 적용**

사람의 오류는 항상 가능하므로 전송할 때마다 옵트아웃 링크가 올바르게 작동하는지 확인하십시오. 예를 들어 증명을 보낼 때 링크가 유효한지, 양식이 온라인 상태인지, `No longer contact this recipient ` 필드가 `Yes`(으)로 변경되었는지 확인합니다.

+++

### 이메일 크기 {#email-size-check}

성능 또는 게재 가능성 문제를 방지하기 위해 이메일의 권장 최대 크기는 약 **35KB**&#x200B;입니다. 메시지 크기를 확인하려면 **[!UICONTROL Preview]** 탭을 탐색하고 테스트 프로필을 선택하십시오. 생성되면 메시지 크기가 오른쪽 상단 모서리에 표시됩니다.


+++ **모범 사례 몇 가지 읽기**

* 중복 또는 사용하지 않는 스타일 제거

* 이메일 콘텐츠 일부를 랜딩 페이지로 이동

* 코드 축소

최종 전송 전에 모든 변경 사항을 테스트해야 합니다.

+++


### SMS 길이 {#sms-length-check}

기본적으로 SMS의 문자 수는 GSM(이동통신 글로벌 시스템) 표준을 충족합니다. GSM 인코딩을 사용하는 SMS 메시지는 SMS당 160자, 또는 여러 부분으로 나누어 전송되는 메시지의 경우 153자로 제한됩니다.


+++ **모범 사례 몇 가지 읽기**

* SMS 메시지의 모든 문자를 그대로 유지하려면 적절한 이름을 변경하지 마십시오(예: 음역을 활성화하지 마십시오).

* 그러나 SMS 메시지에 GSM 표준에서 고려하지 않는 문자가 많이 포함된 경우 음역을 활성화하여 메시지 전송 비용을 제한하십시오. 자세한 내용은 [이 섹션](../send/sms/smpp-external-account.md#smpp-transliteration)을 참조하세요.

* GSM 표준에서 고려하지 않는 SMS 문자를 다른 문자로 바꾸는 SMS 음역을 적용할 수 있습니다. SMS 메시지의 콘텐츠에 개인화 필드를 삽입하면 GSM 인코딩에서 고려하지 않는 문자가 들어갈 수 있습니다. Campaign 관리자는 해당 **[!UICONTROL External account]**&#x200B;의 SMPP 채널 설정 탭에서 해당 상자를 선택하여 문자 변환을 활성화할 수 있습니다. [자세히 알아보기](../send/sms/smpp-external-account.md#smpp-transliteration)

+++

### 첨부 파일 방지

첨부 파일은 특히 대량으로 전송되는 경우 맬웨어의 확산에 가장 일반적인 벡터 중 하나로 유지됩니다. 문서에 첨부하는 대신 보안 링크를 포함하십시오. 이렇게 하면 의도하지 않은 재배포를 방지하기 위해 추가 보안 계층을 보장하고 메시지 크기 또는 보안상의 이유로 인바운드 이메일 게이트웨이에서 메시지가 거부되는 가능성을 크게 줄일 수 있습니다.

<!--
## Work on formatting {#formatting}

To avoid common formatting errors, check the following elements:

* Correct **date formatting**: Adobe Campaign provides date formatting functions for the JavaScript templates and XSL stylesheets. [Learn more](formatting.md#date-display)

* Usage of **authorized characters** in emails: the list of valid characters for email addresses is defined in the "XtkEmail_Characters" option. Learn how to access Campaign options [in this section](../../installation/using/configuring-campaign-options.md). To correctly handle special characters, Adobe Campaign needs to be installed in Unicode. 

* Configuration of **Email Authentication**: make sure that the email headers contain the DKIM signature. DKIM (Domain Keys Identified Mail) authentication allows the receiving email server to verify that a message was indeed sent by the person or entity it claims it was sent by, and whether the message content was altered in between the time it was originally sent (and DKIM "signed") and the time it was received. This standard typically uses the domain in the From or Sender header. For more on this, refer to the [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).-->

## 이미지 관리 {#manage-images}

다음은 이메일 마케팅 캠페인에 대한 이미지를 최적화하기 위한 몇 가지 특정 지침입니다.

### 이미지 차단 방지 {#image-blocking}

일부 이메일 클라이언트는 기본적으로 이미지를 차단하며, 사용자는 설정을 변경하여 데이터 사용 시 저장할 이미지를 차단할 수 있습니다.  따라서 이미지를 다운로드하지 않으면 전체 메시지가 손실될 수 있습니다.

+++ 이를 방지하기 위해 이러한 모범 사례를 적용할 수 있습니다

* 전체 이미지 기반 이메일을 사용하지 마십시오. 이미지 및 텍스트와 콘텐츠의 균형을 맞추십시오.

* 이미지에 텍스트가 포함되어야 하는 경우에는 대체 및 제목 텍스트를 사용하여 메시지가 전달되는지 확인하십시오. 대체/제목 텍스트의 스타일을 지정하여 모양을 개선합니다.

* 일부 이메일 클라이언트에서는 배경 이미지를 지원하지 않으므로 배경 이미지를 사용하지 마십시오.
+++

### 이미지 반응형 만들기 {#responsive-images}

모든 컨텍스트 및 장치에서 이미지를 볼 수 있도록 반응형 및 크기 조정할 수 있도록 하십시오. 빌드하는 데 시간이 더 오래 걸리기 때문에 비용에 영향을 줄 수 있습니다.

### 절대 이미지 참조 사용 {#absolute-images}

외부에서 액세스할 수 있으려면 캠페인에 연결된 이메일 및 공개 리소스에 사용된 이미지가 외부에서 액세스할 수 있는 서버에 있어야 합니다.

* 게재 도우미에서 이미지가 포함된 HTML 페이지를 가져오거나 **[!UICONTROL Image]** 아이콘을 통해 HTML 편집기를 사용하여 직접 이미지를 삽입할 수 있습니다.

* 이미지가 표시되지 않으면 서버에서 사용할 수 있는지 확인하십시오. 이렇게 하려면 게재의 **Source** 탭으로 이동합니다. 이미지를 찾아 웹 브라우저에서 각 이미지의 URL을 복사하여 붙여넣습니다. 이미지가 표시되지 않으면 IT 관리자 또는 게재 콘텐츠를 제공하는 서드파티 공급업체에 문의하십시오.

### 메시지 미리 보기 및 테스트 {#preview-msg}

Adobe은 메시지를 미리 보고 개인화와 수신자가 게재를 보는 방법을 확인할 것을 권장합니다.

게재 도우미에서 **[!UICONTROL Preview]** 하위 탭을 사용하면 수신자에 대한 각 콘텐츠의 렌더링을 볼 수 있습니다. 개인화 필드 및 컨텐츠의 조건부 요소는 선택한 프로필에 대한 해당 정보로 대체됩니다. [자세히 알아보기](../send/preview-and-proof.md).


<!--
*  An automatic anti-spam checking is performed during each preview. In the **[!UICONTROL Preview]** sub-tab, check [SpamAssassin](spamassassin.md) spam scoring.  Click **[!UICONTROL More...]** to find out more about the warning.  Before doing so, make sure SpamAssassin is correctly installed and configured on the Adobe Campaign application server. [Learn more](../../installation/using/configuring-spamassassin.md)
-->

## 적합한 대상자 정의 {#define-the-right-audience}

타겟팅된 모집단은 중요합니다. 목록을 신중하게 작성하고, 인기 있는 이메일 클라이언트 및 모바일 디바이스에서 이메일을 테스트하고, 이메일 목록이 최신 상태인지 확인합니다(알 수 없거나 오래된 주소는 없음). 전체 유효성 검사 주기를 설정하는 데 도움이 되는 증명을 보낼 수도 있습니다. [이 섹션](../audiences/gs-audiences.md)에서 대상자에 대해 자세히 알아보십시오.

### 적합한 대상 타기팅 {#target-the-right-audience}

콘텐츠를 준비한 후에는 메시지를 받을 사용자를 신중하게 정의해야 합니다.

게재를 성공적으로 수행하려면 가장 관련성이 높은 개인화된 콘텐츠를 적절한 수신자에게 전송해야 합니다. Adobe Campaign을 사용하면 가장 정확한 대상을 작성할 수 있습니다. 이전 게재에서 링크를 클릭한 경우 나이, 현지화, 구입한 항목 등에 따라 수신자를 선택할 수 있습니다. Adobe Campaign을 사용하면 테스트 프로필, 컨트롤 그룹 및 시드 주소를 정의하여 타겟이 올바른지 확인할 수도 있습니다.

### 대상 매핑 {#target-mappings}

Campaign에서 기본적으로 게재 템플릿은 **받는 사람**&#x200B;을(를) 대상으로 합니다. Adobe Campaign은 게재에 대한 다른 타겟 매핑을 제공하며, 필요에 따라 변경할 수 있습니다. 예를 들어 소셜 네트워크를 통해 프로필이 수집된 방문자 또는 정보 서비스를 구독한 방문자에게 를 제공할 수 있습니다.

이 매핑은 [이 섹션](../audiences/target-mappings.md)에 표시됩니다.

### 외부 수신자 {#external-recipients}

데이터베이스에 저장되지 않고 외부 파일에 저장된 수신자에게 전달할 수 있습니다. 자세한 내용은 [이 섹션](create-message.md#select-external-recipients-selecting-external-recipients)을 참조하세요.

<!--
### Send to your subscribers {#send-to-subscribers}

To send messages to the subscribers of a newsletter, you can directly target the subscribers to the corresponding information service. Learn more [in this section](../audiences/).-->

### 수신자 테스트 {#test-recipients-seed-addresses}

게재를 테스트하려면 주요 타겟에게 보내기 전에 증명을 사용하십시오.

적절한 증명 수신자를 선택해야 합니다. 메시지 양식 및 내용의 유효성을 검사하기 때문입니다. 증명 수신자를 정의하는 단계는 [이 섹션](create-message.md#select-the-recipients-of-proof-messages-select-the-proof-target)에 나와 있습니다.


### 주소 중복 제거 {#deduplicate-addresses}

중복 이메일 주소는 타겟에 영향을 줄 수 있으므로 피하는 것이 중요합니다.

* 대상이 분할될 때 동일한 메시지를 두 번 이상 보낼 수 있습니다.

* 메시지를 받은 후 수신자가 구독을 취소해도 중복 프로필은 향후 메시지를 계속 수신합니다.

주소 중복을 제거하면 전송 평판이 보호되며 격리도 잘 관리됩니다.

**관련 항목:**

* [중복 제거 활동](../../automation/workflow/deduplication.md).
* [사용 사례: 중복 제거 작업의 병합 기능을 사용](../../automation/workflow/deduplication-merge.md).


## 보내기 전에 모든 확인 수행 {#perform-all-checks}

메시지가 준비되면 모든 디바이스에서 해당 콘텐츠가 올바르게 표시되고 잘못된 개인화 또는 링크가 끊어지는 등의 오류가 없는지 확인합니다. 메시지를 보내기 전에 매개 변수 및 구성이 게재와 일치하는지 확인하십시오.

게재 유효성 검사 단계는 [이 섹션](../send/preview-and-proof.md)에 표시됩니다.

<!--
### Inbox rendering {#inbox-and-email-rendering}

Inbox rendering enables you to preview your messages on major email clients, scan content and reputation, discover how recipients are reading messages.

**Tips**:

* You can view the sent message in the different contexts in which it may be received: webmail, message service, mobile, etc.

* Inbox rendering capabilities are crucial to identifying whether your email campaigns successfully make it past the filters of major ISPs (Internet Service Providers) and webmail services. Such tools send a pre-flight copy of an email to a network of test inboxes, so you can see how the message will display, or render, across these services. They may also include reports and code correction options that help you quickly identify and make fixes that improve deliverability.

Learn more [in this section](inbox-rendering.md).-->

### 증명 메시지 {#proof-messages}

증명을 보내면 옵트아웃 링크, 미러 페이지 및 기타 링크를 확인하고, 메시지의 유효성을 검사하고, 이미지가 표시되는지 확인하고, 가능한 오류를 감지하는 등의 작업을 수행할 수 있습니다. 다른 장치에서 디자인과 렌더링을 확인할 수도 있습니다.

<!--
### Set up A/B testing deliveries {#a-b-testing-deliveries}

If you have several contents for an email delivery, you can use A/B testing to find out which version will have the biggest impact on the targeted population.

**Tips**:

* Send the different versions to some of your recipients

* Select the one with the highest success rate and send it to the rest of your target

Learn more [in this section](get-started-a-b-testing.md).-->

### 메시지가 전달되었는지 확인합니다. {#make-sure-your-message-is-delivered}

마지막 단계로, 기회를 극대화하고 Adobe Campaign의 기능을 활용하여 메시지가 관련 수신자에게 실제로 전달되도록 하십시오.

#### 유효성 검사 프로세스 진행

Adobe Campaign 연산자 및 그룹을 포함하는 전체 유효성 검사 프로세스를 정의하여 대상과 메시지 콘텐츠의 유효성을 모두 검사할 수 있습니다. 이를 통해 타겟팅, 콘텐츠, 예산, 추출 및 증명 전송과 같은 캠페인의 다양한 프로세스를 완벽하게 모니터링하고 제어할 수 있습니다. 사용자는 권한에 따라 알림을 받고 증명을 받으며 메시지를 확인 또는 거부할 수 있습니다. 자세한 내용은 [이 섹션](../../automation/campaigns/marketing-campaign-approval.md)을 참조하세요.

#### 예약된 일괄 처리 사용

웨이브를 사용하여 전송되는 볼륨을 점진적으로 늘릴 수 있습니다. 이렇게 하면 메시지가 스팸으로 표시되거나 하루에 메시지 수를 제한하려는 경우를 방지할 수 있습니다. 웨이브를 사용하여 동시에 대량의 메시지를 전송하는 대신 게재를 여러 배치로 나눌 수 있습니다. 자세한 내용은 [이 섹션](../send/configure-and-send.md#sending-using-multiple-waves)을 참조하세요.

#### 메시지 우선 순위 지정

우선 순위 수준을 입력하여 게재의 전송 순서를 설정할 수 있습니다. 방법은 다음과 같습니다.

1. 게재 속성을 편집하고 **[!UICONTROL Delivery]** 탭을 선택합니다.

1. **[!UICONTROL Very low]**&#x200B;에서 **[!UICONTROL Very high]** 사이의 범위에서 게재 우선 순위 수준을 정의합니다.

>[!NOTE]
>
>게재 내에서 메시지를 보내는 순서를 정의할 수 없습니다.

<!--
#### Setup IP Affinities

To better control the outbound SMTP traffic, you can manage affinities by defining which specific IP addresses can be used for each affinity. This lets you restrict the number of emails for specific deliveries towards machines or output addresses. For example, you can use one affinity per country or sub-domain. You can then create one typology per country and link each affinity to the corresponding typology.

You can:

* Define the IP affinities in the serverConf.xml configuration file. [Learn more](../../installation/using/configuring-campaign-server.md#managing-outbound-smtp-traffic-with-affinities)

* For each IPAffinity element, declare the IP addresses that can be used. [Learn more](../../installation/using/email-deliverability.md#list-of-ip-addresses-to-use)

* In the [typology](../../campaign-opt/using/about-campaign-typologies.md) of your choice, use the **[!UICONTROL Managing affinities with IP addresses]** field to link deliveries to the delivery server (MTA) which manages the said affinity. [Learn more](../../campaign-opt/using/applying-rules.md#control-outgoing-smtp-traffic).

* Once the email is sent, check the header to verify which IP address the delivery was sent from. Your email administrator should help you obtain the header information.

* For SMS deliveries, make sure that the SMS channel has a dedicated affinity limited to **one** application server container. [Learn more](../../installation/using/configure-delivery-settings.md#managing-outbound-smtp-traffic-with-affinities)

>[!NOTE]
>
>Most of these steps can only be performed by an expert user.-->

#### 유형화 사용

유형화 규칙을 사용하여 특정 기준에 따라 대상의 일부를 제외할 수 있습니다. 따라서 회사 커뮤니케이션 정책을 준수하면서 고객의 요구 사항과 기대치에 가장 적합한 메시지를 보낼 수 있습니다. 예를 들어 뉴스레터의 대상에서 미성년인 수신자를 필터링할 수 있습니다. 자세한 내용은 [이 예제](../../automation/campaign-opt/filtering-rules.md)를 참조하세요.


## 추적 및 모니터링 {#track-and-monitor}

**보내기** 단추를 클릭했습니까? 무슨 일이 일어나는지 봅시다. 게재가 전송되면 Adobe Campaign을 통해 전송된 메시지를 추적하고 수신자가 게재에 어떻게 반응하는지 확인할 수 있습니다. 이를 통해 향후 전송을 개선하고 다음 캠페인을 최적화할 수 있습니다.

## 게재 모니터링 {#monitoring-deliveries}

캠페인을 제어하려면 메시지가 실제로 수신자에게 전달되었는지 확인해야 합니다.

Campaign 게재 대시보드에서 처리된 메시지 및 게재 감사 로그를 확인할 수 있습니다. 게재 로그에서 메시지 상태를 제어할 수도 있습니다.

[Campaign Classic v7 설명서에서 게재 모니터링에 대해 자세히 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target="_blank"}


## 동작 추적 {#track-behaviour}

수신자의 동작을 더 잘 알기 위해 수신, 열기, 링크 클릭, 구독 취소 등 수신자가 게재에 어떻게 반응하는지를 추적할 수 있습니다. Campaign에서 이 정보는 게재의 대상인 수신자의 **추적** 탭과 게재의 추적 탭에 표시됩니다.

메시지 추적은 기본적으로 활성화되어 있습니다. URL을 구성하려면 게재 도우미의 아래 섹션에서 URL 표시 옵션을 선택합니다. 메시지의 각 URL에 대해 추적을 활성화할지 여부를 선택할 수 있습니다.


[Campaign Classic v7 설명서에서 추적 기능에 대해 자세히 알아보세요](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html#sending-messages){target="_blank"}
