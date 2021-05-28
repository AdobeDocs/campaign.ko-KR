---
solution: Campaign v8
product: Adobe Campaign
title: Campaign v8 알려진 제한 사항
description: 알려진 제한 사항
feature: 개요
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: 15cd7228a4920702cae182c68e7a329345946e31
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 1%

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
* ID 관리 - 중복 - 확인 + 세부 정보
* 라인 - 확인 + 상세내역
* 지연 - 확인 + 세부 정보
