---
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 074a35acdeb45574f38247156ce777ae149e36f7
workflow-type: tm+mt
source-wordcount: '3820'
ht-degree: 92%

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

## 릴리스 8.4.2 {#release-8-4-2}

_2022년 10월 28일_

**개선 사항**

* Adobe Campaign Enhanced MTA를 사용할 때 성공 게재 표시기가 올바르게 업데이트되지 않는 문제를 수정했습니다. (NEO-50462)

## 릴리스 8.4.1 {#release-8-4-1}

_2022년 9월 30일_

**새로운 기능**

<table> 
<thead>
<tr> 
<th> <strong>Adobe Experience Platform과 Adobe Campaign 통합</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>이제 새로운 대상 및 소스 커넥터를 사용하여 Adobe Campaign과 Adobe Experience Platform 간의 원활한 통합을 수행할 수 있습니다.</p>
<ul><li>Adobe Campaign Managed Cloud Services 대상 커넥터를 사용하여 활성화를 위해 Experience Platform 세그먼트를 Adobe Campaign으로 보낼 수 있습니다.</li>
<li>Adobe Campaign Managed Cloud 소스 커넥터를 사용하여 Adobe Campaign 게재 및 추적 로그를 Adobe Experience Platform으로 보낼 수 있습니다.</li>
</ul>
<p>자세한 내용은 <a href="../connect/ac-aep.md">세부 설명서</a>를 참조하세요.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Twitter 채널 가용성</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p><a href="../send/twitter.md">Twitter 소셜 채널</a>은 이제 Campaign v8에서 사용할 수 있습니다. 다음을 수행할 수 있습니다.</p>
<ul> 
<li><p>Twitter에서 메시지 보내기: Adobe Campaign을 사용하면 Twitter 계정에 직접 메시지를 게시할 수 있습니다. 모든 팔로워에게 직접 메시지를 보낼 수도 있습니다.
</p></li>
<li><p>새 연락처 수집: Adobe Campaign은 프로필 데이터를 자동으로 복구하여 타겟팅 캠페인을 수행하고 크로스 채널 전략을 구현할 수 있습니다.
</p></li>
</ul>
<p><a href="../connect/ac-tw.md">세부 설명서</a>에서 Campaign 및 Twitter를 연결하는 방법을 알아봅니다.</p>
<p><a href="../connect/ac-tw.md">이 페이지</a>에서 캠페인을 통해 Twitter에 메세지를 게시하고 다이렉트 메시지를 보내는 방법에 대해 자세히 알아보십시오.</p>
</td> 
</tr> 
</tbody> 
</table>

**보안 개선**

보안을 최적화하기 위해 Campaign에서 생성한 URL에서 보안 토큰이 제거되었습니다.

* 이러한 변경 사항은 GET URL에만 적용됩니다. POST URL을 포함한 다른 유형은 영향을 받지 않습니다.
* 사용자 지정 코드를 사용하는 경우 보안 토큰은 더 이상 GET URL 보안 토큰 매개 변수에서 검색되지 않습니다. 다음의 JSSP 코드를 사용하여 새로운 보안 토큰을 생성해야 합니다.

   ```getNewSecurityToken(jsspContext.getSessionToken(), jsspContext.getSecurityToken(), true);```

   로그인 API를 사용하여 보안 토큰을 가져올 수도 있습니다.
* 세션 토큰 관리에는 변경 사항이 없습니다.

**개선 사항**

* Microsoft Internet Explorer 11의 수명 종료에 따라 콘솔 환경에서 HTML 렌더링 엔진은 이제 **Microsoft Edge Chromium**&#x200B;을 사용합니다. 또한 클라이언트 콘솔을 설치하려면 이제 **Microsoft Edge WebView 2** 런타임을 설치해야 합니다.
* 워크플로우 고가용성을 사용하여 워크플로우 실행을 개선하여 여러 컨테이너에서 동시에 워크플로우를 실행하여 워크플로우 서비스 손실과 관련 실행 오류를 방지할 수 있습니다. **참고**: 이 새로운 기능은 일부 고객에게만 제한된 가용성으로 제공됩니다.
* 이제 지정된 개인 정보 보호 네임스페이스에 대해 개인 정보 보호 요청이 일괄적으로 수행됩니다. 이러한 개선 사항으로 GDPR/개인 정보 보호 삭제 요청에 대한 실행 시간이 늘어납니다.

