---
title: Campaign v8 알려진 제한 사항
description: 알려진 제한 사항
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: true
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: e41816003958c3373e92d5ea82240fd7ceda5857
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 100%

---

# 알려진 제한 사항

알려진 제한 사항에서는 이 제품의 해당 릴리스에서 지원하지 않거나 해당 릴리스와 올바르게 상호 작용하지 않는 기능, 아키텍처 또는 프로세스를 다룹니다. 이 제한 사항을 신중하게 검토해 주세요.

Adobe Campaign v8의 제한 사항:

* Adobe Campaign v8은 온-프레미스/하이브리드 배포에 사용할 수 없으며, Adobe 관리 클라우드 서비스로만 릴리스할 수 있습니다.
* 기존 고객은 기존 Adobe Campaign 환경에서 Adobe Campaign v8로 마이그레이션할 수 없습니다.
* 양방향 데이터 복제 없음: Campaign 로컬 데이터베이스에서 클라우드 데이터베이스로의 복제만 가능합니다.
* [이 섹션](capability-matrix.md#gs-unavailable-features)에 나열된 기능은 현재 Campaign v8 빌드에서 사용할 수 없습니다.
* 사용할 수 없거나 제거된 기능 중 일부는 계속 사용자 인터페이스에 표시됩니다.
* 구독(옵트인) 및 구독 취소(옵트아웃) 메커니즘 및 모바일 등록은 동기화되지 않는 프로세스입니다. 요청은 특정 기술 워크플로우를 통해 한 시간에 한 번씩 처리됩니다. [자세히 알아보기](../config/replication.md#tech-wf)
* 복제본은 최종 사용자가 수동으로 처리해야 합니다. [자세히 알아보기](../dev/keys.md)
* Adobe Campaign v8은 API 및 웹 애플리케이션에서 확장된 처리량을 지원하지 않습니다. 특정 요구 사항이 있는 경우 Adobe에게 연락하여 안내를 받으십시오.
* Adobe Campaign의 Campaign 최적화 모듈은 압력 유형화 규칙에 대해 예약된 게재를 고려하지 않습니다. 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/pressure-rules.html?lang=ko#setting-the-period)를 참조하세요.