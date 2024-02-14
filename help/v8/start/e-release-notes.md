---
title: 초기 Campaign v8 릴리스 정보
description: 초기 Campaign v8 릴리스
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: eae364fb3d082c91022fee6bf29802c9eb6dfcf5
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 22%

---

# 초기 릴리스 정보 {#e-new-release}

이 페이지에서는 다음 Campaign v8 릴리스에 포함된 개선 사항 및 문제 해결에 대해 설명합니다. 이 내용은 릴리스 일자까지 사전 예고 없이 변경될 수 있습니다. 공식 릴리스 정보는 이 [페이지](../start/release-notes.md)에서 확인할 수 있습니다.

## 릴리스 8.6.1 {#release-8-6-1}

_2024년 2월 14일_


### 새로운 기능 {#new-8-6-1}

* 이번 릴리스부터 새로운 기능에 액세스할 수 있습니다. **Campaign 웹 사용자 인터페이스**, 중앙 Adobe Experience Cloud 환경을 통해 사용할 수 있습니다. Experience Cloud는 Adobe의 디지털 마케팅 애플리케이션, 제품 및 서비스 통합 제품군입니다. 직관적인 인터페이스에서 클라우드 애플리케이션, 제품 기능, 서비스에 빠르게 액세스할 수 있습니다. Adobe Experience Cloud에 연결하고 Adobe Campaign 웹 인터페이스에 액세스하는 방법에 대해 알아봅니다 [이 페이지에서](campaign-ui.md#ac-web-ui).

* 이제 클라이언트 콘솔의 32비트 버전은 더 이상 사용되지 않습니다. 8.6부터 클라이언트 콘솔은 64비트로만 사용할 수 있습니다. 클라이언트 콘솔의 64비트 버전으로 원활하게 업그레이드됩니다. 운영 체제를 업그레이드하는 자세한 방법은 [기술 정보](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=ko)를 참조하십시오.


### 일반 개선 사항 {#improvements-8-6-1}

* Campaign v8.6은 다음을 위한 향상된 처리량을 제공합니다. **이메일 게재 추적 표시기**. 최적화된 프로세스로 수집 및 계산 시간 추적이 감소하며 게재 키 지표를 훨씬 빠르게 확인할 수 있습니다.

* 이제 Campaign v8 인스턴스를 Azure synapse 외부 데이터베이스에 연결할 수 있습니다. 이 연결은 새 외부 계정을 통해 관리됩니다.

* Adobe Campaign v8은 이제 와 통합됩니다. **Adobe Experience Manager as a Cloud Service**, Adobe Campaign 웹 사용자 인터페이스를 통해서만 작성 가능

* 이제 다음을 사용할 수 있습니다. **Adobe Experience Manager Assets 라이브러리** Experience Cloud 에셋과 함께 **Adobe Experience Cloud과 통합** 패키지가 Adobe Campaign 인스턴스에 설치됩니다.

* 더 이상 클라이언트 콘솔에서 연산자를 만들 수 없습니다. 이제 Admin Console을 사용해야 합니다. [자세히 알아보기](../start/gs-permissions.md)

* 보안을 최적화하기 위해 여러 타사 도구가 업데이트되었습니다.

### 게재 기능 업데이트 {#deliverability-8-6-1}

* 2024년 2월까지 Google 또는 Yahoo!를 통해 5,000개 이상의 이메일 메시지를 보내는 모든 회사 도메인 기반 메시지 인증 보고 및 적합성(DMARC)이라고 하는 인증 기술을 사용해야 합니다. Adobe Campaign에서 사용하는 모든 하위 도메인에 대해 DMARC 레코드를 설정해야 합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=ko){target="_blank"}

* 2024년 6월 1일부터 Google 및 Yahoo! 발신자는 원클릭 목록 구독 취소를 준수해야 합니다. 이제 Adobe Campaign에서 이 옵션을 지원합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#one-click-list-unsubscribe){target="_blank"}


### 수정 사항 {#fixes-8-6-1}

이 릴리스에는 NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059-58637, NEO-55197, NEO-52542, NEO 50488 47789