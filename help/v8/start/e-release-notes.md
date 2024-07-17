---
title: 초기 Campaign v8 릴리스 정보
description: 초기 Campaign v8 릴리스
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 09b8ced170ff28b24713722e0a82852038053201
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 58%

---

# 초기 릴리스 정보 {#e-new-release}

이 페이지에서는 다음 Campaign v8 릴리스에 포함된 개선 사항 및 문제 해결에 대해 설명합니다. **아래의 초기 릴리스 정보는 릴리스 예정일까지 사전 예고 없이 변경될 수 있습니다**. 링크, 화면 및 업데이트된 설명서는 릴리스 일자에 [릴리스 정보](release-notes.md)에 게시됩니다.

## 릴리스 8.7.2 {#release-8-7-2}

_2024년 7월 30일 수요일_


>[!AVAILABILITY]
>
>이 릴리스는 **제한 공개**(LA) 상태입니다. 이는 **Adobe Campaign Standard에서 Adobe Campaign v8**&#x200B;로 마이그레이션하는 고객으로 제한되며 다른 환경에는 배포할 수 없습니다.
>
>Campaign v8로 전환하는 Campaign Standard 사용자라면 [Campaign v8 웹 사용자 인터페이스 설명서](https://experienceleague.adobe.com/ko/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}를 통해 전환 과정을 자세히 확인할 수 있습니다.

### 새로운 기능 {#new-8-7-2}

* **새 SMS 전송 커넥터** - SMS 전송 커넥터가 현대화되고 개선되어 송수신기 모드 SMPP 연결을 사용할 수 있고 영구 SMPP 연결을 사용할 수 있으며 Adobe Campaign Standard에서 전환되는 환경에 대해 더 나은 호환성을 보장합니다. 이제 모든 새 SMS 구현에 새 SMS 외부 계정을 사용할 수 있습니다. 기존 구현은 여전히 지원되지만 새로운 최신 및 확장 커넥터로 이동하는 것이 좋습니다.

* **리치 푸시 알림(GA)** - 이제 리치 푸시 알림을 보낼 수 있습니다. 리치 푸시 알림은 이미지, 대화형 버튼 또는 기타 리치 미디어 콘텐츠와 같은 멀티미디어 요소를 통합하여 단순한 문자 메시지를 뛰어 넘는 향상된 형태의 모바일 알림입니다. 이 버전에서는 이제 iOS 및 Android 앱에서 리치 푸시 알림에 대한 템플릿 세트를 사용할 수 있습니다. [자세히 보기](../send/rich-push.md).

* **브랜딩** - 이제 SMS 및 DM을 포함한 모든 채널에 브랜딩 옵션을 사용할 수 있습니다. [자세히 보기](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=ko){target="_blank"}

<!--
### Fixes {#fixes-8-7-2}

The following issues are fixed in this release:

NEO-76592, NEO-75400, NEO-77406, NEO-77674, NEO-77899, NEO-73989, NEO-76064, NEO-76039, NEO-76040, NEO-76845, NEO-76664, NEO-76682, NEO-76663, NEO-73602, NEO-72915, NEO-78134, NEO-77000, NEO-77002, NEO-76955, NEO-76864, NEO-76926, NEO-76495, NEO-77168, NEO-41058, NEO-75581, NEO-74647, NEO-74585, NEO-74586, NEO-74831, NEO-77319, NEO-78607.-->

## 릴리스 8.6.3 {#release-8-6-3}

_2024년 7월 30일 수요일_


### 새로운 기능 {#new-8-6-3}

* **리치 푸시 알림** - 이제 리치 푸시 알림을 보낼 수 있습니다. 리치 푸시 알림은 이미지, 대화형 버튼 또는 기타 리치 미디어 콘텐츠와 같은 멀티미디어 요소를 통합하여 단순한 문자 메시지를 뛰어 넘는 향상된 형태의 모바일 알림입니다. 이 버전에서는 이제 iOS 및 Android 앱에서 리치 푸시 알림에 대한 템플릿 세트를 사용할 수 있습니다. [자세히 보기](../send/rich-push.md).

* 이 버전부터 서비스 계정(JWT) 자격 증명이 Adobe에 의해 더 이상 사용되지 않으며, Adobe 솔루션 및 앱과 Campaign 아웃바운드 통합이 이제 OAuth 서버 간 자격 증명을 사용합니다. [자세히 알아보기](release-notes.md#change-8-7-1)


### 일반 개선 사항 {#improvements-8-6-3}

* 애플리케이션 간의 모든 통신에 대한 보안을 강화하기 위해 이제 외부 API 호출에 대해 mTLS가 지원됩니다.

<!--
### Fixes {#fixes-8-7-2}

The following issues are fixed in this release:
-->