---
title: Campaign v8(콘솔) 2023 릴리스 정보
description: 2023 Campaign v8 릴리스의 기능 및 개선 사항 목록
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
source-git-commit: 69ef7e81d5fc0f5cf0dc74fa16d970ef89607331
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 77%

---

# 2024 릴리스 정보 {#2024-rn}

이 페이지에는 **2024 Campaign v8 릴리스**&#x200B;의 새로운 기능, 개선 사항 및 수정 사항이 나와 있습니다.


## 릴리스 8.6.2 {#release-8-6-2}

_2024년 2월 23일_

### 수정 사항 {#fixes-8-6-2}

이 릴리스에서는 다음 문제가 해결되었습니다.

* 중간 소싱 인스턴스에서 발생할 수 있는 성능 문제를 해결했습니다(NEO-72595).

## 릴리스 8.6.1 {#release-8-6-1}

_2024년 2월 14일_

### 새로운 기능 {#new-8-6-1}

* 이번 릴리스부터 중앙 Adobe Experience Cloud 환경을 통해 사용할 수 있는 새로운 **Campaign Web 사용자 인터페이스**&#x200B;에 액세스할 수 있습니다. Experience Cloud는 Adobe의 디지털 마케팅 애플리케이션, 제품 및 서비스 통합 제품군입니다. 직관적인 인터페이스에서 클라우드 애플리케이션, 제품 기능, 서비스에 빠르게 액세스할 수 있습니다. [이 페이지에서](campaign-ui.md#ac-web-ui) Adobe Experience Cloud에 연결하여 Adobe Campaign Web 인터페이스에 액세스하는 방법을 알아보십시오.


* Adobe Campaign v8은 이제 **Adobe Experience Manager as a Cloud Service**&#x200B;와 통합되어 Adobe Campaign Web 사용자 인터페이스를 통해서만 작성이 가능합니다. [자세히 알아보기](../connect/ac-aem.md)

* 이제 Adobe Campaign 인스턴스에 Adobe Experience Cloud 통합 패키지가 설치되어 있어도 Experience Cloud Assets과 함께 **Adobe Experience Manager Assets 라이브러리**&#x200B;를 사용할 수 있습니다. [자세히 알아보기](../connect/ac-aem.md#assets-library)

### 일반 개선 사항 {#improvements-8-6-1}

* Campaign v8.6은 **이메일 게재 추적 지표**&#x200B;에 대한 처리량이 향상되었습니다. 최적화된 프로세스로 추적 수집 및 컴퓨팅 시간이 단축되고 게재 주요 지표를 훨씬 빠르게 확인할 수 있습니다.


### 전달성 업데이트 {#deliverability-8-6-1}

* 2024년 2월까지 Google 또는 Yahoo!를 통해 5,000개가 넘는 이메일 메시지를 보내는 모든 회사는 도메인 기반 메시지 인증 보고 및 적합성(DMARC)이라는 인증 기술을 사용하기 시작해야 합니다. Adobe Campaign에서 사용하는 모든 하위 도메인에 대해 DMARC 레코드를 설정해야 합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=ko){target="_blank"}

* 2024년 6월 1일부터 Google 및 Yahoo!는 발신자에게 원클릭 목록-구독 취소를 준수하도록 요구할 것입니다. 이제 Adobe Campaign에서 이 옵션을 지원합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=ko#one-click-list-unsubscribe){target="_blank"}


### 수정 사항 {#fixes-8-6-1}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059 58637 55197 52542 50488 47789