**호환성 업데이트**

* 이제 Campaign v8 SDK는 푸시 알림용 iOS 16을 지원합니다.

[캠페인 호환성 매트릭스](compatibility-matrix.md)를 참조하십시오.

**패치**

* FeatureFlag_GZIP_Compression 옵션이 활성화된 경우 MID 인스턴스에서 게재 로그 상태 업데이트에 영향을 주는 문제를 수정했습니다. (NEO-49183)
* 연락 날짜가 도래한 경우에도 게재가 **보류 중**&#x200B;인 상태로 계속 유지될 수 있는 문제를 해결했습니다. (NEO-48079)
* **데이터 로드(파일)** 활동을 사용할 때 서버에서 파일이 업데이트되지 않는 워크플로우 문제를 해결했습니다. 프로세스가 100%에서 중단되었지만 종료되지 않았습니다. (NEO-47269)
* 일본어 환경에서 업그레이드 후 발생하는 문제를 해결했습니다. (NEO-46640)
* MTA 프로세스 중에 게재가 정확한 크기에 도달할 시 발생할 수 있는 문제를 수정했습니다. (NEO-46097)
* 추적 로그가 수신자의 브라우저와 관련된 데이터를 반환하지 못하는 문제를 해결했습니다. (NEO-46612)
* 외부 게재 모드를 사용하여 SMS 메시지를 보낼 때 개인화 문제가 발생하는 문제를 해결했습니다. (NEO-46415)
* 추적 로그에서 중복을 생성할 수 있는 문제를 해결했습니다. (NEO-46409)
* 실행 중 오류가 발생한 경우에도 **[!UICONTROL Replicate Staging data]**(ffdaReplicateStagingData) 기술 워크플로우가 중지되지 않는 문제를 해결했습니다. (NEO-46280)
* 시드 주소로 증명을 보낼 때 속도가 느려지지 않도록 시드 멤버의 모든 연속 복제가 이제 하나의 복제 요청으로 그룹화됩니다. (NEO-44844)
* 메시지 센터 보관된 이벤트에서 게재를 미리 볼 때 오류가 표시되는 문제를 해결했습니다. (NEO-43620)
* 캠페인 **쿼리** 활동 및 **데이터 소스 변경** 활동을 통해 Snowflake 클라우드 데이터베이스에 데이터를 삽입할 때 발생하는 문제를 해결했습니다. 데이터에 백슬래시 문자가 있을 경우 프로세스가 실패했습니다. 소스 문자열이 이스케이프되지 않았으며 데이터가 Snowflake에서 올바르게 처리되지 않았습니다. (NEO-45549)
* **쿼리** 활동을 사용하고 테이블을 필터링할 때를 발생하는 문제를 해결했습니다. 열 이름에 “Update”라는 단어가 포함된 경우 잘못된 식별자와 “업데이트된 행의 수”라는 메시지와 함께 편집 오류가 발생했습니다. (NEO-46485)
* 이제 다음 **데이터베이스 정리** 기술 워크플로우가 사용자 지정 스테이징 스키마도 처리합니다. (NEO-48974)
* 대량의 수신자를 타겟팅할 때 차단 목록에 추가된 수신자를 제외하는 동안 게재 분석 속도가 느려질 수 있는 문제를 해결했습니다. (NEO-48019)
* SOAP 호출 중에 잘못된 XML 문자열을 처리할 때 안정성을 개선했습니다. (NEO-48027)
* 게재에서 달력 및 분할 모드를 사용할 때 불필요한 DeliveryParts가 발생하는 문제를 해결했습니다. (NEO-48634)
* 달력 기반 웨이브를 사용할 때 발생하는 성능 문제를 해결했습니다. (NEO-48451)
* 사용자 지정 스키마에 새 대상 매핑을 만든 후 게재 목록 화면에서 오류 메시지가 표시되는 문제를 수정했습니다. (NEO-49237)
* 스테이징 워크플로우가 오류이고 보존 기간이 완전히 지난 경우 데이터 손실이 발생할 수 있는 문제를 해결했습니다. (NEO-48975)

