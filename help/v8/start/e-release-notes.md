---
title: 초기 Campaign v8 릴리스 정보
description: 초기 Campaign v8 릴리스
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: aadf47ccc7b014416064b7c1318cd1b35077d0fb
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 75%

---

# 초기 릴리스 정보 {#e-new-release}

이 페이지에서는 다음 Campaign v8 릴리스에 포함된 개선 사항 및 문제 해결에 대해 설명합니다. **아래의 초기 릴리스 정보는 릴리스 예정일까지 사전 예고 없이 변경될 수 있습니다**. 링크, 화면 및 업데이트된 설명서는 릴리스 일자에 [릴리스 정보](release-notes.md)에 게시됩니다.

<!--
## Release 8.7.2 {#release-8-7-2}

_July 30, 2024_


>[!AVAILABILITY]
>
>This release is in **Limited Availability** (LA). It is restricted to customers migrating **from Adobe Campaign Standard to Adobe Campaign v8**, and cannot be deployed on any other environment.
>
>As a Campaign Standard user transitioning to Campaign v8, learn more about this transition in [Campaign v8 web user interface documentation](https://experienceleague.adobe.com/en/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### New features {#new-8-7-2}

* **New SMS sending connector** - The SMS sending connector has been modernized and improved to enable transceiver mode SMPP connections, enable persistent SMPP connections, and ensure better compatibility for environments transitioning from Adobe Campaign Standard. A new SMS External account is now available for all new SMS implementations. Existing implementation are still supported, however recommendation is to move to this new modern and extended connector.

* **Rich Push Notification (GA)** - You can now send rich push notifications. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. With this version, a set of templates for rich push notifications are now available for your iOS and Android apps. [Read more](../send/rich-push.md). 

* **Branding** - Branding options are now available for all channels, including SMS and Direct mail. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html){target="_blank"}


### Fixes {#fixes-8-7-2}

The following issues are fixed in this release:

NEO-76592, NEO-75400, NEO-77406, NEO-77674, NEO-77899, NEO-73989, NEO-76064, NEO-76039, NEO-76040, NEO-76845, NEO-76664, NEO-76682, NEO-76663, NEO-73602, NEO-72915, NEO-78134, NEO-77000, NEO-77002, NEO-76955, NEO-76864, NEO-76926, NEO-76495, NEO-77168, NEO-41058, NEO-75581, NEO-74647, NEO-74585, NEO-74586, NEO-74831, NEO-77319, NEO-78607.
-->

## 릴리스 8.6.3 {#release-8-6-3}

_2024년 7월 30일 수요일_

### 새로운 기능 {#new-8-6-3}

* **리치 푸시 알림** - 이제 리치 푸시 알림을 보낼 수 있습니다. 리치 푸시 알림은 이미지, 대화형 버튼 또는 기타 리치 미디어 콘텐츠와 같은 멀티미디어 요소를 통합하여 단순한 문자 메시지를 뛰어 넘는 향상된 형태의 모바일 알림입니다. 이 버전에서는 이제 iOS 및 Android 앱에서 리치 푸시 알림에 대한 템플릿 세트를 사용할 수 있습니다. [자세히 보기](../send/rich-push.md).

* 이 버전부터 서비스 계정(JWT) 자격 증명이 Adobe에 의해 더 이상 사용되지 않으며, Adobe 솔루션 및 앱과 Campaign 아웃바운드 통합이 이제 OAuth 서버 간 자격 증명을 사용합니다. [자세히 알아보기](release-notes.md#change-8-7-1)

### 일반 개선 사항 {#improvements-8-6-3}

* 애플리케이션 간 모든 통신에 대한 보안을 강화하기 위해 이제 외부 API 호출에도 mTLS를 지원합니다.

### 수정 사항 {#fixes-8-6-3}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-72504, NEO-70263, NEO-67620, NEO-63197, NEO-58596, NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->