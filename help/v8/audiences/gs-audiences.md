---
title: Campaign에서 프로필 및 대상자 시작
description: Campaign에서 프로필 및 대상자를 만들고 관리하는 방법을 알아봅니다
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 43483085-8aa6-47e6-89e7-9211e37beaa4
version: Campaign v8, Campaign Classic v7
source-git-commit: b24e05f152bc299ea7953856bfa71950b5cc9837
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 20%

---

# 프로필 및 대상자 시작하기{#gs-profiles-and-audiences}

프로필은 고객, 서비스 구독자 또는 잠재 고객과 같이 Campaign 데이터베이스에 저장된 연락처입니다. 프로필을 가져오고 이 데이터베이스를 빌드하는 데 사용할 수 있는 메커니즘은 웹 양식을 통한 온라인 수집, 텍스트 파일 수동 또는 자동 가져오기, 회사 데이터베이스 또는 기타 정보 시스템을 사용한 복제와 같이 다양합니다. Adobe Campaign을 사용하면 마케팅 기록, 구매 정보, 환경 설정, CRM 데이터 및 관련 PI 데이터를 통합 보기에 통합하여 분석하고 조치를 취할 수 있습니다. 프로필에는 개인에 대한 타겟팅, 자격 부여 및 추적에 필요한 모든 정보가 포함되어 있습니다.

프로필은 이름, 성, 이메일 주소, 쿠키 ID, 고객 ID, 모바일 식별자 또는 특정 채널과 관련된 기타 정보와 같은 모든 프로필 특성을 저장하는 외부 테이블 또는 **nmsRecipient** 테이블의 레코드입니다. 수신자 테이블과 연결된 다른 테이블에는 프로필 관련 데이터가 포함됩니다(예: 수신자에게 전송된 모든 게재의 레코드가 포함된 게재 로그 테이블). [이 섹션](../dev/datamodel.md#ootb-profiles)에서 기본 제공 프로필 및 받는 사람 테이블에 대해 자세히 알아보세요.

![](assets/recipients-in-explorer.png)

Adobe Campaign에서 **수신자**&#x200B;는 게재(이메일, SMS 등)를 보낼 타겟팅된 기본 프로필입니다.

데이터베이스에 저장된 수신자 데이터를 사용하면 지정된 게재를 받을 대상을 필터링하고 게재 콘텐츠에 개인화 데이터를 추가할 수 있습니다. 데이터베이스에 다른 유형의 프로필이 있습니다. 다양한 용도로 디자인되어 있습니다. 예를 들어 최종 대상으로 전송되기 전에 시드 프로필을 테스트하여 게재를 테스트합니다.

Adobe Campaign을 프로필 데이터로 채우려면 다음을 수행할 수 있습니다.

* CRM 시스템 또는 플랫 파일과 같은 외부 데이터 원본에서 [데이터 파일 가져오기](../start/import.md)
* 고객이 자신의 정보를 입력하고 자신의 프로필을 만들 수 있도록 [웹 양식을 만듭니다](../dev/webapps.md)
* 프로필이 저장된 외부 데이터베이스에 [매핑](../connect/fda.md)
* 다음과 같이 클라이언트 콘솔에서 프로필을 수동으로 입력합니다.

![](assets/create-profile.png)

<!--You can also select your message audience in an external file: recipients are stored not in the database, but in files. These are known as "external" deliveries. These contacts can be imported or not in Adobe Campaign. [Learn more](external-profiles.md).-->

가져온 후에는 메시지를 보낼 대상을 만들 수 있습니다. 이 섹션[에서 대상 &#x200B;](create-audiences.md)을(를) 만드는 방법을 알아보세요.