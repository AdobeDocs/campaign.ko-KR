---
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: ht
source-wordcount: '756'
ht-degree: 100%

---

# 최신 릴리스{#latest-release}

이 페이지에서는 **최신 Campaign v8 릴리스**&#x200B;의 새로운 기능, 개선 사항 및 버그 해결 사항 목록을 확인할 수 있습니다.

## 릴리스 8.1.20 {#release-8-1-20}

_2021년 9월 7일_

**향상된 보안 기능**

* 디렉토리 순회 공격으로부터 보호를 강화하기 위해 보안 문제를 해결했습니다. (NEO-28547)

**개선 사항**

*  Flash의 수명이 종료됨에 따라 관련된 모든 캠페인 기능과 구성 요소에서 제거되고 HTML5로 대체되었습니다. 차트의 **측정** 유형이 제거되었습니다. (NEO-30330) [자세히 보기](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html?lang=ko)
* 이제 Windows에 클라이언트 콘솔을 설치할 때 설치 관리자에서 상위 레지스트리 노드가 있는지 확인하고 누락된 경우 생성합니다. 따라서 콘솔을 시작할 때 발생할 수 있는 문제가 방지됩니다. (NEO-34854)
* 타사 도구(이메일 클라이언트, 인터넷 브라우저 등)와 연결된 오류를 방지하기 위해 추적 서명 기능이 개선되었습니다. 특수 문자를 처리합니다. 이제 URL 매개 변수가 인코딩됩니다.

**기타 변경 사항**

* 이전에 더 이상 사용되지 않는 Microsoft CRM 커넥터(Office 365 및 On-premise 배포)가 인터페이스에서 제거되었습니다. [자세히 보기](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=ko#configure-acc-for-microsoft)
* Tomcat 8로 마이그레이션한 후 IIS 통합 문제를 해결하기 위해 IIS 설정 스크립트가 업데이트되었습니다. (NEO-31019)
* [과금 기술 워크플로우](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html?lang=ko#billing-report)를 마케팅 인스턴스에서만 실행할 수 있도록 하기 위해 가드레일이 추가되었습니다.
* 데이터 소스 식별이 워크플로우 전환 **모집단 보기** 창의 데이터 및 스키마 탭에서 개선되었습니다.
* 데이터베이스 업데이트 문제를 방지하기 위해 누락된 데이터베이스 인덱스가 다음 스키마에 추가되었습니다. xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**패치**

* 오퍼가 게재에 연결되어 있을 때 **핫 클릭** 보고서가 작동하지 않는 문제를 해결했습니다. (NEO-26295)
* **하위 워크플로우** 실행 시 출력 테이블이 생성되지 않는 경우 활동 문제가 해결되었습니다. (NEO-36242)
* **설명 분석** 보고서를 PDF로 내보낼 때 발생하는 다양한 문제를 해결했습니다. (NEO-25847)
* 외부 메일 게재를 사용할 때 전송이 실패하는 문제를 해결했습니다. (NEO-37435)
* 웹 API를 사용하여 Microsoft CRM에 연결할 때 발생하는 오류를 수정했습니다. 기능에 영향을 주지 않았으므로 오류 메시지가 제거되었습니다.
* 미드 서버가 추적 및 마케팅 서버 간의 중계기로 설정되었을 때 추적 로그 중복 제거 문제를 수정했습니다. (NEO-36285)
* Vault가 특정 코드 저장소로 사용되지 않는 회귀 문제를 해결했습니다.
* 수신 전환이 FDA 데이터 소스에서 온 경우 **데이터 보강** 워크플로우 활동에서 변수를 사용할 수 없는 문제를 해결했습니다.
* FFDA로 인해 운영자 그룹 및 권한이 제대로 복제되지 않는 문제를 해결했습니다.
* 게재를 통해 잘못된 구독 취소 링크를 전송할 수 있는 문제를 해결했습니다.
* 업그레이드 후 지속 시간에 영향을 주는 복제 관리 문제를 해결했습니다.
* **핫 클릭**&#x200B;이 표시되지 않는 문제를 해결했습니다.
* 이메일 메시지에서 URL이 손상되는 문제를 해결했습니다.

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
