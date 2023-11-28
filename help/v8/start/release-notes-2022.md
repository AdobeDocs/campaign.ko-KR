---
title: Campaign v8 2022 릴리스 정보
description: 2022 Campaign v8 릴리스의 기능 및 개선 사항 목록
feature: Release Notes
role: User
level: Beginner
exl-id: 76473fa5-48ba-42cf-8664-0dd197833a86
source-git-commit: f463c5747b844544ba561a63e4cb0359c0c258c8
workflow-type: tm+mt
source-wordcount: '1847'
ht-degree: 91%

---

# 2022 릴리스 정보{#2022-rn}

이 페이지에서는 **2022 Campaign v8 릴리스**&#x200B;의 새로운 기능, 개선 사항, 버그 해결 사항 목록을 확인할 수 있습니다.

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
<th> <strong>X(이전의 Twitter) 채널 가용성</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>다음 <a href="../send/twitter.md">X 소셜 채널</a> 는 이제 Campaign v8에서 사용할 수 있습니다. 다음을 수행할 수 있습니다.</p>
<ul> 
<li><p>X에서 메시지 보내기(이전의 Twitter): Adobe Campaign을 사용하면 메시지를 X 계정에 직접 게시할 수 있습니다. 모든 팔로워에게 직접 메시지를 보낼 수도 있습니다.
</p></li>
<li><p>새 연락처 수집: Adobe Campaign은 프로필 데이터를 자동으로 복구하여 타겟팅 캠페인을 수행하고 크로스 채널 전략을 구현할 수 있습니다.
</p></li>
</ul>
<p>에서 Campaign과 X를 연결하는 방법을 알아봅니다. <a href="../connect/ac-tw.md">자세한 설명서</a>.</p>
<p>에서 Campaign을 사용하여 게시물을 만들고 다이렉트 메시지를 보내는 방법을 배웁니다. <a href="../connect/ac-tw.md">이 페이지</a>.</p>
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

* Microsoft Internet Explorer 11의 수명 종료에 따라 콘솔 환경에서 HTML 렌더링 엔진은 이제 **Microsoft Edge Chromium**&#x200B;을 사용합니다. 또한 설치 **Microsoft Edge WebView 2** 이제 모든 클라이언트 콘솔 설치에 런타임이 필요합니다.
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
* **쿼리** 활동을 사용하고 테이블을 필터링할 때를 발생하는 문제를 해결했습니다. 열 이름에 &quot;Update&quot;라는 단어가 포함된 경우 잘못된 식별자와 &quot;업데이트된 행의 수&quot;라는 메시지와 함께 편집 오류가 발생했습니다. (NEO-46485)
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
* **쿼리** 활동을 사용하고 테이블을 필터링할 때를 발생하는 문제를 해결했습니다. 열 이름에 &quot;Update&quot;라는 단어가 포함된 경우 잘못된 식별자와 &quot;업데이트된 행의 수&quot;라는 메시지와 함께 편집 오류가 발생했습니다. (NEO-46485)
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
