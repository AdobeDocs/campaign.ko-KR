---
title: 향상된 보안 추가 기능
description: Campaign 향상된 보안 추가 기능 시작
feature: Configuration
role: Developer
level: Experienced
hide: true
hidefromtoc: true
exl-id: 7c586836-82e1-45fb-9c28-18361572e1fa
source-git-commit: f9b064dffa0f8792e8653760cb2ac44cfdf43848
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 1%

---

# 향상된 보안 추가 기능 {#enhanced-security}

네트워크 연결을 보다 안전하게 만들고 리소스에 대해 향상된 보안을 제공하기 위해 [!DNL Adobe Campaign] 새 항목 제공 **향상된 보안** 추가 기능.

이 추가 기능에는 다음 두 가지 생태계 기능이 포함됩니다.

* [보안 CMK 통합](#secure-cmk-integration)

* [보안 VPN 터널링](#secure-vpn-tunneling)

이러한 기능은 아래에 자세히 설명되어 있습니다.

## 보안 CMK 통합 {#secure-cmk-integration}

다음 **CMK(Secure Customer-Managed Key) 통합** 에서는 Amazon Web Services(AWS) 계정을 통해 자체 키를 사용하여 인스턴스 및 데이터를 암호화할 수 있습니다.

고객 관리 키는 사용자가 생성, 소유 및 관리하는 AWS 계정의 KMS(키 관리 서비스) 키입니다. 이러한 KMS 키를 완벽하게 제어할 수 있으며 이 키를 사용하여 데이터를 암호화하고 해독합니다. 암호화 키 생성 및 관리를 책임지게 함으로써 키 취소 등 암호화 키를 보다 세밀하게 제어할 수 있습니다.

>[!CAUTION]
>
>키를 취소하는 경우 영향을 알고 있어야 합니다. [자세히 알아보기](#cmk-callouts)

Campaign과 CMK 통합을 사용하려면 아래 단계를 따르십시오.

1. 다음에 연결 [Amazon Web Services(AWS)](https://aws.amazon.com/){target="_blank"} 계정입니다.

1. AWS KMS(키 관리 서비스)를 사용하여 자동 순환이 설정된 키를 생성합니다. [방법 알아보기](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}.

1. 리소스에 대한 액세스 권한을 부여하려면 Adobe으로 제공된 정책을 AWS 계정에 적용하십시오. [자세히 알아보기](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"}. <!--link TBC-->

1. 공유하기 [Amazon 리소스 이름(키 ARN)](https://docs.aws.amazon.com/kms/latest/developerguide/find-cmk-id-arn.html){target="_blank"} 포함 [!DNL Adobe Campaign]. 이렇게 하려면 Adobe 담당자에게 문의하십시오. <!--or Adobe transition manager?-->

1. Amazon EventBridge 규칙을 만들고 테스트하여 Adobe으로 키를 모니터링할 수 있습니다&#x200B;. [자세히 알아보기](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}.

## 보안 VPN 터널링 {#secure-vpn-tunneling}

다음 **보안 가상 사설망(VPN) 터널링** 는 사용자의 구내에서 로 개인 네트워크를 통해 전송되는 데이터에 대한 보안 액세스를 제공하는 사이트 간 VPN입니다. [!DNL Adobe Campaign] 인스턴스.

<!--As it connects two networks together, it is a site-to-site VPN.-->

HA(High Availability)를 보장하기 위해 한 터널에서 문제가 발생할 경우 두 개의 터널을 사용하여 중단을 방지합니다.

다음 세 가지 사용 사례가 지원됩니다.

* VPN을 통한 FDA(Federated Data Access)<!--to access your on-premise database from the Campaign instance over VPN-->

* Thick 클라이언트에서 VPN을 통해 인스턴스 로그인

* VPN을 통한 인스턴스 SFTP 액세스

>[!CAUTION]
>
>온-프레미스 데이터베이스 및 AWS 호환 VPN 장치만 지원됩니다. [자세히 알아보기](#vpn-callouts)

이 기능을 올바르게 사용하려면 아래 지침을 따르십시오.

* Adobe 측 VPN 구성을 기반으로 측 VPN을 설정합니다.

* 고가용성을 위해 두 터널을 모두 위로 유지합니다.

* 측면 터널을 모니터링합니다.

* 터널의 개시자여야 하며, 터널이 작동 중지될 경우 연결을 다시 시작하도록 정렬해야 합니다.

* 연결 실패가 발생할 경우를 대비하여 끝에 다시 시도 메커니즘을 설정합니다.

## 보호 기능 {#callouts}

향상된 보안 기능과 관련된 몇 가지 보호 기능 및 제한 사항이 아래에 나와 있습니다.

* 모든 보안 CMK 통합 / 보안 VPN 터널링 사용 사례가 작동하는지 확인합니다.

<!--* Adobe shall reach out to you or your technical team if any issue is found on your side.

* Currently, when using Enhanced security features, any communication with Adobe must be performed manually via email.-->

* Adobe이 다음을 모니터링합니다.

   * 인스턴스를 사용할 수 있고 키를 사용할 수 없는 경우 경고 를 계속 진행합니다.

   * VPN은 터널링하고 문제가 발생할 경우 경고를 계속 진행합니다.

### 보안 CMK 통합 보호 {#cmk-callouts}

* Adobe은 AWS 계정을 제공하지 않습니다. 고유한 AWS 계정이 있어야 하며, 이 계정을 설정하여 키를 생성하고 Adobe과 공유해야 합니다.

* 전용 [AWS 키 관리 서비스](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"} (KMS) 키가 지원됩니다. KMS 외부의 고객 생성 키를 사용할 수 없습니다&#x200B;.

* 처음 설치하는 경우 일부 다운타임이 발생합니다. &#x200B;가동 중지 시간은 데이터베이스의 크기에 따라 다릅니다.

* 키를 소유하고 유지 관리하는 동안 키가 변경되면 Adobe에 연락해야 합니다&#x200B;.

* 다음을 사용하여 키를 감사할 수 있습니다. [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"} 필요한 경우 취소합니다&#x200B;.

* 키를 취소, 비활성화 또는 삭제하는 경우 해당 작업을 되돌릴 때까지 암호화된 리소스 및 인스턴스에 액세스할 수 없습니다.

  >[!CAUTION]
  >
  >키를 비활성화하고 7일 이내에 이 작업을 되돌리지 않으면 데이터베이스는 백업에서만 복구할 수 있습니다.
  >
  >키를 삭제하고 30일 이내에 이 작업을 되돌리지 않으면 모든 데이터가 영구적으로 삭제되고 손실됩니다&#x200B;.

### 보안 VPN 터널링 보호 기능 {#vpn-callouts}

* 현재 지원되는 온-프레미스 데이터베이스는 다음과 같습니다<!--Richa to check the list with PM-->:

   * MySQL
   * Netezza 
   * Oracle 
   * SAP HANA 
   * SQL 서버 
   * Sybase 
   * Teradata 
   * Hadoop via HiveSQL

* AWS 호환 VPN 장치만 지원됩니다. 호환되는 장치 목록은에서 사용할 수 있습니다. [이 페이지](https://docs.aws.amazon.com/vpn/latest/s2svpn/your-cgw.html#example-configuration-files){target="_blank"}<!--check which list should be communicated-->.

* 서드파티 또는 외부 공급업체에 대한 VPN 연결은 지원되지 않습니다.

* 개인 클라우드 데이터베이스에 대한 Adobe 관리 추가 VPN은 포함되지 않습니다.