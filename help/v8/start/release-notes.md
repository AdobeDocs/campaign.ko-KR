---
product: Adobe Campaign
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: 개요
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 328f1bca11f8554def6ad4ccb741a86695481e98
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 7%

---

# 최신 릴리스{#latest-release}

이 페이지에는 **최신 Campaign v8 릴리스**&#x200B;에 포함된 새로운 기능, 개선 사항 및 수정 사항이 나와 있습니다.

## 릴리스 8.1.14 {#release-8-1-14}

_2021년 7월 23일_

**새로운 기능**

<table>
<thead>
<tr>
<th><strong>새 워크플로우 활동: 데이터 소스 변경</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>새 <b>데이터 소스 변경</b> 워크플로우 활동을 사용하면 워크플로우의 작업 테이블의 데이터 소스를 변경할 수 있습니다. 이렇게 하면 다양한 데이터 소스(FDA, FFDA 및 로컬 데이터베이스)에서 데이터를 유연하게 관리할 수 있습니다.</p>
<p>Adobe Campaign 워크플로우에서 데이터는 작업(또는 임시) 테이블을 사용하여 관리됩니다. 워크플로우가 실행되면 작업 테이블이 워크플로우 활동 간에 데이터를 공유합니다. 기본적으로 작업 테이블은 쿼리하는 데이터의 소스와 동일한 데이터베이스에 생성됩니다.</p>
<p>Campaign v8을 사용하면 기본 프로필 테이블이 클라우드 데이터베이스에 직접 저장됩니다. 따라서 프로필 테이블을 쿼리하면 클라우드 데이터베이스에서도 작업 테이블이 만들어집니다. 특정 작업을 수행하기 위해 작업 테이블을 다른 데이터 소스로 이동하는 것이 적절할 수 있습니다.</p>
<p>자세한 내용은 <a href="../config/workflows.md#change-data-source-activity">세부 설명서</a>를 참조하십시오.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>LINE 채널 가용성</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p><a href="../send/line.md">LINE 채널</a>은(는) 이제 <a href="../send/transactional.md">트랜잭션 메시지</a> 모듈과 결합할 때 다음과 같은 향상된 기능을 포함하여 Campaign v8에서 사용할 수 있습니다.
<ul> 
<li><p>LINE 게재에서 방문자가 타겟팅되지 않는 문제를 해결했습니다. 
</p></li>
<li><p>실행 인스턴스에서 마케팅 인스턴스로 방문자를 검색할 때 오류가 발생할 수 있는 문제를 수정했습니다.
</p></li>
<li><p>실시간 이벤트를 처리하는 동안 발생하는 문제를 수정했습니다.</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**기타 개선 사항**

* **핫 클릭** 보고서가 특정 게재에 대해 표시되지 않도록 하는 문제를 해결했습니다.
* 중복 제거&#x200B;**워크플로우 활동에서 부정확한 중복 카운트가 발생할 수 있는 문제를 수정했습니다.**
* ID가 비어 있지 않음 필터와 함께 워크플로우 쿼리를 사용할 때 전환 모집단에서 빈 항목이 표시되는 문제를 해결했습니다.
* 새 대상 매핑에서 추가 필드가 생성되지 않는 문제가 해결되었습니다.
