---
title: 초기 Campaign v8 릴리스 정보
description: 초기 Campaign v8 릴리스
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 9ce5acd97e077105316c81029e3ccbc6fa4389dc
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 86%

---

# 초기 릴리스 정보 {#e-new-release}

이 페이지에서는 다음 Campaign v8 릴리스에 포함된 개선 사항 및 문제 해결에 대해 설명합니다. **아래의 얼리 릴리스 정보는 릴리스 예정일까지 사전 예고 없이 변경될 수 있습니다**. 링크, 화면 및 업데이트된 설명서는 릴리스 일자에 [릴리스 정보](release-notes.md)에 게시됩니다.


## 릴리스 8.7.2 {#release-8-7-2}

_2024년 9월 3일_

>[!AVAILABILITY]
>
>이 릴리스는 **제한 공개**(LA) 상태입니다. 이는 **Adobe Campaign Standard에서 Adobe Campaign v8**&#x200B;로 마이그레이션하는 고객으로 제한되며 다른 환경에는 배포할 수 없습니다.
>
>Campaign Standard 사용자가 Campaign v8로 전환하는 경우 [Campaign v8 웹 사용자 인터페이스 설명서](https://experienceleague.adobe.com/docs/campaign-web/v8/start/acs-migration.html?lang=ko){target="_blank"}에서 이 전환에 대해 자세히 알아보세요.

### 새로운 기능 {#new-8-7-2}

* **새로운 SMS 전송 커넥터** - SMS 전송 커넥터가 최신화되고 개선되었습니다. 송수신기 모드 SMPP 연결 및 영구 SMPP 연결을 사용할 수 있으며 Adobe Campaign Standard에서 전환할 때 환경에 대해 보다 나은 호환성을 보장합니다. 이제 모든 새 SMS 구현에 새 SMS 외부 계정을 사용할 수 있습니다. 기존 구현은 여전히 지원되지만 새로운 최신 및 확장 커넥터로 이동하는 것이 좋습니다.

* **리치 푸시 알림(GA)** - 이제 리치 푸시 알림을 전송할 수 있습니다. 리치 푸시 알림은 이미지, 대화형 버튼 또는 기타 리치 미디어 콘텐츠와 같은 멀티미디어 요소를 통합하여 단순한 문자 메시지를 뛰어 넘는 향상된 형태의 모바일 알림입니다. 이번 버전에서는 이제 iOS 및 Android 앱에서 리치 푸시 알림을 위한 템플릿 세트를 사용할 수 있습니다. [자세히 보기](../send/rich-push-android.md).

* **브랜딩** - 이제 SMS 및 다이렉트 메일을 포함한 모든 채널에서 브랜딩 옵션을 사용할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=ko){target="_blank"}


### 수정 사항 {#fixes-8-7-2}

이 릴리스에서는 다음 문제가 해결되었습니다.

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328.
