---
product: campaign
title: Campaign에서 게재 기능 시작
description: 전달성 모범 사례 학습
feature: Deliverability
role: User
version: Campaign v8, Campaign Classic v7
exl-id: f301b34c-244c-4279-b23f-8224ea8eedbe
source-git-commit: 96f1518f252be7ffa27ba8157b8a090bf4d4510d
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 7%

---

# 전달성의 정의{#about-deliverability}

전달성을 사용하면 캠페인이 바운스 없이 또는 스팸으로 표시되지 않고 수신자의 받은 편지함에 도달했는지 측정할 수 있습니다. [전달성이 중요한 이유를 알아보세요](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html?lang=ko#why-deliverability-matters){target="_blank"}.

더 정확히 말해, 이메일 전달성이란 메시지가 개인 이메일 주소를 통해, 짧은 시간 내에, 그리고 콘텐츠와 형식 측면에서 예상되는 품질로 대상에 도달할 수 있는지를 결정하는 일련의 특징들을 말합니다.

전달성의 의미에 대해 자세히 알아보고 주요 전달성 용어, 개념 및 접근 방식에 대한 자세한 내용은 [Adobe 전달성 모범 사례 안내서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=ko){target="_blank"}를 참조하세요.

## 게재 능력을 향상시키는 방법 {#deliverability-key-points}

전달성 문제는 일반적으로 인터넷 서비스 공급자 및 메일 서버 관리자가 구현하는 스팸 방지 측정과 연결됩니다.

* 성공적인 이메일 마케팅 캠페인을 디자인하는 방법에 대한 일반적인 권장 사항은 [전달성 전략 및 정의](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html?lang=ko){target="_blank"}를 참조하십시오.

* Adobe Campaign 이메일의 전달성을 최적화하는 방법에 대한 보다 구체적인 권장 사항을 알려면 Adobe에서는 이 섹션에 나열된 모범 사례를 사용하는 것이 좋습니다.

>[!NOTE]
>
>ISP는 스팸 발신자로부터 고객을 보호하기 위해 새로운 정교한 필터링 기법을 지속적으로 개발해야 하므로 이메일 전달성은 항상 변화하는 기준과 규칙으로 특징지어집니다. 정기적으로 업데이트되는 [Adobe 전달성 모범 사례 안내서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=ko){target="_blank"}를 참조하세요.

### 전달률

전달률은 배달된 메시지 수와 비교하여 수신자의 받은 편지함에 도달한 메시지 수입니다. 게재 능력을 개선하기 위해 이 속도를 높이는 작업을 할 수 있습니다.

Adobe Campaign의 경우 전달률은 여러 가지 요인에 따라 다릅니다. 특히

* 인스턴스의 올바른 구성: 도움이 필요하면 Adobe 담당자에게 문의하십시오.
* 올바른 네트워크 구성: [도메인 설정 및 전략](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=ko#domain-setup-and-strategy){target="_blank"}을 참조하세요.
* IP 주소 신뢰도: [IP 전략](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=ko#ip-strategy){target="_blank"}을 참조하세요.
* 낮은 [컴플레인](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html?lang=ko){target="_blank"} 및 [하드 바운스](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html?lang=ko#hard-bounces){target="_blank"} 비율.
* 메시지 내용: [전자 메일 내용 제어](control-message-content.md)를 참조하세요.
* 메시지 인증(SPF, DKIM, DMARC): [이 섹션](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=ko#authentication){target="_blank"}을 참조하세요.
* 보낸 사람의 신뢰도: 기본 ISP에서 보낸 사람의 신뢰도를 평가하는 방법을 알아보려면 [이 섹션](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html?lang=ko){target="_blank"}을 참조하세요.

## Campaign 전달성 도구 {#deliverability-tools}

<!--Adobe Campaign provides a number of tools designed to ensure optimal deliverability.-->
Adobe Campaign은 플랫폼의 전달성 성능을 추적하고 개선하는 여러 도구를 제공합니다. 이 페이지에서는 Campaign 사용 시 전달성을 최적화하기 위해 염두에 두어야 하는 주요 원칙도 강조 표시합니다.

### 메시지를 주의 깊게 작성하세요

메시지를 구성, 디자인 및 테스트할 때 아래 나열된 섹션에 설명된 모범 사례를 따라야 합니다. Adobe Campaign에서 제공하는 모든 기능을 활용하면 전달성을 향상시킬 수 있습니다.

* [게재 모범 사례](../start/delivery-best-practices.md)
* [이메일 콘텐츠 제어](control-message-content.md)
* [받은 편지함 렌더링](inbox-rendering.md)
* [증명 보내기](preview-and-proof.md#send-proofs)

### 이중 옵트인을 통해 동의 확인 {#double-opt-in}

Adobe은 잘못된 주소로 메시지를 보내지 않도록 하고 부적절한 커뮤니케이션을 제한하며 보낸 사람의 평판을 향상시키기 위해 이중 옵트인 메커니즘을 구현하는 것을 권장합니다. 이 방법을 사용하면 수신자가 의도적으로 구독했는지 확인할 수 있습니다.

자세한 내용은 [이중 옵트인](https://experienceleague.adobe.com/ko/docs/campaign-classic/using/designing-content/web-forms/use-cases-web-forms){target=_blank}을 사용하여 구독 양식 만들기를 참조하십시오.

고객으로부터 데이터를 수집하는 모범 사례에 대한 자세한 내용은 [Adobe 전달성 모범 사례 안내서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html?lang=ko#data-quality-and-hygiene){target="_blank"}를 참조하세요.

### 격리 관리 활용

Adobe Campaign은 지속적으로 발생하는 스팸 불만, 하드 바운스 및 소프트 바운스를 수집하는 목록을 관리합니다.

게재 가능성을 보호하기 위해 해당 목록에 있는 주소의 수신자는 이후 모든 게재에서 기본적으로 제외됩니다. 이러한 연락처로 보내면 전송 평판이 떨어질 수 있기 때문입니다.

일부 인터넷 액세스 제공 업체는 잘못된 주소의 비율이 너무 높은 경우 이메일을 자동으로 스팸으로 간주합니다. 따라서 이러한 공급자에 의해 차단 목록에 추가하다에 추가되는 것을 피할 수 있습니다.

자세한 내용은 다음 섹션을 참조하십시오.

* [게재 실패 이해](delivery-failures.md)
* [격리 관리 이해](quarantines.md)
* [차단 목록에 추가하다 방역](quarantines.md)

### 모니터링 및 보고 도구 사용

Adobe Campaign에서 제공하는 기능을 사용하여 게재 가능성을 모니터링합니다.

Adobe Campaign을 사용하면 게재 시 향상된 insight에 대한 내장된 실시간 표시기 및 보고서 세트를 통해 게재의 수행 방식을 확인할 수 있습니다.

자세한 내용은 다음 섹션을 참조하십시오.

* [게재 기능 모니터링](monitoring-deliverability.md)
* [Campaign 기본 제공 보고서 시작](../reporting/built-in-reports.md)
