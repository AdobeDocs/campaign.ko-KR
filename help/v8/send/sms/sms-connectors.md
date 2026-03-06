---
title: SMS 커넥터
description: Adobe Campaign의 SMS 커넥터에 대해 알아보기
feature: SMS
role: User, Admin
level: Intermediate
source-git-commit: e349e9f236c3eeb28ffe96bcc5ec72ab64c4c127
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 1%

---

# SMS 커넥터 유형 기본 정보 {#sms-connectors}

Adobe Campaign은 고객에게 SMS 메시지를 전송하는 데 사용되는 두 개의 SMS 커넥터를 지원합니다.

* **기존 SMS 커넥터**: Campaign v7 및 이전 버전의 Campaign v8에 사용된 커넥터의 첫 번째 버전입니다. [자세히 알아보기](#legacy-sms-connector)
* **SMS 커넥터 v2**: Campaign v8.9.1부터 GA에서 사용할 수 있는 이 v2 전용 SMS 커넥터는 향상된 성능과 안정성을 제공하기 위해 현대화되었습니다. [자세히 알아보기](#sms-connector-v2)

## 레거시 SMS 커넥터 {#legacy-sms-connector}

레거시 SMS 커넥터는 이전 버전의 Adobe Campaign에서 사용된 MTA 기반 SMS 커넥터입니다. Adobe 이 커넥터는 기존 구현에서 여전히 지원되지만, v2 커넥터의 향상된 성능과 안정성을 활용하려면 v8.9.1 이상으로 업그레이드하는 것이 좋습니다.

v2 커넥터의 이점을 활용하는 방법을 알아보려면 [활성화](#activation) 섹션을 참조하세요.

기존 SMS 커넥터 구성 및 사용에 대한 자세한 내용은 [Campaign Classic 설명서](https://experienceleague.adobe.com/ko/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}를 참조하세요.

## SMS 커넥터 v2 {#sms-connector-v2}

v8.9.1부터 GA에서 사용할 수 있는 v2 커넥터는 송수신기 모드 SMPP 연결, 영구 SMPP 연결을 가능하게 하고 더 나은 호환성을 보장합니다. 전용 SMS 외부 계정은 v2 커넥터를 사용하는 모든 SMS 구현에 사용할 수 있습니다.

v2 커넥터는 새 설치에 대해 기본적으로 활성화되어 있습니다. 기존 커넥터를 사용하여 이전 버전에서 업그레이드한 경우 v2 커넥터로 전환하려면 Adobe 담당자에게 문의해야 합니다. [활성화](#activation) 섹션을 참조하십시오.

Campaign v8에서 SMS 커넥터 v2를 사용하는 방법을 알아보려면 [SMS 설명서](sms.md)를 참조하세요.

>[!NOTE]
>
>v2 커넥터는 몇 가지 제한 사항과 함께 다음 빌드에서도 사용할 수 있습니다.
>* 8.8.1: 모든 Campaign FDA 환경용 릴리스. Campaign FFDA 배포에는 사용할 수 없습니다.
>* 8.8.2: FFDA를 포함한 모든 배포 유형에 대한 릴리스. LA(Limited Availability)에 출시되었습니다.

## 활성화 {#activation}

### v2 커넥터로 전환하는 이유 {#why-switch-v2}

전용 SMS 프로세스에서는 SMPP 송수신기 모드를 지원하여 연결 수를 줄이고 리소스 효율성을 개선하는 동시에 필요한 경우 송신기/수신기 설정을 계속 지원합니다. 오류 복구 속도, 지속적인 연결, 로컬 파일 또는 프로세스 간 통신에 대한 의존도 없이 훨씬 뛰어난 안정성을 제공합니다. 또한 대기 시간이 짧고 처리량이 많으며 지능적인 마이크로 버칭을 통해 속도와 안정성 간의 균형을 맞출 수 있어 성능이 향상되었습니다. 또한 SMS 프로세스를 분리하면 문제 해결이 간단해지고 크로스 채널 영향이 최소화됩니다. 이러한 향상된 기능을 통해 전용 커넥터는 SMS 전송을 위한 보다 강력하고 확장 가능한 솔루션이 되었습니다.

### 구성 {#configuration}

Adobe Campaign Managed Cloud Services을 사용하면 Adobe에서 서버 구성 및 SMS 커넥터 마이그레이션을 관리합니다. 이 기술 절차를 수행하려면 서버 구성 파일 및 데이터베이스 작업에 직접 액세스해야 합니다.

SMS 커넥터 v2를 활성화하고 사용하려면 먼저 v8.9.1 이상으로 업그레이드해야 합니다. Adobe 담당자 또는 Adobe 고객 지원 센터에 문의하십시오. 인스턴스에 필요한 업데이트를 예약하고 수행합니다.