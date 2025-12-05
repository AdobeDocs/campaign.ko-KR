---
title: 새 SMS 커넥터 v2로 이동
description: 새 SMS 커넥터 v2로 이동하는 방법 알아보기
feature: Technote
role: Admin
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
source-git-commit: 30ab5a10f17baddfc455dc406a4f31f058ea05ba
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# 새 SMS 커넥터 v2로 이동

Adobe Campaign v8에서는 기존 MTA 기반 SMS 커넥터에 비해 향상된 성능과 안정성을 제공하는 새로운 **전용 SMS 프로세스 커넥터**(v2)를 도입했습니다.

## v2 커넥터로 전환하는 이유

전용 SMS 프로세스에서는 SMPP 송수신기 모드를 지원하여 연결 수를 줄이고 리소스 효율성을 개선하는 동시에 필요한 경우 송신기/수신기 설정을 계속 지원합니다. 오류 복구 속도, 지속적인 연결, 로컬 파일 또는 프로세스 간 통신에 대한 의존도 없이 훨씬 뛰어난 안정성을 제공합니다. 또한 대기 시간이 짧고 처리량이 많으며 지능적인 마이크로 버칭을 통해 속도와 안정성 간의 균형을 맞출 수 있어 성능이 향상되었습니다. 또한 SMS 프로세스를 분리하면 문제 해결이 간단해지고 크로스 채널 영향이 최소화됩니다. 이러한 향상된 기능을 통해 전용 커넥터는 SMS 전송을 위한 보다 강력하고 확장 가능한 솔루션이 되었습니다.

## 구성

Adobe Campaign Managed Cloud Services을 사용하면 Adobe에서 서버 구성 및 SMS 커넥터 마이그레이션을 관리합니다. 이 기술 절차를 수행하려면 서버 구성 파일 및 데이터베이스 작업에 직접 액세스해야 합니다.

새 SMS 커넥터 v2로 마이그레이션해야 하는 경우 Adobe 담당자 또는 Adobe 고객 지원 센터에 문의하십시오. 인스턴스에 필요한 업데이트를 예약하고 수행합니다.

Campaign v8의 SMS 채널에 대한 자세한 내용은 [SMS 설명서](../../v8/send/sms/sms.md)를 참조하세요.
