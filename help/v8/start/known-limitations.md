---
product: Adobe Campaign
title: Campaign v8 알려진 제한 사항
description: 알려진 제한 사항
feature: 개요
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: cf00895f988514fc029d0060d7404bdef0c8b30e
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 2%

---

# 알려진 제한 사항

알려진 제한 사항은 이 제품 릴리스에서 지원하지 않거나 해당 제품과 올바르게 상호 작용하지 않는 기능, 아키텍처 또는 프로세스를 식별합니다. 이러한 제한 사항을 신중하게 검토하십시오.

Adobe Campaign v8의 경우 다음과 같은 제한 사항이 있습니다.

* Adobe Campaign v8은 온-프레미스/하이브리드 배포에 사용할 수 없습니다. Adobe 관리 Cloud Service으로 릴리스만 됩니다.
* 기존 고객은 기존 Adobe Campaign 환경에서 Adobe Campaign v8로 마이그레이션할 수 없습니다
* 양방향 데이터 복제 없음:Campaign 로컬 데이터베이스에서 클라우드 데이터베이스로의 복제만 수행됩니다
* 이 섹션](capability-matrix.md#gs-unavailable-features)에 나열된 기능은 현재 Campaign v8 빌드에서 사용할 수 없습니다[
* 사용 불가능하거나 제거된 일부 기능은 여전히 사용자 인터페이스에 표시됩니다
* 구독(옵트인) 및 구독 취소(옵트아웃) 메커니즘 및 모바일 등록은 비동기 프로세스입니다. 요청은 특정 기술 워크플로우를 통해 매시간 처리됩니다. [자세히 알아보기](../config/replication.md#tech-wf)
* 최종 사용자가 중복을 수동으로 처리해야 합니다. [자세히 알아보기](../dev/keys.md)
* Adobe Campaign v8은 API 및 웹 애플리케이션에서 확장된 처리량을 지원하지 않습니다. 특정 요구 사항이 있는 경우 Adobe에게 연락하여 지침을 받으십시오.


