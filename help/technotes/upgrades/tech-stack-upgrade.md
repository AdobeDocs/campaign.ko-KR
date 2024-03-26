---
product: campaign
title: 기술 노트 - Adobe Campaign 시스템 업그레이드
description: Adobe Campaign 시스템 업그레이드
hide: true
hidefromtoc: true
exl-id: cc64cce1-2473-4136-aadc-8b13e89ef7f9
source-git-commit: 0f5efba364ef924447324bdd806e15e6db8d799d
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 9%

---

# Adobe Campaign 2023 환경 업그레이드 {#ac-system-upgrade}

Campaign 인프라는 최신 버전 및 수정 사항으로 정기적으로 업데이트해야 하는 서드파티 시스템을 사용합니다. 이러한 업데이트는 서비스의 연속성을 보장하고 보안 위험으로부터 Campaign 환경을 보호하기 위해 필수입니다. 또한 서드파티 시스템 변경 사항과의 호환성을 보장하려면 Campaign을 업그레이드해야 합니다.

로서의 **관리되는 Cloud Service 고객**, Adobe은 이러한 업그레이드가 필요할 때 사용자에게 알려 줍니다. 규정 준수를 보장하려면 권장 사항에 따라 환경을 업그레이드해야 합니다.

보안상의 이유로 Adobe은 [최신 Campaign 빌드 설치](#ac-upgrade)을 클릭한 다음 을(를) 업그레이드하십시오 [운영 체제](#os-upgrade) 및/또는 사용자 [RDBMS(관계 데이터베이스 관리 시스템)](#pg-upgrade).

>[!NOTE]
>
>이러한 변경 사항에 대한 질문이 있으면 [Adobe 고객 지원 센터](https://helpx.adobe.com/kr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html)에 문의하십시오.
>

## Campaign 빌드 업그레이드 {#ac-upgrade}

**영향을 받습니까?**

의 영향을 받는 경우 [운영 체제 업그레이드](#os-upgrade) 및/또는 [데이터베이스 시스템 업그레이드](#pg-upgrade) 아래에 자세히 설명되어 있습니다. Adobe은 Campaign 환경을 다음으로 업그레이드해야 합니다. [최신 8.4.3 버전](../../v8/start/release-notes.md): 이러한 시스템과 호환됩니다.

**업데이트 방법**

관리 Cloud Service 고객은 Adobe에게 연락하여 Campaign 버전을 업그레이드합니다.

## 운영 체제 업그레이드 {#os-upgrade}

**영향을 받습니까?**

데비안 운영 체제에서 Campaign을 실행하는 경우 최신 데비안 보안 업데이트의 혜택을 받으려면 Adobe이 Campaign 인프라를 다음으로 이동해야 합니다. **데비안**. Debian 9에 대한 보안 지원은 2023년 6월 30일까지 제공됩니다.

**업데이트 방법**

관리 Cloud Service 고객은 Adobe에게 연락하여 환경을 업그레이드합니다.

## 데이터베이스 시스템 업그레이드 {#pg-upgrade}

**영향을 받습니까?**

Campaign용 데이터베이스 시스템이 PostgreSQL인 경우 최신 PostgreSQL 혁신 및 보안 업데이트의 혜택을 받으려면 Adobe을 로 업그레이드해야 합니다. **PostgreSQL 14**. PostgreSQL 11은 2023년 11월 9일에 사용이 종료됩니다.

**업데이트 방법**

관리 Cloud Service 고객은 Adobe에게 연락하여 데이터베이스 시스템을 PostgreSQL 11에서 PostgreSQL 14로 업그레이드합니다.
