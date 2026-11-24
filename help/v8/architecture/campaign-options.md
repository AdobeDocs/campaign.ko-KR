---
title: 캠페인 옵션
description: Campaign 옵션의 정의, 저장 위치 및 Campaign v8에 대해 문서화된 옵션의 사용 방법을 알아봅니다.
feature: Architecture
role: Admin, Developer
level: Intermediate
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: bae31391-3416-5fbd-bc4b-2cdcae2922db
    internal-label: Architecture
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 92bab89570eca3eb13d6010db0deec74e7860c91
workflow-type: tm+mt
source-wordcount: '2849'
ht-degree: 3%
---
# 캠페인 옵션 {#campaign-options}

옵션은 Campaign 인스턴스의 동작 방식을 제어하는 매개 변수입니다(예: 이메일 이미지 기본 크기 제한, 동시에 실행되는 워크플로 수 또는 게재 템플릿의 기본 라우팅 공급자). 일부 옵션은 기본적으로 제공되며, 다른 옵션은 필요할 때 생성됩니다. 사용 가능한 옵션은 인스턴스에 설치된 패키지에 따라 다릅니다. [기본 제공 패키지](built-in-packages.md)에서 자세히 알아보세요.

>[!CAUTION]
>
>Campaign 설명서에 설명된 옵션만 수정합니다. 문서화되지 않은 옵션은 내부용이며 수정해서는 안 됩니다. 수정 옵션은 전문가 사용자용으로 예약되어 있습니다.

## 옵션이 저장되는 위치 {#where-options-are-stored}

옵션은 **xtkOption** 테이블(스키마 **xtk:option**)의 Campaign 데이터베이스에 저장됩니다. Campaign 탐색기에서 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**&#x200B;에서 사용할 수 있습니다. Campaign 웹 사용자 인터페이스에서 **[!UICONTROL Administration]** > **[!UICONTROL Options]**&#x200B;에서 사용할 수 있습니다. 두 목록은 동일합니다. [Campaign 옵션 구성](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options){target="_blank"}에서 자세히 알아보세요.

## 옵션 사용 {#use-options}

1. Campaign 탐색기에서 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**(으)로 이동합니다.
1. 옵션을 선택한 다음 해당 값을 업데이트합니다. 옵션이 없는 경우 설명서에 지정된 정확한 이름으로 만듭니다.
1. 설명서에서 예상하는 유형의 값을 설정합니다. 예를 들어 CRM 동기화 날짜에 대한 텍스트 옵션 또는 워크플로우 다시 시작 지연에 대한 정수 옵션 중에서 선택할 수 있습니다.