## 릴리스 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> 클라이언트 콘솔 업그레이드는 필수입니다. 이 [페이지](../start/connect.md#download-ac-console)에서 클라이언트 콘솔을 업그레이드하는 방법을 알아보십시오.

_2022년 10월 7일_

**개선 사항**

* FeatureFlag_GZIP_Compression 옵션이 활성화된 경우 MID 인스턴스에서 게재 로그 상태 업데이트에 영향을 주는 문제를 수정했습니다. (NEO-49183)
* 이제 **데이터베이스 정리** 기술 워크플로우가 사용자 지정 스테이징 스키마도 처리합니다. (NEO-48974)
* 연락 날짜가 도래한 경우에도 게재가 **보류 중**&#x200B;인 상태로 계속 유지될 수 있는 문제를 해결했습니다. (NEO-48079, NEO-48251)
* SOAP 호출 중에 잘못된 XML 문자열을 처리할 때 안정성을 개선했습니다. (NEO-48027)
* 대량의 수신자를 타겟팅할 때 차단 목록에 추가된 수신자를 제외하는 동안 게재 분석 속도가 느려질 수 있는 문제를 해결했습니다. (NEO-48019)
* 시드 주소로 증명을 보낼 때 속도가 느려지지 않도록 시드 멤버의 모든 연속 복제가 이제 하나의 복제 요청으로 그룹화됩니다. (NEO-44844)
* 외부 게재 모드를 사용하여 SMS 메시지를 보낼 때 개인화 문제가 발생하는 문제를 해결했습니다. (NEO-46415)
* 메시지 센터 보관된 이벤트에서 게재를 미리 볼 때 오류가 표시되는 문제를 해결했습니다. (NEO-43620)
* **데이터 로드(파일)** 활동을 사용할 때 서버에서 파일이 업데이트되지 않는 워크플로우 문제를 해결했습니다. 프로세스가 100%에서 중단되었지만 종료되지 않았습니다. (NEO-47269)
* 게재에서 달력 및 분할 모드를 사용할 때 불필요한 DeliveryParts가 발생하는 문제를 해결했습니다. (NEO-48634)
* 달력 기반 웨이브를 사용할 때 발생하는 성능 문제를 해결했습니다. (NEO-48451)
* 사용자 지정 스키마에 새 대상 매핑을 만든 후 게재 목록 화면에서 오류 메시지가 표시되는 문제를 수정했습니다. (NEO-49237)
* MTA 프로세스 중에 게재가 정확한 크기에 도달할 시 발생할 수 있는 문제를 수정했습니다. (NEO-46097)
* 추적 로그가 수신자의 브라우저와 관련된 데이터를 반환하지 못하는 문제를 해결했습니다. (NEO-46612)
* 일본어 환경에서 업그레이드 후 발생하는 문제를 해결했습니다. (NEO-46640)
* **쿼리** 활동을 사용하고 테이블을 필터링할 때를 발생하는 문제를 해결했습니다. 열 이름에 “Update”라는 단어가 포함된 경우 잘못된 식별자와 “업데이트된 행의 수”라는 메시지와 함께 편집 오류가 발생했습니다. (NEO-46485)
* 실행 중 오류가 발생한 경우에도 **[!UICONTROL Replicate Staging data]**(ffdaReplicateStagingData) 기술 워크플로우가 중지되지 않는 문제를 해결했습니다. (NEO-46280)
* 스테이징 워크플로우가 오류이고 보존 기간이 완전히 지난 경우 데이터 손실이 발생할 수 있는 문제를 해결했습니다. (NEO-48975)
* 캠페인 **쿼리** 활동 및 **데이터 소스 변경** 활동을 통해 Snowflake 클라우드 데이터베이스에 데이터를 삽입할 때 발생하는 문제를 해결했습니다. 데이터에 백슬래시 문자가 있을 경우 프로세스가 실패했습니다. 소스 문자열이 이스케이프되지 않았으며 데이터가 Snowflake에서 올바르게 처리되지 않았습니다. (NEO-45549)

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
<p>자세한 내용은 <a href="https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=ko#campaign-optimization">세부 설명서</a>를 참조하세요.</p>
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
