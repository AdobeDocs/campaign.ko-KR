---
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 3bc247ba81de3de56c26bdf8fa9b8aa5ea91fb2a
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 23%

---

# 최신 릴리스 {#latest-release}

이 페이지에는 Campaign v8(콘솔) **최신 릴리스**&#x200B;에 포함된 새로운 기능, 개선 사항 및 수정 사항이 나와 있습니다. Campaign 릴리스와 버전, 업그레이드에 대한 자세한 내용은 [이 페이지](upgrades.md)에서 알아보세요. 다른 릴리스는 이 설명서의 이전 릴리스 섹션에 나열되어 있습니다.

## 릴리스 8.8.2 {#release-8-8-2}

_2025년 10월 9일_

>[!AVAILABILITY]
>
>이 릴리스는 **LA(제한 공개)** 상태입니다. 

### 새로운 기능 {#features-8-8-2}

이제 **Campaign FFDA 배포**&#x200B;에 [새 SMS 전송 커넥터](../architecture/enterprise-deployment.md)를 사용할 수 있습니다. [자세한 설명서](../send/sms/sms.md)를 참조하세요.

이 릴리스에는 Campaign 웹 사용자 인터페이스에서 사용할 수 있는 기능 집합도 포함되어 있습니다.

* [트랜잭션 메시지의 프로필 보강](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html?lang=ko){target="_blank"}
* [트랜잭션 메시지, 푸시 알림 및 SMS를 위한 다국어 기능](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html?lang=ko){target="_blank"}

Campaign 웹 UI [릴리스 노트](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=ko){target="_blank"}를 참조하세요.

### 해결 사항 {#fixes-8-8-2}

<!--
* Fixed an issue which prevented dynamic reporting from being available for transactional messages.
-->
* 데이터베이스 정리 워크플로우가 실패하는 문제를 해결했습니다. (NEO-87949)
* 분산 마케팅에서 공동 캠페인 게재에 대한 추적 데이터가 기록되지 않는 문제를 해결했습니다. (NEO-86836)
<!--
* Issue SMS2.0 with FFDA Continuous Deliveries (NEO-88785)
-->
* 조각의 개인화가 제대로 작동하지 않는 문제를 해결했습니다. (NEO-88161)
* 새 Redshift ODBC 커넥터로 마이그레이션한 후 SQL 오류로 인해 분할 워크플로우 활동이 실패할 수 있는 문제를 해결했습니다. (NEO-87466)
* 워크플로우에서 부정확한 제외 수를 초래할 수 있는 문제를 해결했습니다. (NEO-89207)
* 푸시 알림에 대한 클릭 지표가 부정확해질 수 있는 문제를 해결했습니다. (NEO-89503)
* SMS 게재 로그가 올바르게 업데이트되지 않아 Adobe Campaign에서 정확한 상태 보고가 이루어지지 않는 문제가 해결되었습니다. (NEO-88479)
* 게재 콘텐츠에서 프랑스어 따옴표가 영어 따옴표로 잘못 변환되던 문제를 수정했습니다. (NEO-89631)
* Real-Time Server가 대신 잘못된 IMS 토큰에 대한 잘못된 응답 코드를 반환한 문제가 해결되었습니다. (NEO-87428)
* 이메일 및 SMS에 대한 게재 통계가 완전히 다시 계산되지 않아 정확하지 않은 성공 지표가 발생하는 문제를 해결했습니다. (NEO-88106)
* 게재 로그가 작은 메시지 하위 집합에 대한 게재 상태를 잘못 할당했던 새 SMS 전송 커넥터 문제를 해결했습니다. (NEO-89581)
* T-Mobile 게재에 대한 성공 지표가 마케팅 및 중간 서버 모두에서 올바르게 업데이트되지 않는 새 SMS 전송 커넥터 문제를 해결했습니다. (NEO-89850)
* 추적 로그 누락 및 잘못된 보고의 원인이 되는 실시간 및 마케팅 인스턴스 간 동기화 문제를 해결했습니다. (NEO-90247)
* 사용자 지정 스키마의 두 개의 연속 1-N 링크에서 필드를 선택할 때 오류가 발생할 수 있는 워크플로우 보강 문제를 해결했습니다. (NEO-87682)