예를 들어 워크플로우의 중간 데이터를 저장하는 등의 고유한 옵션을 만들 수도 있습니다. 이름을 입력하고 데이터 유형을 선택한 다음 값을 설정합니다. [Campaign 옵션 구성](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options#create){target="_blank"}에서 자세히 알아보세요.

일부 옵션은 자격 증명을 보유합니다. [Campaign 및 Adobe Experience Platform 랜딩 페이지 작업](../connect/ac-aep-landing-pages.md)에 설명된 대로 `cryptString` 함수로 암호를 암호화합니다. 자격 증명을 회전할 때는 옵션에 저장된 자격 증명도 회전합니다. 자세한 내용은 [자격 증명 회전 가이드](../../technotes/security/credential-rotation-guide.md#ac-options-credentials)를 참조하세요.

## 워크플로우 및 개인화의 옵션 사용 {#use-options-in-processes}

JavaScript 코드, 개인화 및 쿼리에서 옵션 값을 읽고 쓸 수 있습니다.

* **JavaScript 코드**(예: JavaScript 코드 워크플로우 활동: `getOption('OptionName')`은(는) 옵션 값을 반환하고 `setOption('OptionName', value, 'description')`이(가) 설정합니다. 예: `getOption('IMS_ORG_ID')`. [getOption](../../campaign-api/f-getoption.md) 및 [setOption](../../campaign-api/f-setoption.md)에서 자세히 알아보세요.
* **게재 개인화**: `<%@ include option='OptionName' %>`에서 옵션 값을 삽입합니다. 예를 들어 `<%@ include option='NmsServer_URL' %>`은(는) LINE 메시지의 웹 앱에 연결된 링크에 서버 URL을 포함합니다. 자세한 내용은 [Adobe Campaign과 LINE 다이렉트 메시지 보내기](../send/line/line.md)를 참조하세요.
* **쿼리 편집기**: 옵션 값을 사용하려면 **값** 필드에 `$(options:OPTION_NAME)`을(를) 입력하십시오. [쿼리 디자인](../start/design-queries.md)에서 자세히 알아보세요.

## 사용 가능한 옵션 {#available-options}

아래 표에는 영역별로 그룹화된 Campaign v8에서 사용할 수 있는 옵션이 나열되어 있습니다. 설명서의 다른 페이지에서 옵션을 설명하는 경우 해당 옵션이 표로 연결됩니다. 일부 항목은 정보 제공 또는 유지 관리 옵션입니다. 옵션을 나열한다고 해서 변경해도 안전하다는 의미는 아니다.

### 게재 {#delivery-options}

이러한 옵션은 게재 준비 및 전송 방법을 제어합니다. 여기에는 이미지 및 첨부 파일 제한, 기본 라우팅 공급자, 중간 소싱 분할 임계값, 열기 추적 스크립트, 공용 서버 URL, 게재 유효성, 중복 및 지연 게재 처리 및 바코드가 포함됩니다. [파일 첨부](../send/attaching-files.md), [전자 메일 매개 변수](../send/email-parameters.md), [게재 모범 사례](../start/delivery-best-practices.md), [Campaign 아키텍처 시작](architecture.md#split), [전자 메일 추적 픽셀에 대한 지침](../start/cnil-pixel-tracking.md) 및 [DM 메시지 보내기](../send/line/line.md)에서 자세히 알아보세요.

| 옵션 | 설명 |
|---|---|
| NmsDelivery_MaxDownloadedImageSize | 개인화된 URL에서 다운로드되고 이메일에 첨부된 이미지의 최대 크기(바이트)입니다. 기본값은 100,000바이트(100KB)입니다. [자세히 알아보기](../send/attaching-files.md) |
| NmsDelivery_MaxRecommendedAttachments | 경고가 표시되기 전 이메일 또는 트랜잭션 이메일 템플릿의 최대 첨부 파일 수입니다. 기본값은 1입니다. [자세히 알아보기](../send/attaching-files.md) |
| NmsEmail_DefaultErrorAddr | 게재에서 오류 주소를 비워 둘 때 사용되는 인스턴스의 기본 오류 이메일 주소입니다. [자세히 알아보기](../send/email-parameters.md) |
| XtkEmail_Characters | 이메일 주소에 유효한 문자입니다. [자세히 알아보기](../start/delivery-best-practices.md) |
| NmsBroadcast_DefaultProvider | 새 게재 템플릿의 기본 라우팅 공급자입니다. 기본적으로 분할 게재를 사용하려면 분할 외부 계정의 이름으로 설정합니다. [자세히 알아보기](architecture.md#split) |
| NmsDelivery_MultiMidSplitThreshold | 여러 중간 소싱 인스턴스 간에 게재가 분할되는 크기입니다. 기본값은 100K입니다. [자세히 알아보기](architecture.md#split) |
| NmsTracking_OpenFormula | 열린 추적 URL을 계산하는 스크립트. 픽셀 용도당 하나의 옵션을 정의합니다. [자세히 알아보기](../start/cnil-pixel-tracking.md) |
| NmsServer_URL | 공개 웹 애플리케이션 서버의 기본 URL. 예를 들어 LINE 메시지에 웹 앱 링크를 포함하는 데 사용됩니다. [자세히 알아보기](../send/line/line.md) |
| NmsBroadcast_MsgValidityDuration | 게재의 기본 유효 기간(초)입니다. |
| NmsBroadcast_RemoveDuplicatesRecipients | 중복 수신자를 자동으로 무시하려면 1로 설정하십시오. |
| NmsDelivery_ImageServerTimeout | 개인화된 URL에서 다운로드하고 이메일에 첨부된 이미지를 검색할 때 서버에서 응답을 가져오는 시간 제한(초)입니다. 시간이 초과되면 메시지를 보낼 수 없습니다. 기본값은 60초입니다. |
| NmsDeliveryWizard_ShowDeliveryWeight | 게재 도우미에 메시지 가중치를 표시합니다. |
| NmsMTA_Alert_Delay | 지연, 분 단위, 그 이후 게재가 지연된 것으로 간주됩니다. 기본값은 30분입니다. |
| NmsServer_MirrorPageUrl | 미러 페이지 서버의 URL. 라우팅 정의에 URL이 지정되지 않은 경우 이메일 게재의 기본값입니다. 기본적으로 추적 서버 URL과 동일합니다. |
| XtkBarcode_SpecialChar | Code128 바코드에 대한 특수 문자 지원을 활성화하거나 비활성화합니다. |
| NMS_ActivateOwnerConfirmation | 게재 시작을 위해 특정 운영자 또는 그룹을 지정한 경우 게재 담당 운영자가 전송을 확인할 수 있도록 1로 설정합니다. 비활성화하려면 0으로 설정합니다. 지정된 운영자, 그룹 또는 관리자만 전송을 확인할 수 있습니다. |
| NmsDelivery_senderAddressMask | 이메일 게재의 보낸 사람 이메일 필드에 허용된 발신자 주소를 쉼표로 구분한 목록입니다. 옵션에 값이 있으면 필드가 드롭다운 목록이 됩니다. 제한 사항은 전역입니다. 모든 브랜드 및 게재 템플릿에 적용되며 정적 주소만 지원합니다. [자세히 알아보기](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options#restrict-sender-address){target="_blank"} |

### 캠페인 및 워크플로우 {#campaign-workflow-options}

이러한 옵션은 캠페인 및 워크플로우의 실행 방식을 제어합니다. 여기에는 전송 소유자 확인, 동시에 처리된 작업 수, 워크플로우 확인 및 자동 재시작 등이 포함됩니다. 또한 SQL 활동 보호, 기본 캠페인 유효성, 내보낸 보고서 로고도 다룹니다. [마케팅 캠페인 게재](../../automation/campaigns/marketing-campaign-deliveries.md), [워크플로우 모범 사례](../../automation/workflow/workflow-best-practices.md), [워크플로우 실행 모니터링](../../automation/workflow/monitor-workflow-execution.md), [워크플로우 속성](../../automation/workflow/workflow-properties.md), [SQL 코드 및 JavaScript 코드](../../automation/workflow/sql-code-and-javascript-code.md#important-notes)에서 자세히 알아보십시오.

| 옵션 | 설명 |
|---|---|
| NmsCampaign_Activate_OwnerConfirmation | 검토자가 정의된 경우에도 캠페인 소유자가 전송을 확인할 수 있도록 만들고 1로 설정합니다. 비활성화하려면 0으로 설정합니다. [자세히 알아보기](../../automation/campaigns/marketing-campaign-deliveries.md) |
| NmsOperation_LimitConcurrency | 캠페인이 동시에 처리하는 최대 게재, 워크플로우, 가설 및 시뮬레이션 작업 수입니다. 기본값은 10입니다. [자세히 알아보기](../../automation/workflow/workflow-best-practices.md) |
| NmsServer_PausedWorkflowPeriod | 일시 중지된 워크플로에 대한 두 확인 사이의 일 수입니다. [자세히 알아보기](../../automation/workflow/monitor-workflow-execution.md) |
| XtkWorkflow_WatchdogRestartTimerTimeout | 워크플로우가 자동으로 선택되고 다시 시작되는 30초 간격을 변경하려면 정수 옵션으로 만듭니다. [자세히 알아보기](../../automation/workflow/workflow-properties.md) |
| XtkSecurity_FeatureFlag_SqlSensitive | 차단된 SQL 메서드에 대한 SQL 코드 활동의 보호를 비활성화하려면 0으로 설정합니다. [자세히 알아보기](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| XtkSecurity_SqlSensitive_Methods | SQL 활동이 차단하거나 경고하는 SQL 메서드 목록입니다. [자세히 알아보기](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| NmsOperation_Duration | 캠페인의 기본 유효 기간(초)입니다. |
| NmsOperation_TimeRange | 예약 모드에서 타겟팅 및 추출 조건에 대한 기간. |
| NmsOperation_OperationMgtDebug | 워크플로우 감사 로그에 operationMgt 기술 워크플로우의 실행 정보를 기록하려면 1로 설정합니다. |
| NmsOperation_DeliveryPreparationWindow | operationMgt 기술 워크플로우에 의해 실행 중인 게재 수에서 불일치 상태의 게재가 제외되는 일 수입니다. 기본값은 7입니다. |
| Workflow_AnalysisThreshold | 테이블 통계가 자동으로 다시 계산되는 영향을 받는 레코드 수입니다. |
| XtkReport_Logo | 내보낸 보고서의 오른쪽 위 모서리에 표시되는 로고입니다. |

### 이메일 기본값 {#email-default-options}

이러한 옵션은 이메일의 기본 발신자 및 회신 주소와 레이블을 정의합니다. Campaign은 게재가 해당 필드를 비워 두면 이를 사용합니다. [전자 메일 매개 변수](../send/email-parameters.md) 및 [게재 템플릿 작업](../send/create-templates.md)에서 자세히 알아보세요.

| 옵션 | 설명 |
|---|---|
| NmsEmail_DefaultFromAddr | 기본 인스턴스의 보낸 사람 주소이며, 게재가 이 주소를 비워 둘 때 사용됩니다. |
| NmsEmail_FromName | 기본 인스턴스의 레이블: 을(를) 지정합니다. 게재가 비어 있을 때 사용됩니다. |
| NmsEmail_DefaultReplyToAddr | 게재에서 비워 둘 때 사용되는 인스턴스의 기본 회신 주소. |
| NmsEmail_ReplyToName | 게재에서 비워 둘 때 사용되는 인스턴스의 기본 회신 레이블입니다. |
| NmsEmail_DefaultErrorAddr | 게재가 인스턴스를 비워 둘 때 사용되는 인스턴스의 기본 오류 주소입니다. [자세히 알아보기](../send/email-parameters.md) |
| NmsDelivery_FromAddressMasks | 메시지를 보낼 때 사용되는 보낸 사람 주소 구문. |
| NmsDelivery_ErrorAddressMasks | 메시지에 회신할 때 사용되는 오류 주소 구문. |
| NmsEmail_ExpOrganization | 수신자에게 표시되는 일부 경고 메시지에 사용되는 조직의 일반 이름. |

### 소프트 오류 및 격리 {#error-options}

이러한 옵션은 일시적인 게재 실패인 소프트 오류 후 수신자를 격리하는 시기를 정의합니다. [Campaign의 격리 관리](../send/quarantines.md#soft-error-management) 및 [Campaign의 게재 실패](../send/delivery-failures.md#retries)에서 자세히 알아보세요.

| 옵션 | 설명 |
|---|---|
| NmsNPAI_EmailMaxError | 수신자가 격리되기 전에 이메일 채널에 허용된 최대 소프트 오류 수. |
| NmsNPAI_EmailSignificantErrorDelay | 새 소프트 오류를 고려하기 전에 이메일 채널에서 이전 소프트 오류 발생 후 경과해야 하는 최소 시간입니다. |
| NmsNPAI_MobileMaxError | 수신자가 격리되기 전에 모바일 채널에서 허용되는 최대 소프트 오류 수. |
| NmsNPAI_MobileSignificantErrorDelay | 새 소프트 오류가 고려되기 전에 모바일 채널에서 이전 소프트 오류 이후 경과해야 하는 최소 시간입니다. |

### 채널 {#channel-options}

이러한 옵션은 DM의 발신자 주소, LINE 및 SMS 채널의 설정 및 인바운드 이메일의 허용된 전달 주소를 정의합니다. 자세한 내용은 [Adobe Campaign과 DM 보내기](../send/direct-mail.md), [Adobe Campaign과 DM 메시지 보내기](../send/line/line.md) 및 [Adobe Campaign과 SMS 보내기](../send/sms/sms.md)를 참조하세요.

| 옵션 | 설명 |
|---|---|
| NmsPaper_SenderLine1, NmsPaper_SenderLine3, NmsPaper_SenderLine4, NmsPaper_SenderLine6, NmsPaper_SenderLine7 | DM 게재 발신자 주소 1, 3, 4, 6, 7행. |
| NmsLine_AESKey | LINE 채널에서 URL을 인코딩하기 위해 lineImage 서블릿에서 사용하는 AES 키입니다. |
| NmsLine_MessageCenterURL | LINE 채널에서 환영 메시지를 보내는 데 사용되는 메시지 센터 서버 URL. |
| NmsSMS_Priority | SMS 게이트웨이로 전송된 보낸 SMS 메시지의 우선 순위입니다. |
| NmsInmail_AllowlistEmails | 인바운드 메일 처리 모듈의 승인된 전달 이메일 주소(쉼표로 구분). 모든 주소를 허용하려면 *를 사용하십시오. |

### 메시지 센터 임계값 {#message-center-options}

이러한 옵션은 트랜잭션 메시지를 트리거하는 실시간 이벤트 처리가 저하될 때 경고나 경고를 발생시키는 임계값을 정의합니다. 각 지표에는 경고 임계값과 경고 임계값이 있습니다. 옵션 이름은 Warning 또는 Alert로 끝납니다(예: MC_RtEventErrorWarning 및 MC_RtEventErrorAlert). [캠페인 트랜잭션 메시지](../send/transactional.md) 및 [캠페인 트랜잭션 메시지 설정](../config/transactional-msg-settings.md)에서 자세히 알아보세요.

| 옵션 이름 접두사 | 지표 |
|---|---|
| MC_RtEventAvgDeliveryTime | 실시간 이벤트의 평균 전송 시간입니다. |
| MC_RtEventAvgProcessTime | 실시간 이벤트의 평균 처리 시간입니다. |
| MC_RtEventAvgQueueTime | 실시간 이벤트의 평균 대기 시간입니다. |
| MC_RtEventAvgQueue | 대기열에 추가된 평균 실시간 이벤트 수입니다. |
| MC_RtEventMaxQueue | 대기열에 추가된 최대 실시간 이벤트 수. |
| MC_RtEventMinQueue | 대기열에 추가된 최소 실시간 이벤트 수. |
| MC_RtEventQueue | 보류 중인 실시간 이벤트 큐. 경고 임계값은 위기 조건입니다. |
| MC_RtEventError | 실시간 이벤트의 처리 오류입니다. |
| MC_RtEventThroughput | 실시간 이벤트의 처리량입니다. |

### 데이터 보존 및 데이터베이스 {#database-options}

정리 워크플로우는 오래된 레코드를 삭제하여 데이터베이스가 커지는 것을 방지합니다. 이러한 옵션은 Campaign에서 각 유형의 데이터를 유지하는 기간을 정의합니다. 인터페이스에서 지연을 변경하면 제거 지연 옵션이 자동으로 만들어집니다. 옵션 목록에서 편집하는 경우 값을 초 단위로 표현합니다. 자세한 내용은 [일반 아키텍처](general-architecture.md) 및 [보안 지침](../config/security.md#consent)을 참조하세요.

관리자만 지우기 지연 옵션을 수정할 수 있습니다. 적절한 값은 환경에 따라 다르므로 인스턴스의 현재 값을 확인하고 범용 기본값을 가정하지 마십시오.

| 옵션 | 설명 |
|---|---|
| NmsCleanup_BroadLogPurgeDelay | 게재 로그(브로드로그)가 지워진 후 지연됩니다. |
| NmsCleanup_TrackingLogPurgeDelay | 추적 로그가 지워지지 않는 지연. |
| NmsCleanup_TrackingStatPurgeDelay | 추적 통계가 지워진 후 지연됩니다. |
| NmsCleanup_EventPurgeDelay | 이후 이벤트가 지워지는 지연. |
| NmsCleanup_EventHistoPurgeDelay | 이벤트 기록이 지워지는 지연 시간. |
| NmsCleanup_EventStatPurgeDelay | 이벤트 통계가 지워진 후 지연됩니다. |
| NmsCleanup_PropositionPurgeDelay | 제안 삭제 후 지연. |
| NmsCleanup_QuarantineMailboxFull | 격리 해제 후 지연. |
| NmsCleanup_RecycedDeliveryPurgeDelay | 재활용 게재가 지워지는 지연 시간. |
| NmsCleanup_RejectPurgeDelay | 거부가 지워지는 지연. |
| NmsCleanup_VisitorPurgeDelay | 방문자가 지워진 후 지연됩니다. |
| NmsCleanup_WorkflowResultPurgeDelay | 워크플로우 결과가 지워지는 지연 시간. |
| WdbcKillSessionPolicy | PostgreSQL에서 워크플로 무조건적 중지의 비헤이비어. 0 (기본값): 데이터베이스에 영향을 주지 않고 워크플로우 프로세스를 중지합니다. 1: 프로세스를 중지하고 쿼리를 취소합니다(pg_cancel_backend). 2: 프로세스를 중지하고 쿼리를 종료합니다(pg_terminate_backend). |
| XtkSequence_AutoGeneration | 이 옵션이 설정된 후 생성된 사용자 정의 스키마에 적용되며, autopk=&quot;true&quot;이고 pkSequence 속성이 없습니다. Campaign은 시퀀스를 자동으로 생성합니다. |

### 메시지 센터 사용자 지정 {#message-center-customization}

이러한 옵션을 사용하면 Campaign에서 실시간 및 배치 이벤트를 강화하고 라우팅하는 방법을 사용자 지정할 수 있습니다. [캠페인 트랜잭션 메시지](../send/transactional.md) 및 [캠페인 트랜잭션 메시지 설정](../config/transactional-msg-settings.md)에서 자세히 알아보세요.

| 옵션 | 설명 |
|---|---|
| MC_EnrichmentCustomJs | 이벤트를 강화하는 JavaScript 라이브러리입니다. 실시간 이벤트에 대해 enrichRtEvents(aiEventId)를 구현하고 배치 이벤트에 대해 enrichBatchEvents(aiEventId)를 구현해야 합니다. 두 함수 모두 이벤트를 보강하고 데이터베이스에 저장합니다. |
| MC_RoutingCustomJs | 이벤트를 라우팅하는 JavaScript 라이브러리입니다. 실시간 또는 일괄 처리 이벤트에 대해 선택한 트랜잭션 메시지의 내부 이름을 반환하는 dispatchRtEvent(iEventId) 및 dispatchBatchEvent(iEventId)를 구현해야 합니다. |
| NmsMessageCenter_RoutingBatchSize | 이벤트 라우팅에 사용된 그룹 크기입니다. |
| NmsTracking_RT_ClickFormula, NmsTracking_RT_OpenFormula | 브랜딩이 활성화될 때 실시간(RT) 게재의 클릭 및 열기 추적에 사용되는 공식입니다. RT 컨트롤 인스턴스에서 구성됩니다. [자세히 알아보기](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/branding/branding-configure){target="_blank"} |
| Branding_RT_ListXtkOptions_toPublish | RT 게재가 적용할 수 있도록 사용자 지정 추적 공식을 포함하는 옵션 목록(쉼표로 구분). [자세히 알아보기](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/branding/branding-configure){target="_blank"} |

### 상호 작용(오퍼 관리) {#interaction-options}

이러한 옵션은 오퍼 관리 모듈인 캠페인 상호 작용에 적용됩니다. 제안 작성 방법과 제어 및 실행 인스턴스의 동기화 방법을 제어합니다. 상호 작용 아키텍처의 [캠페인 상호 작용 - 오퍼 관리](../interaction/interaction.md) 및 [유지 관리 옵션](../interaction/interaction-architecture.md#maintenance-options)에서 자세히 알아보세요.

| 옵션 | 설명 |
|---|---|
| NmsInteraction_UseDaemon | 제안에 대한 비동기 쓰기를 활성화하려면 1로 설정하고 비활성화하려면 0으로 설정합니다. |
| NmsInteraction_MapWorkflowId | 생성된 모든 동기화 워크플로 목록입니다. 제어 인스턴스의 정보 유지 관리 옵션: 수정하지 마십시오. |
| NmsExecutionInstanceId | 실행 인스턴스 식별자. 실행 인스턴스에서 정보 옵션을 사용할 수 있습니다. 수정하지 마십시오. |

다음 옵션도 제어 인스턴스의 유지 관리 옵션입니다.

* **`NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>`**: 특정 인스턴스에서 환경이 마지막으로 동기화된 날짜입니다.
* **`NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>`**: 스키마의 제안이 한 인스턴스에서 다른 인스턴스로 동기화된 마지막 날짜입니다.

>[!CAUTION]
>
>유지 관리 옵션은 특정 유지 관리 경우에만 사용하십시오.

다음 옵션은 엔터프라이즈(FFDA) 배포에서 사용할 수 없는 쿠폰에 적용됩니다. [개인화된 쿠폰](../send/personalized-coupons.md)에서 자세히 알아보세요.

| 옵션 | 설명 |
|---|---|
| NmsModule_CouponsEnabled | 쿠폰을 활성화합니다. |
| NmsCoupons_MaxPerTransac | SQL 트랜잭션당 업데이트된 쿠폰 수입니다. |

### 개인 정보 보호 요청 {#privacy-options}

이러한 옵션은 삭제 확인, 허용되는 오류 수 및 요청 데이터가 유지되는 기간 등 Campaign에서 개인 정보 요청을 처리하는 방법을 제어합니다. [Campaign의 개인 정보 보호 요청 관리](../start/privacy.md)에서 자세히 알아보세요.

| 옵션 | 설명 |
|---|---|
| Privacy_Request_ConfirmDeletePending | 두 번째 단계에서 인터페이스에서 각 삭제를 수동으로 확인하려면 1로 설정하십시오. 그렇지 않으면 데이터가 확인 없이 삭제됩니다. |
| Privacy_Request_ConfirmDeletePendingDelay | 삭제 확인을 기다리는 요청이 취소되는 지연 시간. |
| Privacy_Request_MaxErrorAllow | 개인 정보 요청을 처리하거나 삭제할 때 허용되는 최대 오류 수. |
| Privacy_Request_RemoveDelay | 대기열에서 요청 생성과 해당 데이터 삭제 사이의 지연. |
| realtimeReporting_collectPII | 동적 보고를 위한 PII(개인 식별 정보) 계약 선택. 값 1은 나중에 묻기에 해당하고, 2는 거절에 해당하며, 3은 수락에 해당합니다. [자세히 알아보기](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reporting/dynamic-reporting/pii-agreement){target="_blank"} |

### 감사 추적 {#audit-trail-options}

감사 추적은 Campaign 엔티티에 대한 변경 사항을 기록합니다. 이러한 옵션을 사용하여 엔티티에 대해 활성화하거나 비활성화합니다(예: 데이터베이스의 공간을 절약하기 위해). 감사 추적을 활성화하려면 값을 1로 설정하고 비활성화하려면 값을 0으로 설정합니다. 자세한 내용은 [감사 추적](../reporting/audit-trail.md#enable-disable-audit-trail)을 참조하세요.

| 옵션 | 감사된 엔티티 |
|---|---|
| XtkAudit_Workflows | 워크플로 |
| XtkAudit_DataSchema | 스키마 |
| XtkAudit_Option | 옵션 |
| XtkAudit_Delivery | 게재 |
| XtkAudit_ExtAccount | 외부 계정 |
| XtkAudit_DeliveryMapping | 게재 매핑 |
| XtkAudit_WebApp | 웹 애플리케이션 |
| XtkAudit_Offer | 오퍼 |
| XtkAudit_Operator | 연산자 |
| XtkAudit_Enable_All | 모든 엔티티 |

### 통합 및 설문 조사 {#integration-options}

이러한 옵션은 통합 및 설문 조사 설정을 저장합니다. 랜딩 페이지에 대한 Adobe Developer Console 자격 증명, CRM 커넥터 활동의 마지막 동기화 날짜 및 설문 조사 응답에 대한 기본 백업입니다. [Adobe Campaign 랜딩 페이지에서 Adobe Experience Platform 프로필 업데이트](../connect/ac-aep-landing-pages.md), [CRM 커넥터 데이터 동기화](../connect/crm-data-sync.md) 및 [답변 관리](../dev/surveys/managing-answers.md)에서 자세히 알아보세요.

| 옵션 | 설명 |
|---|---|
| IMS_CLIENT_ID, IMS_CLIENT_SECRET, IMS_ORG_ID, IMS_CLIENT_API_KEY | Adobe Experience Platform이 있는 랜딩 페이지에 사용되는 Adobe Developer Console 자격 증명입니다. [자세히 알아보기](../connect/ac-aep-landing-pages.md) |
| LASTIMPORT_ 뒤에 인스턴스의 내부 이름과 활동 이름이 옵니다. | 일반 CRM 커넥터 활동의 마지막 동기화 날짜입니다. `yyyy/MM/dd hh:mm:ss` 형식의 텍스트 옵션으로 수동으로 만듭니다. [자세히 알아보기](../connect/crm-data-sync.md) |
| NmsWebApp_XmlBackup | 모든 설문 조사에 대해 기본적으로 원시 답변 사본을 저장하려면 만들고 1로 설정합니다. [자세히 알아보기](../dev/surveys/managing-answers.md) |
| AEMResourceTypeFilter | Campaign에서 사용할 수 있는 Adobe Experience Manager 리소스 유형으로, 쉼표로 구분됩니다. [자세히 알아보기](../connect/ac-aem.md) |
| nmsPipeline_config | JSON 형식의 Adobe Experience Cloud 트리거 구성입니다. 긴 텍스트 옵션으로 만듭니다. [자세히 알아보기](../connect/ac-triggers.md) |
| TNT_EdgeServer | 통합에 사용되는 Adobe Target 서버(기본적으로 설정됨) 뒤에 /m2가 오는 Adobe Target 도메인 서버입니다(예: tt.omtrdc.net/m2). [자세히 알아보기](../connect/ac-at.md) |
| TNT_TenantName | Adobe Target 조직(클라이언트)의 이름입니다. [자세히 알아보기](../connect/ac-at.md) |
| AAM_DataSourceId, AAM_DestinationId | Adobe Audience Manager 통합에서 사용하는 식별자. [자세히 알아보기](../start/shared-audiences.md) |
| WdbcCapabilities_AzureDw | Azure Synapse(Azure SQL Data Warehouse) 커넥터 옵션 [자세히 알아보기](../connect/fda.md) |

## 관련 항목 {#related-topics}

* [기본 제공 패키지](built-in-packages.md)
* [글로벌 원칙](general-architecture.md)
* [자격 증명 회전 안내서](../../technotes/security/credential-rotation-guide.md)
