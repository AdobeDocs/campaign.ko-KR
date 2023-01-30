---
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: e7f4982a9b13fe5413b6cce0a1cc58e2b3a6afa4
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 34%

---

# 최신 릴리스{#latest-release}

이 페이지에서는 **최신 Campaign v8 릴리스**&#x200B;의 새로운 기능, 개선 사항 및 버그 해결 사항 목록을 확인할 수 있습니다.

## 릴리스 8.4.3 {#release-8-4-3}

>[!CAUTION]
>
> 클라이언트 콘솔 업그레이드는 필수입니다. 이 [페이지](../start/connect.md#download-ac-console)에서 클라이언트 콘솔을 업그레이드하는 방법을 알아보십시오.

_2023년 1월 27일_

**개선 사항**

* 마케팅 서버와 중간 소싱 서버 간의 게재 지표 동기화 문제를 해결했습니다. (NEO-50724) <!--OKKKK-->
* 워크플로우를 내보낼 때 오류가 발생할 수 있는 문제를 해결했습니다. (NEO-50555) <!--OKKKK-->
* 이전에 확장된 스키마를 확장할 때 발생하는 문제를 수정했습니다. (NEO-49118) <!--OKKKK-->
* 링크 정의에 동일한 식별자로 두 개의 데이터 보강 활동을 사용할 때 발생하는 문제를 수정했습니다. (NEO-48851)
* 두 개의 게재 준비 실패 문제가 해결되었습니다. 조작된 잠재적 오퍼 수가 너무 많으면 게재 준비가 실패할 수 있습니다. 두 번째 문제는 이미지 URL이 텍스트 형식 배달에서 추적할 URL로 정의될 때 발생했습니다. (NEO-48807) <!--OKKKK-->
* 워크플로우가 FFDA 이외의 계정에 대해 외부 계정에 정의된 웨어하우스 이름을 덮어쓰는 워크플로우 오류가 발생할 수 있는 문제를 수정했습니다. (NEO-43209) <!--OKKKK-->
* DDoS 공격을 방지하기 위해 웹 응용 프로그램의 보안이 개선되었습니다. (NEO-50757) <!--OKKKK-->
* 통합 추적 데이터 관리가 **[!UICONTROL Consolidated tracking]** (nms:trackingStats) 중복을 방지하기 위한 FFDA 테이블입니다. (NEO-46409)
* 을 사용할 때 워크플로우 쿼리의 논리 연산자 문제를 해결했습니다 `enableIf` 를 반환합니다. 이전 논리 조건을 덮어씁니다. (NEO-45815)  <!--OKKKK-->
* 활성 프로필 생성은 성능을 개선하기 위해 청구 워크플로우에서 최적화되었습니다. (NEO-47658) <!--OKKKK-->
* 이미지 노드(img)에 개인화 필드가 있는 URL이 포함된 경우 HTML 파일 가져오기 문제를 해결했습니다. (NEO-48396)
* 에서 정렬 매개 변수를 사용할 때 Snowflake(모든 배포)와 관련된 문제를 해결했습니다. **분할** 워크플로우 활동. (NEO-45899) <!--OKKKK-->
* nmsDeliveryMapping 폴더에 대한 읽기 액세스 권한이 있는 사용자가 캠페인 또는 워크플로우를 실행하려고 할 때 오류가 발생하는 문제를 해결했습니다. (NEO-48230)
* 큰 HTML 코드에 대해 발생할 수 있는 게재 HTML 탭의 성능 문제를 해결했습니다. (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* 사용자가 **선택한 행 병합** 워크플로우 옵션. (NEO-48488)
* 보강 중에 &quot;0 또는 1 카디널리티 단순 조인&quot; 옵션을 사용할 때 레코드가 삭제되는 Snowflake FDA 커넥터 문제를 해결했습니다. (NEO-48737)
* log4j 라이브러리에 대한 나머지 참조를 Windows의 Campaign 설치에서 제거했습니다. (NEO-44851)
* **쿼리** 워크플로우 활동의 추가 데이터에 **열었던 수신자** (estimatedRecipientOpen) 지표를 추가할 때 오류가 발생하는 문제를 해결했습니다. (NEO-46665)
* 성능을 개선하기 위해 여러 게재가 있는 워크플로우에서 추적 URL 관리를 개선했습니다. (NEO-50894) <!--OKKKK-->
* Xtkfolder를 사용하는 스키마 복제가 실패하는 문제를 해결했습니다. (NEO-46787) <!--OKKKK-->
* NmsSubscription 테이블에서 &quot;lastModified&quot; 사용자 지정 열이 삭제되는 문제를 수정했습니다. (NEO-48402)
