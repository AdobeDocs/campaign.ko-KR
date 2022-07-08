---
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 39edd6c60c220118f34cd476b887194e1e7763e4
workflow-type: ht
source-wordcount: '2161'
ht-degree: 100%

---

# 최신 릴리스{#latest-release}

이 페이지에서는 **최신 Campaign v8 릴리스**&#x200B;의 새로운 기능, 개선 사항 및 버그 해결 사항 목록을 확인할 수 있습니다.

## 릴리스 8.3.8 {#release-8-3-8}

_2022년 5월 18일_

**새로운 기능**


<table> 
<thead>
<tr> 
<th> <strong>시간 구분 알림</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>iOS 15에서 Apple은 알림이 긴급하다고 간주되어 사용자에게 실시간으로 연락해야 할 때 앱 개발자에게 포커스 모드를 무시하도록 제어하는 긴급한 알림 개념을 추가했습니다.</p>
<p>자세한 내용은 <a href="../send/push.md#send-notifications-on-ios">세부 설명서</a>를 참조하세요.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>핵심 개인 정보 보호 통합</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>이제 Campaign v8이 Adobe 개인 정보 보호 핵심 서비스와 통합됩니다. 개인 정보 보호 핵심 서비스에서 모든 Experience Cloud 솔루션으로 푸시된 개인 정보 보호 요청은 전용 워크플로우를 통해 Campaign에서 자동으로 처리됩니다.</p>
<p>자세한 내용은 <a href="privacy.md">세부 설명서</a>를 참조하세요.</p>
</td> 
</tr> 
</tbody> 
</table>


<table>
<thead>
<tr>
<th><strong>응답 매니저</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>캠페인 응답 관리를 사용하면 마케팅 캠페인의 성공 및 ROI를 측정하거나 이메일, 모바일, DM 등 모든 채널에서 제안을 제공할 수 있습니다.</p>
<p>자세한 내용은 <a href="../start/campaigns.md#response-manager-add-on">세부 설명서</a>를 참조하세요.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>분산 마케팅</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>캠페인 분산 마케팅을 사용하면 중앙 엔터티(본사, 마케팅 부서 등) 및 지역 엔터티(영업 지점, 지역 에이전시 등) 간의 공동 캠페인을 실시할 수 있습니다. 공유 작업 공간(캠페인 패키지)을 통해 캠페인 템플릿을 만들고 로컬 엔티티에 제안할 수 있습니다.</p>
<p>자세한 내용은 <a href="../start/campaigns.md#distributed-marketing-add-on">세부 설명서</a>를 참조하세요.</p>
</td> 
</tr> 
</tbody> 
</table>

**호환성 업데이트**

* 이제 Campaign v8 SDK는 푸시 알림용 Android 12 및 iOS 15를 지원합니다.
* 이제 Campaign v8이 Windows 11과 호환됩니다.

[캠페인 호환성 매트릭스](compatibility-matrix.md)를 참조하십시오.

**개선 사항**

