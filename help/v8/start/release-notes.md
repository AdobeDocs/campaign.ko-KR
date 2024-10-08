---
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: fb7abba9009591a2757c07f584c0a7c59c6eb01a
workflow-type: ht
source-wordcount: '532'
ht-degree: 100%

---

# 최신 릴리스 {#latest-release}

Adobe Campaign은 정기적으로 업데이트됩니다. 이러한 정기 업데이트 빈도는 최신 업데이트를 직접 경험해 보고 사용 환경을 안전하게 지키며 Adobe 제품 경험을 향상시키는 것을 목표로 합니다. Adobe는 모든 고객에게 최신 버전으로 업그레이드할 것을 강력히 권장합니다. 이 페이지에는 최신 Campaign v8 릴리스(콘솔)의 최신 릴리스와 함께 새로운 기능, 개선 및 수정 사항이 나와 있습니다. [이 페이지](upgrades.md)에서 Campaign 버전 및 업데이트에 대해 자세히 알아보십시오.

Adobe는 새 버전이 나올 때마다 Managed Cloud Services 사용자의 인스턴스를 업그레이드합니다. Adobe이 귀하에게 연락하여 환경을 업그레이드합니다. Campaign 클라이언트 콘솔은 **Campaign 서버와 동일한 버전으로 업그레이드**&#x200B;되어야 합니다. [이 페이지](../start/connect.md#upgrade-ac-console)에서 클라이언트 콘솔을 업그레이드하는 방법을 알아보십시오.

또한 고객은 [호환성 매트릭스](compatibility-matrix.md)에 나열된 최신 지원 버전의 시스템을 사용하고 있는지 확인하십시오.


## 릴리스 8.7.2 {#release-8-7-2}

_2024년 9월 3일_

>[!AVAILABILITY]
>
>이 릴리스는 **제한 공개**(LA) 상태입니다. 이는 **Adobe Campaign Standard에서 Adobe Campaign v8**&#x200B;로 마이그레이션하는 고객으로 제한되며 다른 환경에는 배포할 수 없습니다.
>
>Campaign v8로 전환하는 Campaign Standard 사용자라면 [Campaign v8 웹 사용자 인터페이스 설명서](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/start/acs-migration){target="_blank"}를 통해 전환 과정을 자세히 확인할 수 있습니다.

### 새로운 기능 {#new-8-7-2}

* **새로운 SMS 전송 커넥터** - SMS 전송 커넥터가 최신화되고 개선되었습니다. 송수신기 모드 SMPP 연결 및 영구 SMPP 연결을 사용할 수 있으며 Adobe Campaign Standard에서 전환할 때 환경에 대해 보다 나은 호환성을 보장합니다. 이제 모든 새 SMS 구현에 새 SMS 외부 계정을 사용할 수 있습니다. 기존 구현도 여전히 지원하지만 새롭게 확장된 최신형 커넥터로 옮기는 것을 권장합니다. [자세히 보기](../send/sms/sms.md).

* **리치 푸시 알림(GA)** - 이제 리치 푸시 알림을 전송할 수 있습니다. 리치 푸시 알림은 이미지, 대화형 버튼 또는 기타 리치 미디어 콘텐츠와 같은 멀티미디어 요소를 통합하여 단순한 문자 메시지를 뛰어 넘는 향상된 형태의 모바일 알림입니다. 이번 버전에서는 이제 iOS 및 Android 앱에서 리치 푸시 알림을 위한 템플릿 세트를 사용할 수 있습니다. [자세히 보기](../send/rich-push-android.md).

* **브랜딩** - 이제 SMS 및 다이렉트 메일을 포함한 모든 채널에서 브랜딩 옵션을 사용할 수 있습니다. [자세히 보기](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=ko){target="_blank"}


### 수정 사항 {#fixes-8-7-2}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328.


## 릴리스 8.6.3 {#release-8-6-3}

_2024년 7월 30일_

### 새로운 기능 {#new-8-6-3}

* **리치 푸시 알림** - 이제 리치 푸시 알림을 전송할 수 있습니다. 리치 푸시 알림은 이미지, 대화형 버튼 또는 기타 리치 미디어 콘텐츠와 같은 멀티미디어 요소를 통합하여 단순한 문자 메시지를 뛰어 넘는 향상된 형태의 모바일 알림입니다. 이번 버전에서는 이제 iOS 및 Android 앱에서 리치 푸시 알림을 위한 템플릿 세트를 사용할 수 있습니다. [자세히 보기](../send/rich-push-android.md).

* 이 버전부터 서비스 계정(JWT) 자격 증명이 Adobe에 의해 더 이상 사용되지 않으며, Adobe 솔루션 및 앱과 Campaign 아웃바운드 통합이 이제 OAuth 서버 간 자격 증명을 사용합니다. [자세히 알아보기](release-notes-2024.md#change-8-7-1)

### 일반 개선 사항 {#improvements-8-6-3}

* 애플리케이션 간 모든 통신에 대한 보안을 강화하기 위해 이제 외부 API 호출에도 mTLS를 지원합니다.

### 수정 사항 {#fixes-8-6-3}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-79328, NEO-78843, NEO-77795, NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-72504, NEO-70263, NEO-67620, NEO-63197, NEO-58596, NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->
