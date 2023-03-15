---
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 814f7c81aa4f154fdf289effc82b8d02bdd9b4c6
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 91%

---

# 최신 릴리스{#latest-release}

이 페이지에서는 **최신 Campaign v8 릴리스**&#x200B;의 새로운 기능, 개선 사항 및 버그 해결 사항 목록을 확인할 수 있습니다.

## 릴리스 8.4.4 {#release-8-4-4}

_2023년 3월 8일_

**보안 개선**

* 보안을 개선하기 위해 Tomcat이 버전 8.5.81에서 8.5.85로 업데이트되었습니다. (NEO-50530)

**패치**

* 에서 스크롤하지 못하는 문제를 해결했습니다. **편집** dce(디지털 콘텐츠 편집기)의 탭입니다. (NEO-54474)
* 복제 중 웹 서버 충돌을 야기할 수 있는 문제를 해결했습니다. (NEO-53670)


>[!CAUTION]
>
> 클라이언트 콘솔 업그레이드는 필수입니다. 이 [페이지](../start/connect.md#upgrade-ac-console)에서 클라이언트 콘솔을 업그레이드하는 방법을 알아보십시오.


## 릴리스 8.4.3 {#release-8-4-3}


_2023년 1월 27일_

**개선 사항**

* 마케팅 서버와 중간 소싱 서버 간 게재 지표 동기화 문제를 해결했습니다. (NEO-50724) <!--OKKKK-->
* 워크플로우를 내보낼 때 오류가 발생할 수 있는 문제를 해결했습니다. (NEO-50555) <!--OKKKK-->
* 이전에 확장한 스키마를 확장할 때 발생하는 문제를 해결했습니다. (NEO-49118) <!--OKKKK-->
* 링크 정의에서 식별자가 동일한 두 개의 보강 활동을 사용할 때 발생하는 문제를 해결했습니다. (NEO-48851)
* 두 가지 게재 준비 실패 문제를 해결했습니다. 조작하는 잠재적 오퍼 수가 너무 많으면 게재 준비가 실패할 수 있었습니다. 두 번째 문제는 이미지 URL을 텍스트 형식 게재에서 추적할 URL로 정의한 경우 발생했습니다. (NEO-48807) <!--OKKKK-->
* 워크플로우가 FFDA 이외의 계정에 대해 외부 계정에서 정의한 데이터 웨어하우스 이름을 덮어쓰는 워크플로우 실패로 이어질 수 있는 문제를 해결했습니다. (NEO-43209) <!--OKKKK-->
* DDoS 공격을 방지하기 위해 웹 애플리케이션의 보안을 개선했습니다. (NEO-50757) <!--OKKKK-->
* **[!UICONTROL Consolidated tracking]**(nms:trackingStats) FFDA 테이블의 통합 추적 데이터 관리를 개선하여 중복을 방지했습니다. (NEO-46409)
* 워크플로우 쿼리의 논리 연산자 조건문에 `enableIf`을(를) 사용할 때의 논리 연산자 문제를 해결했습니다. 이전 논리 조건문을 덮어쓰는 문제가 있었습니다. (NEO-45815)  <!--OKKKK-->
* 성능을 개선하기 위해 과금 워크플로우의 활성 프로필 생성을 최적화했습니다. (NEO-47658) <!--OKKKK-->
* 이미지 노드(img)에 개인화 필드가 있는 URL이 포함된 경우 HTML 파일 가져오기 문제를 해결했습니다. (NEO-48396)
* **분할** 워크플로우 활동에서 정렬 매개변수를 사용할 때 Snowflake(전체 배포) 문제를 해결했습니다. (NEO-45899) <!--OKKKK-->
* nmsDeliveryMapping 폴더에 대한 읽기 액세스 권한이 있는 사용자가 캠페인 또는 워크플로우를 실행하려고 할 때 오류가 발생하는 문제를 해결했습니다. (NEO-48230)
* 큰 HTML 코드에 대해 발생할 수 있는 게재 HTML 탭의 성능 문제를 해결했습니다. (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* **선택한 라인 병합** 워크플로우 옵션을 사용할 수 없는 문제를 해결했습니다. (NEO-48488)
* 보강 중에 “0 또는 1 카디널리티 단순 결합”을 사용하면 레코드를 삭제하는 Snowflake FDA 커넥터 문제를 해결했습니다. (NEO-48737)
* log4j 라이브러리에 대한 나머지 참조를 Windows의 Campaign 설치에서 제거했습니다. (NEO-44851)
* **쿼리** 워크플로우 활동의 추가 데이터에 **열었던 수신자** (estimatedRecipientOpen) 지표를 추가할 때 오류가 발생하는 문제를 해결했습니다. (NEO-46665)
* 성능을 개선하기 위해 여러 게재가 있는 워크플로우의 추적 URL 관리를 개선했습니다. (NEO-50894) <!--OKKKK-->
* Xtkfolder를 사용하는 스키마의 복제가 실패하는 문제를 해결했습니다. (NEO-46787) <!--OKKKK-->
* NmsSubscription 테이블에서 “lastModified” 사용자 정의 열을 삭제하는 문제를 해결했습니다. (NEO-48402)


>[!CAUTION]
>
> 클라이언트 콘솔 업그레이드는 필수입니다. 이 [페이지](../start/connect.md#upgrade-ac-console)에서 클라이언트 콘솔을 업그레이드하는 방법을 알아보십시오.
