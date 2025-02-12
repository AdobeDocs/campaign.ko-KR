---
title: Campaign v8(콘솔) 2025 릴리스 정보
description: 2025 Campaign v8 릴리스의 기능 및 개선 사항 목록
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: 82622a4517356eaba1f7eba23d4b3050d8ca37c9
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 90%

---

# 2025 릴리스 정보 {#2025-rn}

이 페이지에는 **2025 Campaign v8 릴리스**&#x200B;의 새로운 기능, 개선 사항 및 수정 사항이 나와 있습니다. 최신 릴리스는 [이 페이지](release-notes.md)에 나열되어 있습니다.

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