* 이제 Campaign에서 POP3용 Microsoft Exchange Online OAuth 2.0 인증이 지원됩니다. [자세히 보기](../config/external-accounts.md#bounce-mails-external-account)
* Microsoft Dynamics Connector 웹 API에 대해 중요한 문제를 해결했습니다.
* 사용자가 연산자(xtk:operator) 및 연산자 그룹(xtk:group) 스키마를 삽입, 업데이트 및 삭제할 수 있도록 하기 위해 이름이 right인 새로운 연산자 및 그룹 스키마 쓰기(operatorWrite)가 추가되었습니다.

<!--* You can now enable the Email BCC (blind carbon copy) capability to store emails sent by Campaign at the delivery level, through the dedicated option in the delivery properties. [Read more](../config/email-settings.md#email-bcc)-->
<!--* To ensure better performances, a new "Split" option is now activated by default in the Routing external account. This option allows messages to be automatically split across your mid-sourcing instances in order to be delivered faster to the recipients.-->
* 이제 단일 중간 소싱에 여러 LINE 활성 계정을 구성할 수 있습니다.
* 웹 프로세스에 대한 기본 연결 수가 50개에서 150개로 증가했습니다.
* Campaign에는 Snowflake 데이터베이스에 중복되는 키가 삽입되지 않도록 하는 새 보호 기능 세트가 포함되어 있습니다. [자세히 보기](../architecture/keys.md)

**패치**

* 동일한 반복 게재에서 시드 및 컨트롤 그룹을 사용할 때 발생하는 문제를 해결했습니다. (NEO-41197)
* 개인화 블록에 이러한 문자(`' & < > "`) 중 하나가 들어 있을 때 전송 프로세스(최대 256개) 중에 동일한 deliveryPart에 속하는 모든 수신자에 대해 이메일 전송이 차단되는 FFDA 문제를 해결했습니다. 이제 이러한 문자가 개인화 블록에서 지원됩니다(예: firstname=&quot;Brian O&#39;Neil&quot;) (NEO-43184)
* 사용자 지정 스키마를 대상 매핑으로 사용할 때 추적 워크플로우가 실패하는 문제를 해결했습니다. 이제 대상 매핑 마법사를 통해 broadLog 스키마를 생성할 때 사용자 지정 타깃팅 스키마에 대한 외부 링크 유형이 올바른지 확인합니다. (NEO-43506)
* 영어 이외 언어에 대해 FFDA 배포 워크플로우가 실패할 수 있는 문제를 해결했습니다. (NEO-44561)

## 릴리스 8.2.10 {#release-8-2-10}

_2022년 2월 2일_

**패치**

* 유형화 규칙에서 정의한 최대 메시지 수에 도달하면 게재 준비가 실패하는 문제를 해결했습니다.
* 이메일 주소에 문자 &quot;s&quot;가 포함되어 있는 경우 Adobe Analytics 커넥터 구성 중 발생하는 문제를 해결했습니다.
* 업그레이드 후 게재 매핑 테이블에서 사용자 지정 게재 매핑의 데이터가 소실되는 문제를 해결했습니다.
* 이메일 주소에 작은따옴표(&#39;)가 포함된 경우 수신자가 동일한 게재에서 동일한 메시지를 여러 번 받을 수 있는 문제를 해결했습니다. 이제 이 문자를 이스케이프 처리합니다. (NEO-41198)
* 시드 또는 대체 주소로 증명을 보낼 때 발생하는 ID 생성 문제를 해결했습니다. (NEO-42637)
* 주소 대체 방법을 사용하여 증명을 보낼 수 없는 문제를 해결했습니다. (NEO-40417)
* LINE 패키지를 설치하지 못하는 문제를 해결했습니다. (NEO-42503)

## 릴리스 8.2.8 {#release-8-2-8}

_2021년 10월 28일_

<table>
<thead>
<tr>
<th><strong>인바운드 상호 작용</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>이제 인바운드 채널에 대해 실시간 상호 작용 관리를 사용할 수 있습니다. Campaign 인바운드 상호 작용 모듈로 고객이 웹사이트를 방문하거나 콜센터에 연락할 때 고객에게 최상의 오퍼를 제공할 수 있습니다. 이 기능은 Campaign v8과 함께 선택 기능으로 제공되며, 인스턴스에서 특정 구성을 진행해야 합니다. 인바운드 상호 작용 모듈에 대한 액세스 권한을 받으려면 Adobe 담당자에게 문의하세요.</p>
<p>자세한 내용은 <a href="../interaction/interaction-architecture.md">세부 설명서</a>를 참조하세요.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Campaign 최적화</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>이제 Campaign 최적화 모듈을 사용할 수 있습니다. 이 모듈로 게재 전송을 제어, 필터링 및 모니터링할 수 있습니다. 캠페인 간의 충돌을 방지하기 위해 Adobe Campaign은 특정 제한 조건을 적용하여 다양한 조합을 테스트할 수 있습니다. 이를 통해 회사 커뮤니케이션 정책을 준수하면서 고객의 요구 사항과 기대치에 가장 적합한 메시지를 보내도록 보장합니다.</p>
<p>자세한 내용은 관련 <a href="https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=ko">Campaign Classic v7 설명서</a>를 참조하세요.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>단일성 서비스</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>[단일성 서비스]는 [클라우드 데이터베이스 관리자]의 새로운 구성 요소입니다. [클라우드 데이터베이스] 테이블 내에서 고유 키 제약 조건의 무결성을 유지 및 모니터링하는 데 도움이 됩니다. 이를 통해 중복 키를 삽입할 위험을 줄일 수 있습니다.
<p>[클라우드 데이터베이스]는 단일성 제약 조건을 적용하지 않으므로, [단일성 서비스]는 애플리케이션 수준에서 <b>여러 새로운 가드레일</b>을 도입함으로써 Adobe Campaign으로 데이터를 관리할 때 중복 키를 삽입하는 위험을 줄여 줍니다.</p> 
<p>[단일성 서비스]는 <b>ffdaUnicity</b>라는 새로운 내장 워크플로우를 시작하여 단일성 제약 조건 및 중복이 검색되었을 때의 경고를 모니터링합니다.</p>
<p>자세한 내용은 <a href="../architecture/keys.md">세부 설명서</a>를 참조하세요.</p>
</td> </tr> 
</tbody> 
</table>

<!--
<table> 
<thead>
<tr> 
<th> <strong>Twitter channel availability</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>The <a href="../send/twitter.md">Twitter social channel</a> is now available with Campaign v8. You can:</p>
<ul> 
<li><p>Send messages on Twitter: Adobe Campaign lets you post messages directly to your twitter account. You can also send direct messages to all your followers.
</p></li>
<li><p>Collect new contacts: Adobe Campaign can automatically recovers the profile data, which enables you to carry out targeting campaigns and implement cross-channel strategies.
</p></li>
</ul>
<p>Learn how to connect Campaign and Twitter in the <a href="../connect/ac-tw.md">detailed documentation</a>.</p>
<p>Learn how to post tweets and send direct messages with Campaign in <a href="../connect/ac-tw.md">this page</a>.</p>
</td> 
</tr> 
</tbody> 
</table>
-->

**개선 사항**

* Snowflake 커넥터의 성능을 개선했습니다.
* 모니터링 및 테스트 목적으로, 이제 **[!UICONTROL Replicate Staging data]** 워크플로우의 감사 로그에 FFDA(Full Federated Data Access) 데이터베이스로 보낸 레코드의 수가 포함됩니다.
* 이제 SQL 코드 활동에서 SQL 스크립트를 저장할 데이터베이스를 기본 데이터 소스 또는 선택한 활성 FDA 외부 계정 중 선택할 수 있습니다.
* 이제 사전 정의된 여러 웨어하우스를 사용할 수 있으며, 이를 세분화, ETL 또는 최고점 등 다양한 쿼리를 동시에 실행하는 데 사용할 수 있습니다. [자세히 표시](../config/workflows.md)

**기타 변경 사항**

* **[!UICONTROL Encrypted identifier]** 필드가 방문자 스키마(`nms:visitor`)에 추가되었습니다. 이 필드는 계산되며 웹 애플리케이션에 사용할 수 있습니다.
* 일부 IP 관심도가 일부 미드소싱 컨테이너에 존재하지만 전체에 있지는 않은 경우 게재 분석이 실패하는 문제를 해결했습니다. 이제 IP 관심도가 모두 데이터베이스에 저장되므로 모든 컨테이너가 다른 모든 컨테이너의 관심도에 액세스할 수 있습니다. (NEO-37564)
* 이제 여러 스키마와 탐색 트리 노드가 있는 패키지를 가져올 수 있습니다.

**패치**

* 사용자가 데이터 스키마에서 테이블 정의 요소의 `<autoStg>` 속성을 제거하거나 값을 `true`에서 `false`(으)로 변경해도 관련 스테이징 테이블이 삭제되지 않는 문제가 있었습니다. 이 문제를 해결했습니다.
* FFDA 데이터 소스를 사용한 ID 관리로 인해 전용 양식으로 레코드를 만들 때 오류가 발생하는 문제를 해결했습니다.
* 워크플로우에서 강화 활동으로 관리하는 오퍼가 게재에 삽입되지 않는 문제를 해결했습니다.
* 패키지 가져오기 속도를 저하시킬 수 있는 문제를 해결했습니다.
* 시드 주소를 사용한 이메일 게재를 보내지 못하는 문제를 해결했습니다.
* 오퍼 제안 테이블에서 제안이 저장되지 않는 문제를 해결했습니다.
* 네트워크 시간 초과 문제가 네트워크 오류가 아닌 스크립트 중단 문제로 잘못 기록되는 문제를 해결했습니다. 이 문제는 JavaScript 활동에 포함된 HTTP 요청의 경우에 발생했습니다.
* 오퍼가 Snowflake의 라이브 오퍼 환경에서 재현되지 않는 문제를 해결했습니다.
* 확장이 적용되지 않은 기본 제공 스키마에 대해 &#39;autoStg&#39; 속성을 무시하던 문제를 해결했습니다.
* 사용자가 프로필을 미리 볼 때 **[!UICONTROL Country/Region]** 링크를 선택할 수 없는 문제를 해결했습니다.
* 사용자 지정 보고서에서 데이터 선택기를 사용하면 스크립트 오류가 발생하는 문제를 해결했습니다. (NEO-36345)
* 구성 파일이 잘못된 경우 구성을 다시 생성할 때 시스템이 충돌하는 문제를 해결했습니다.
* 마케팅 및 제어 인스턴스가 성공적으로 업그레이드되지 않는 문제를 해결했습니다.
* 마케팅 인스턴스에서 과금 워크플로우가 충돌할 수 있는 문제를 해결했습니다.
* FFDA Snowflake 기본 제공 테이블에서 키가 중복될 수 있는 문제를 해결했습니다. (NEO-38583)
* 두 개의 중복 제거 활동을 차례로 편집할 때 워크플로우 임시 스키마가 누락될 수 있는 문제를 해결했습니다. (NEO-34063)
* Amazon Redshift HoursDiff 및 MinutesDiff 함수를 실행할 때 시간 구성 요소를 추출하려 하는 중 잘못된 결과를 반환하는 문제를 해결했습니다.(NEO-31673)
* 프록시 구성 문제로 인해 사용자가 콘솔에 로그인하지 못하는 문제를 해결했습니다. (NEO-38388)
* **폴더 제거** 기능이 제대로 작동하지 못하게 하는 회귀 문제를 해결했습니다. (NEO-37459)
* 워크플로우에 첨부된 모바일 게재를 미리 볼 수 없는 문제를 해결했습니다.
* 목록의 신원이 데이터베이스에서 음수 ID로 지정되어 있는 경우 **목록 읽기** 워크플로우가 작동하지 않는 문제를 해결했습니다. (NEO-39607)

## 릴리스 8.1.20 {#release-8-1-20}

_2021년 9월 7일_

**향상된 보안 기능**

* 디렉토리 순회 공격으로부터 보호를 강화하기 위해 보안 문제를 해결했습니다. (NEO-28547)

**개선 사항**

* 수명 종료에 따라 Flash를 Campaign의 기능과 구성 요소에서 제거하고 HTML5로 대체했습니다. 차트의 **측정** 유형이 제거되었습니다. (NEO-30330) [자세히 보기](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html?lang=ko)
* 이제 Windows에 클라이언트 콘솔을 설치할 때 설치 관리자에서 상위 레지스트리 노드가 있는지 확인하고 누락된 경우 클라이언트 콘솔을 만듭니다. 따라서 콘솔을 시작할 때 발생할 수 있는 문제를 방지할 수 있습니다. (NEO-34854)
* 서드파티 도구(이메일 클라이언트, 인터넷 브라우저 등)의 특수문자 처리 방식과 관련된 오류를 방지하기 위해 추적 서명 기능이  개선되었습니다. 이제 URL 매개 변수가 인코딩됩니다.

**기타 변경 사항**

* 이전에 사용 종료된 Microsoft CRM 커넥터(Office 365 및 온프레미스 배포)를 인터페이스에서 제거했습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=ko#configure-acc-for-microsoft)
* Tomcat 8로 마이그레이션한 후 IIS 설정 스크립트를 업데이트하여 IIS 통합 문제를 해결했습니다. (NEO-31019)
* [청구 기술 워크플로우](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html?lang=ko#billing-report)를 마케팅 인스턴스에서만 실행할 수 있도록 하기 위해 가드레일이 추가되었습니다.
* 워크플로우 전환의 **모집단 보기** 창에서 데이터 및 스키마 탭에서 데이터 소스 식별이 개선되었습니다.
* 데이터베이스 업데이트 문제를 방지하기 위해 누락된 데이터베이스 인덱스가 xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl 스키마에 추가되었습니다. 

**패치**

* 오퍼가 게재에 연결되어 있을 때 **핫 클릭** 보고서가 작동하지 않는 문제를 해결했습니다. (NEO-26295)
* 실행 시 출력 테이블이 생성되지 않는 경우 발생하는 **하위 워크플로우** 활동 문제를 해결했습니다. (NEO-36242)
* **설명 분석** 보고서를 PDF로 내보낼 때 발생하는 다양한 문제를 해결했습니다. (NEO-25847)
* 외부 메일 전송을 사용할 때 게재 실패를 유발할 수 있는 문제를 해결했습니다. (NEO-37435)
* 웹 API를 사용하여 Microsoft CRM에 연결할 때 발생하는 오류를 수정했습니다. 기능에 영향을 주지 않으므로 오류 메시지를 제거했습니다.
* 추적과 마케팅 서버 간의 중계기로 Mid 서버가 설정되었을 때 발생하는 추적 로그 중복 제거 문제를 수정했습니다. (NEO-36285)
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
