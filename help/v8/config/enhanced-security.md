---
title: Campaign 향상된 보안 추가 기능
description: Campaign 향상된 보안 추가 기능에 대한 보안 구성 지침
feature: Configuration
role: Developer
level: Experienced
exl-id: 7c586836-82e1-45fb-9c28-18361572e1fa
source-git-commit: 925f8152d28f60f876c5ef4420064fa0d71cdb9d
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 2%

---


# Campaign 향상된 보안 추가 기능 {#enhanced-security}

이 페이지는 Adobe v8용 [공개적으로 사용 가능한 권장 보안 구성 지침](security.md#public-guidance)의 일부입니다.

네트워크 연결을 보다 안전하게 만들고 리소스에 향상된 보안을 제공하기 위해 [!DNL Adobe Campaign]에서는 새로운 **향상된 보안** 추가 기능을 제공합니다.

이 추가 기능에는 다음 두 가지 생태계 기능이 포함됩니다.

* [CMK(Secure Customer-Managed Key) 통합](#secure-cmk-integration)

* [보안 가상 사설망(VPN) 터널링](#secure-vpn-tunneling)

이러한 기능은 아래에 자세히 설명되어 있습니다.

이 페이지에는 향상된 보안 기능과 관련된 몇 가지 보호 기능 및 제한 사항이 나와 있습니다. 또한 모든 보안 CMK 통합 / 보안 VPN 터널링 사용 사례가 작동하는지 확인해야 합니다.

이러한 기능이 구현되면 Adobe은 다음을 모니터링합니다.

* 인스턴스를 사용할 수 있고 키를 사용할 수 없는 경우 경고 를 계속 진행합니다.

* VPN은 터널링하고 문제가 발생할 경우 경고를 계속 진행합니다.

## 안전한 고객 관리 키 통합 {#secure-cmk-integration}

**CMK(Secure Customer-Managed Key) 통합**&#x200B;을(를) 사용하면 Amazon Web Services(AWS) 계정을 통해 자체 키를 사용하여 사용하지 않는 데이터를 암호화할 수 있습니다.

고객 관리 키는 사용자가 생성, 소유 및 관리하는 AWS 계정의 KMS(키 관리 서비스) 키입니다. 이러한 KMS 키를 완벽하게 제어할 수 있으며 이 키를 사용하여 데이터를 암호화하고 해독합니다. 암호화 키 생성 및 관리를 책임지게 함으로써 키 취소 등 암호화 키를 보다 세밀하게 제어할 수 있습니다.

>[!CAUTION]
>
>키를 취소하는 경우 영향을 알고 있어야 합니다. [자세히 알아보기](#cmk-callouts)

Campaign과 CMK 통합을 사용하려면 아래 단계를 따르십시오.

1. [Amazon Web Services(AWS)](https://aws.amazon.com/){target="_blank"} 계정에 연결합니다.

1. AWS KMS(키 관리 서비스)를 사용하여 자동 순환이 설정된 키를 생성합니다. [방법을 알아보세요](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}.

1. 리소스에 대한 액세스 권한을 부여하려면 Adobe에서 제공한 정책을 AWS 계정에 적용하십시오. [자세히 알아보기](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"}. <!--link TBC-->

1. [Amazon 리소스 이름(키 ARN)](https://docs.aws.amazon.com/kms/latest/developerguide/find-cmk-id-arn.html){target="_blank"}을(를) [!DNL Adobe Campaign]과(와) 공유합니다. 이렇게 하려면 Adobe 담당자에게 문의하십시오. <!--or Adobe transition manager?-->

1. Amazon EventBridge 규칙을 만들고 테스트하여 Adobe에서 키를 모니터링할 수 있습니다&#x200B;. [자세히 알아보기](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}.


### 가드레일 및 제한 사항 {#cmk-callouts}

Adobe Campaign v8과 CMK 통합에는 다음과 같은 보호 기능 및 제한 사항이 적용됩니다.

* Adobe은 [Amazon Web Services(AWS)](https://aws.amazon.com/){target="_blank"} 계정을 제공하지 않습니다. 자신의 AWS 계정이 있어야 하며, 이 계정을 설정하여 Adobe에서 키를 생성하고 공유해야 합니다.

* [AWS 키 관리 서비스](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"}(KMS) 키만 지원됩니다. KMS 외부의 고객 생성 키를 사용할 수 없습니다&#x200B;.

* 다운타임은 처음 설치하는 동안 예상됩니다. &#x200B;다운타임 기간은 데이터베이스의 크기에 따라 다릅니다.

* 고객은 키를 소유하고 유지 관리합니다. 키가 변경되면 Adobe에 연락해야 합니다&#x200B;.

* [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"}을(를) 사용하여 키를 감사하고 필요한 경우 취소할 수 있습니다&#x200B;.

* 키를 취소, 비활성화 또는 삭제하는 경우 해당 작업을 되돌릴 때까지 암호화된 리소스 및 인스턴스에 액세스할 수 없습니다.

  >[!CAUTION]
  >
  >키를 비활성화하고 7일 이내에 이 작업을 되돌리지 않으면 데이터베이스는 백업에서만 복구할 수 있습니다.
  >
  >키를 삭제하고 30일 이내에 이 작업을 되돌리지 않으면 모든 데이터가 영구적으로 삭제되고 손실됩니다&#x200B;.

## 보안 가상 개인 네트워크 터널링 {#secure-vpn-tunneling}

**Secure Virtual Private Network(VPN) 터널링**&#x200B;은(는) 개인 네트워크를 통해 전송 중인 데이터에 대한 보안 액세스를 사용자의 전제에서 [!DNL Adobe Campaign] 인스턴스로 제공하는 사이트 간 VPN입니다.

<!--As it connects two networks together, it is a site-to-site VPN.-->

HA(High Availability)를 보장하기 위해 한 터널에서 문제가 발생할 경우 두 개의 터널을 사용하여 중단을 방지합니다.

다음 세 가지 사용 사례가 지원됩니다.

* VPN을 통해 Campaign 인스턴스에서 온-프레미스 데이터베이스에 액세스하기 위한 VPN을 통한 FDA(Federated Data Access)

* Thick 클라이언트에서 VPN을 통해 인스턴스 로그인

* VPN을 통한 인스턴스 SFTP 액세스

>[!CAUTION]
>
>온-프레미스 및 클라우드 데이터베이스가 지원됩니다. [자세히 알아보기](#vpn-databases)

이 기능을 올바르게 사용하려면 아래 지침을 따르십시오.

* Adobe 측 VPN 구성을 기반으로 측 VPN을 설정합니다.

* 고가용성을 위해 두 터널을 모두 위로 유지합니다.

* 측면 터널을 모니터링합니다.

* 터널의 개시자여야 하며, 터널이 작동 중지될 경우 연결을 다시 시작하도록 정렬해야 합니다.

* 연결 실패가 발생할 경우를 대비하여 끝에 다시 시도 메커니즘을 설정합니다.

### 지원되는 데이터베이스 및 디바이스 {#vpn-databases}

지원되는 온-프레미스 데이터베이스는 다음과 같습니다.

* MySQL
* Netezza
* Oracle
* SAP HANA
* SQL Server
* Sybase
* Teradata
* Hadoop via HiveSQL
* PostgreSQL

클라우드 데이터베이스가 지원됩니다. [호환성 매트릭스](../start/compatibility-matrix.md#FederatedDataAccessFDA)를 참조하세요.

>[!NOTE]
>
>* 서드파티 또는 외부 공급업체에 대한 VPN 연결은 지원되지 않습니다.
>
>* Adobe에서 관리하는 사설 클라우드 데이터베이스에 대한 추가 VPN은 포함되지 않습니다.
