---
product: campaign
title: 푸시 알림 채널 예정된 변경 사항
description: 푸시 알림 채널 예정된 변경 사항
hide: true
hidefromtoc: true
source-git-commit: 11330ed8e79ec256b158747914f178b8b6857a33
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 1%

---

# 푸시 알림 채널 예정된 변경 사항 {#push-upgrade}

이 페이지에서는 Adobe Campaign Classic의 Firebase Cloud Messaging을 통해 푸시 알림 채널에 대해 예정된 변경 사항에 대해 설명합니다.

여기서 는 Adobe Campaign Classic 구현에 영향을 줄 수 있는 Firebase Cloud Messaging(FCM) 서비스에 대한 중요한 변경 사항입니다.

서비스 개선을 위한 Google의 지속적인 노력의 일환으로 레거시 FCM API는 2024년 6월에 중단됩니다(Firebase Cloud Messaging HTTP 프로토콜: https://firebase.google.com/docs/cloud-messaging/http-server-ref)

이러한 API는 현재 푸시 알림 메시지를 보내기 위해 Adobe Campaign Classic과 통합되었습니다. 당사는 귀하와 같은 많은 고객이 마케팅 캠페인 및 커뮤니케이션 요구 사항, 특히 Android 디바이스를 위해 이러한 서비스에 의존하고 있음을 잘 알고 있습니다.

## 어떤 영향을 미칩니까?

* **HTTP(기존) API 사용자**: 활성 푸시 알림 캠페인이 HTTP(레거시) API를 활용하는 경우 설정은 이 변경의 영향을 직접 받습니다. 현재 구성을 검토하고 최신 API로의 마이그레이션을 준비하는 것이 좋습니다.

* **HTTP v1 API 사용자를 위한 유용한 뉴스**: Android 푸시 알림용 HTTP v1 API만 사용하는 경우 이미 을(를) 준수하고 있으므로 추가 작업이 필요하지 않습니다.

## 뭐하는 거야?

* **전환 계획**: 우리 팀은 포괄적인 전환 계획을 수립하기 위해 적극적으로 노력하고 있습니다. 이렇게 하면 필요한 경우 최신 버전의 Adobe Campaign에서 이미 사용 가능하고 캠페인에 대한 중단을 최소화하면서 구현을 최신 FCM API로 업데이트할 수 있습니다.

* **자세한 지침**: 원활한 전환 프로세스를 촉진하기 위한 단계별 안내서와 기타 리소스를 제공합니다.

* **지원**: 이 전환 전반에 걸쳐 EMC 고객 지원 팀에서 도움을 드릴 수 있습니다. 또한 전환에 대한 기술 측면과 모범 사례를 다루기 위해 웨비나와 활성화 세션을 호스팅할 수 있습니다.

## 어떤 영향을 미칩니까?

* **최신 정보 수신**: 세부 전환 계획을 포함하여 더 이상 당사에서 커뮤니케이션을 할 수 없도록 받은 편지함을 주시하십시오.

* **현재 설정 검토**: 필요한 경우 변경할 수 있도록 Adobe Campaign Classic의 현재 구성 및 사용자 지정을 검토하십시오.

* **연락처**: 즉각적인 우려 사항이나 질문이 있는 경우 주저하지 말고 지원 팀에 문의하십시오.

## 구현 단계

앞으로 몇 주 이내에 타임라인 및 작업 항목을 포함하여 레거시 FCM API의 전환 계획에 대한 자세한 내용을 공유할 예정입니다. 안심하십시오. 당사의 주요 목표는 귀사와 귀하의 팀이 최대한 원활하게 전환하는 것입니다.

귀사의 비즈니스에 감사드리며 이러한 변화에 적응해 주신 데 대해 감사드립니다. 여러분의 성공이 저희의 최우선 과제이며, 저희는 여러분을 지원하기 위해 최선을 다하고 있습니다.

따라서 변경 사항을 예측할 수 있습니다. 다음은 푸시 구성을 HTTP(레거시)에서 FCM HTTPv1 API로 마이그레이션하는 데 필요한 일반 단계입니다.

### 빌드 업그레이드

* Campaign Classic: AC7 20.3.1 릴리스에 HTTPv1에 대한 지원이 추가되었습니다. 이전 버전을 사용하는 경우 먼저 최신 Campaign Classic 빌드로 업그레이드해야 합니다.

* Campaign v8: HTTPv1은 모든 Campaign v8 릴리스에서 지원됩니다. 업그레이드할 필요가 없습니다.

### 마케팅 서버

구성 변경은 고객/파트너가 수행할 수 있습니다.

1. 먼저 JSON 파일을 추출해야 합니다. 모바일 애플리케이션을 HTTPv1로 이동하려면 Firebase Admin SDK 서비스의 계정 JSON 파일이 필요합니다. 다음을 참조하십시오. [페이지](https://firebase.google.com/docs/admin/setup#initialize-sdk).

1. 내 목록으로 이동 **서비스 및 구독**.

1. HTTP(기존) API 버전을 사용하여 모든 모바일 애플리케이션을 찾습니다.

1. 이러한 각 모바일 애플리케이션에 대해 **API 버전** HTTPv1에 연결한 다음 [설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html).

>[!NOTE]
>
>HTTPv1 API로의 전환은 새 게재를 위해 고려됩니다. 다시 시도하거나, 진행 중이거나, 사용 중인 게재는 여전히 HTTP(기존) API를 사용합니다.

### 중간 소싱 서버

필요한 변경 사항이 없습니다.

### 실시간 실행 서버

이 경우 Adobe Campaign 지원 센터에 문의해야 합니다. 마이그레이션 절차는 마케팅 서버와 동일합니다.

### Android OS 및 Android 모바일 애플리케이션

Android 모바일 애플리케이션의 코드에는 특정 변경 사항이 필요하지 않으며 알림 동작은 변경되지 않아야 합니다.

그럼에도 불구하고 HTTPv1은 세 가지 새로운 페이로드 요소를 도입하고 있습니다.

| 이름 | 기본 값 |
|---|---|
| 고정 | 거짓 |
| 우선 순위 | 기본 |
| 가시성 | 거짓 |
| 고정 | 개인 |
