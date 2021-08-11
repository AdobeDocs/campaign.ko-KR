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
workflow-type: ht
source-wordcount: '312'
ht-degree: 100%

---

# 최신 릴리스{#latest-release}

이 페이지에서는 **최신 Campaign v8 릴리스**&#x200B;의 새로운 기능, 개선 사항 및 버그 해결 사항 목록을 확인할 수 있습니다.

## 릴리스 8.1.14 {#release-8-1-14}

_2021년 7월 23일_

**새로운 기능**

<table>
<thead>
<tr>
<th><strong>새로운 워크플로우 활동: 데이터 소스 변경</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>새로 추가된 <b>데이터 소스 변경</b> 워크플로우 활동을 사용하면 워크플로우의 작업 테이블의 데이터 소스를 변경할 수 있습니다. 이를 통해 다양한 데이터 소스(FDA, FFDA 및 로컬 데이터베이스)에서 데이터를 유연하게 관리할 수 있습니다.</p>
<p>Adobe Campaign 워크플로우에서 데이터는 작업(또는 임시) 테이블을 사용하여 관리됩니다. 워크플로우를 실행하면 작업 테이블이 여러 워크플로우 활동 간에 데이터를 공유합니다. 기본 설정에서 작업 테이블은 쿼리하는 데이터의 소스와 동일한 데이터베이스에 생성됩니다.</p>
<p>Campaign v8을 사용하면 기본 프로필 테이블이 클라우드 데이터베이스에 직접 저장됩니다. 따라서 [프로필] 테이블을 쿼리하면 클라우드 데이터베이스에서도 작업 테이블이 만들어집니다. 때에 따라서는 특정 작업을 수행하기 위해 작업 테이블을 다른 데이터 소스로 이동하는 것이 적절할 수 있습니다.</p>
<p>자세한 내용은 <a href="../config/workflows.md#change-data-source-activity">세부 설명서</a>를 참조하세요.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>LINE 채널 사용 가능</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>이제 Campaign v8에서 <a href="../send/line.md">LINE 채널</a>을 사용할 수 있습니다. 이 채널을 <a href="../send/transactional.md">트랜잭션 메시지</a> 모듈과 결합하는 경우에 대해 다음과 같은 개선 사항이 있습니다.
<ul> 
<li><p>LINE 게재에서 방문자가 타깃팅되지 않는 문제를 해결했습니다. 
</p></li>
<li><p>실행 인스턴스에서 마케팅 인스턴스로 방문자를 검색할 때 오류가 발생할 수 있는 문제를 해결했습니다.
</p></li>
<li><p>실시간 이벤트 처리 중 발생하는 문제를 해결했습니다.</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**기타 개선 사항**

* 특정 게재에 대해 **핫 클릭** 보고서가 표시되지 않는 문제를 해결했습니다.
* **중복 제거** 워크플로우 활동에서 중복을 부정확하게 인식하는 문제를 해결했습니다.
* 워크플로우 쿼리에 &quot;ID가 비어 있지 않음&quot; 필터를 적용하여 사용할 때 전환 모집단에 비어 있는 항목이 표시되는 문제를 해결했습니다.
* 새로운 타겟 매핑 시 추가 필드를 만들 수 없는 문제를 해결했습니다.
