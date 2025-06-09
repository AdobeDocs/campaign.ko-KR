---
product: campaign
title: 기술 노트 - 자격 증명 회전 안내서
description: Adobe Campaign 기술 노트 - 자격 증명 회전 안내서
hide: true
hidefromtoc: true
exl-id: 0848ee2d-3506-4167-9aea-a1589aa82805
source-git-commit: 14e49a0b4de1b82239113bd670213449f464c27f
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 1%

---

# 기술 참고: 자격 증명 회전 안내서 {#ac-customer-credentials}

고객은 손상 위험을 완화하기 위해 자격 증명을 정기적으로 새 세트로 교체할 책임이 있습니다.

## Adobe Campaign 옵션 자격 증명 {#ac-options-credentials}

Adobe Campaign 탐색기에서 **관리 > 플랫폼 > 옵션** 노드를 사용하면 Adobe Campaign 옵션을 수정할 수 있습니다. 여기에 자격 증명을 저장한 경우 반드시 회전하십시오.

![](assets/technote-2.png)

## 외부 계정 자격 증명 {#ac-accounts-credentials}

**관리 > 플랫폼 > 외부 계정** 노드를 사용하면 Adobe Campaign 외부 계정을 수정할 수 있습니다.

외부 계정에 저장된 모든 자격 증명을 회전하십시오.

>[!CAUTION]
>
>**Adobe 관리 자격 증명을 수정하지 마십시오**. `adobe` 관련 서버가 있는 모든 외부 계정을 수정해서는 안 됩니다.

![](assets/technote-1.png)

특정 기술 `mc*`(예: mc1, mc2 등) 및 `Interaction*`(예: interaction1, interaction2 등) 연산자의 경우 아래 두 가지 방법 중 하나를 따를 수 있습니다.

1. Adobe은 이러한 연산자에 대한 자격 증명을 변경하여 사용자와 공유할 수 있습니다. 이러한 연산자를 사용하는 모든 통합은 이러한 연산자에 대한 자격 증명이 사용자 측에서 업데이트될 때까지 작동하지 않습니다.

1. Adobe은 각 기존 연산자에 해당하는 **new** 연산자를 만들어 사용자와 공유할 수 있습니다. Adobe은 이러한 새 연산자로 전환한 후 이전 연산자를 모두 삭제합니다.


## Mobile Services 개인 키/인증서  {#ac-key-credentials}

모바일 서비스 관련 개인 키 및 인증서 순환에 대해서는 아래 링크를 참조하십시오.

* Android의 경우 [이 설명서](https://experienceleague.adobe.com/ko/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android){target="_blank"}를 참조하세요.
**Android 모바일 애플리케이션 만들기 > API 버전 구성** 섹션으로 이동합니다.

* iOS의 경우 [이 설명서](https://experienceleague.adobe.com/ko/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application){target="_blank"}를 참조하세요.
**iOS 모바일 앱 만들기->인증 모드** 섹션으로 이동합니다.

## GPG 키 {#ac-gpg-credentials}

GPG 키를 회전하려면 다음 단계를 수행해야 합니다.

1. 기존 키를 사용하여 기존 데이터를 해독합니다. [자세히 알아보기](https://experienceleague.adobe.com/ko/docs/control-panel/using/instances-settings/gpg-keys-management#decrypting-data){target="_blank"}.

1. 새 GPG 키 쌍을 만듭니다. [이 설명서](https://experienceleague.adobe.com/ko/docs/control-panel/using/instances-settings/gpg-keys-management#decrypting-data){target="_blank"}에서 GPG 키 관리에 대해 자세히 알아보세요.

1. 모든 워크플로우의 기존 GPG 키 사용을 새로 만든 키로 바꿉니다.

1. 기존 GPG 키를 삭제합니다.
