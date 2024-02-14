---
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 92fe7c41047aafd26cca70a547025a3eff73e398
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 16%

---

# 최신 릴리스{#latest-release}

Adobe Campaign은 정기적으로 업데이트됩니다. 이러한 정기 업데이트 빈도는 최신 업데이트를 직접 경험해 보고 사용 환경을 안전하게 지키며 Adobe 제품 경험을 향상시키는 것을 목표로 합니다. Adobe은 모든 고객에게 최신 버전으로 업그레이드할 것을 강력히 권장합니다. Campaign 버전 및 권장 사항에 대해 자세히 알아보기 [이 페이지에서](upgrades.md).

Managed Cloud Service 사용자는 Adobe에 의해 모든 새 버전으로 인스턴스가 업그레이드됩니다. Adobe이 귀하에게 연락하여 환경을 업그레이드합니다. Campaign 클라이언트 콘솔 **은(는) 동일한 버전으로 업그레이드해야 합니다.** Campaign 서버로. 클라이언트 콘솔을 업그레이드하는 방법: [페이지](../start/connect.md#upgrade-ac-console).

또한 고객은 다음에 나열된 시스템에서 지원되는 최신 버전을 사용하고 있는지 확인하십시오. [호환성 매트릭스](compatibility-matrix.md).


## 릴리스 8.6.1 {#release-8-6-1}

_2024년 2월 14일_


### 새로운 기능 {#new-8-6-1}

* 이번 릴리스부터 새로운 기능에 액세스할 수 있습니다. **Campaign 웹 사용자 인터페이스**, 중앙 Adobe Experience Cloud 환경을 통해 사용할 수 있습니다. Experience Cloud는 Adobe의 디지털 마케팅 애플리케이션, 제품 및 서비스 통합 제품군입니다. 직관적인 인터페이스에서 클라우드 애플리케이션, 제품 기능, 서비스에 빠르게 액세스할 수 있습니다. Adobe Experience Cloud에 연결하고 Adobe Campaign 웹 인터페이스에 액세스하는 방법에 대해 알아봅니다 [이 페이지에서](campaign-ui.md#ac-web-ui).


* Adobe Campaign v8은 이제 와 통합됩니다. **Adobe Experience Manager as a Cloud Service**, Adobe Campaign 웹 사용자 인터페이스를 통해서만 작성 가능 [자세히 알아보기](../connect/ac-aem.md)

* 이제 다음을 사용할 수 있습니다. **Adobe Experience Manager Assets 라이브러리** Adobe Campaign 인스턴스에 Adobe Experience Cloud 패키지와 통합이 설치된 경우에도 Experience Cloud Assets와 함께 사용할 수 있습니다.[자세히 알아보기](../connect/ac-aem.md#assets-library)

### 일반 개선 사항 {#improvements-8-6-1}

* Campaign v8.6은 다음을 위한 향상된 처리량을 제공합니다. **이메일 게재 추적 표시기**. 최적화된 프로세스로 수집 및 계산 시간 추적이 감소하며 게재 키 지표를 훨씬 빠르게 확인할 수 있습니다.


### 게재 기능 업데이트 {#deliverability-8-6-1}

* 2024년 2월까지 Google 또는 Yahoo!를 통해 5,000개 이상의 이메일 메시지를 보내는 모든 회사 도메인 기반 메시지 인증 보고 및 적합성(DMARC)이라고 하는 인증 기술을 사용해야 합니다. Adobe Campaign에서 사용하는 모든 하위 도메인에 대해 DMARC 레코드를 설정해야 합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=ko){target="_blank"}

* 2024년 6월 1일부터 Google 및 Yahoo! 발신자는 원클릭 목록 구독 취소를 준수해야 합니다. 이제 Adobe Campaign에서 이 옵션을 지원합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#one-click-list-unsubscribe){target="_blank"}


### 수정 사항 {#fixes-8-6-1}

이 릴리스에는 NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059-58637, NEO-55197, NEO-52542, NEO 50488 47789