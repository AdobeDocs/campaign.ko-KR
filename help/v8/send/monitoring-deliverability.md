---
product: campaign
title: Adobe Campaign의 전달성 모니터링
description: Adobe Campaign의 전달성 모니터링에 대한 도구 및 지침에 대해 알아봅니다
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 3dd4f6041ef193a0d7ea74a0b2c06183861c2797
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 3%

---

# 게재 가능성 모니터링{#monitoring-deliverability}

아래에서는 Adobe Campaign에서 제공하는 다양한 모니터링 도구에 대한 세부 정보와 Adobe Campaign에서 제공하는 기능을 활용하여 플랫폼의 전달성을 모니터링하는 방법에 대한 몇 가지 추가 지침을 확인할 수 있습니다.

## 모니터링 도구 {#monitoring-tools}

Adobe Campaign에서는 아래 나열된 게재 기능 도구에 액세스할 수 있습니다.

### 받은 편지함 렌더링 {#inbox-rendering-tool}

[받은 편지함 렌더링 보고서](inbox-rendering.md)를 사용하면 주요 이메일 클라이언트에서 메시지를 미리 보고 콘텐츠와 평판을 검사할 수 있습니다.

### 게재 처리량 {#throughput-reports}

**[!UICONTROL Delivery throughput]** 보고서는 지정된 기간 동안 전체 플랫폼의 처리량에 대한 개요를 제공합니다. 자세한 내용은 [이 섹션](../reporting/global-reports.md#delivery-throughput)을 참조하십시오.

### 브로드캐스트 통계 {#broadcast-statistics}

각 게재는 다른 인터넷 서비스 공급자(ISP)에 대한 브로드캐스트 통계 보고서를 생성합니다. 다음 숫자를 포함하여 전달성에 영향을 줄 수 있는 일부 데이터 품질 및 신뢰도 지표를 표시합니다.

**[!UICONTROL Hard bounces]**&#x200B;은(는) 데이터 품질을 나타냅니다. 이 숫자는 2% 미만이어야 합니다.

**[!UICONTROL Soft bounces]**&#x200B;은(는) 평판을 나타냅니다. 이 숫자는 특정 ISP의 경우 10%보다 커서는 안 됩니다.

<!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

### 게재 대시보드 {#delivery-dashboard-monitoring}

일반적으로 [게재 대시보드](delivery-dashboard.md)를 통해 다음에 액세스할 수 있습니다.

전송 세부 정보 및 전송, 처리 및 성공적으로 전송된 메시지 수를 보여주는 게재 요약입니다.

제외된 타겟 및 이유를 보여 주는 게재 로그 및 기록.

열기 및 클릭 수와 같은 추적 정보를 표시하는 추적 로그.

### SpamAssassin 테스트 {#spam-testing}

[SpamAssassin](spamassassin.md)을(를) 사용하여 이메일 콘텐츠를 테스트하고 점수를 매겨 수신 시 사용되는 스팸 방지 도구로 인해 메시지가 스팸으로 간주될 위험이 있는지 여부를 확인합니다.

### 컨트롤 패널 {#control-panel-monitoring}

>[!NOTE]
>
>Campaign 컨트롤 패널은 Campaign v8 Managed Cloud Services 사용자가 사용할 수 있습니다. [Campaign 컨트롤 패널](../config/self-service.md)에 대해 자세히 알아보세요.

Campaign [Campaign 컨트롤 패널](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ko){target="_blank"}은(는) 하위 도메인 및 인증서 관리, 활성 프로필 모니터링, 게재 처리량 및 지연 지표 등 게재 가능성을 위한 모니터링 기능을 제공합니다.

## 모니터링 지침 {#monitoring-guidelines}

다음은 게재 가능성 모니터링에 대한 몇 가지 추가 지침입니다.

### 플랫폼 처리량 모니터링

전체 플랫폼에 대한 [게재 처리량](../reporting/global-reports.md#delivery-throughput)을(를) 정기적으로 확인하여 원본 설정과 일치하는지 확인하십시오.

### 구성 다시 시도

게재 템플릿에 [다시 시도](delivery-failures.md#retries)가 올바르게 설정되었는지(다시 시도 기간 30분 및 20번 이상 다시 시도) 확인하십시오.

### 반송 사서함 확인

[바운스](delivery-failures.md#bounce-mail-qualification) 사서함에 액세스할 수 있고 계정이 곧 만료되지 않는지 정기적으로 확인하십시오.

### 게재 성능 확인

[게재 대시보드](delivery-dashboard.md)에서 액세스할 수 있는 각 게재 처리량을 확인하여 게재 콘텐츠의 유효성과 일치하는지 확인합니다(예: &#39;플래시 판매&#39;는 일 수가 아닌 분 단위로 제공되어야 함).

### 예약된 일괄 처리 시간 확인

[예약된 일괄 처리](configure-and-send.md#sending-using-multiple-waves)를 사용하는 경우 다음 예약된 일괄 처리가 트리거되기 전에 각 일괄 처리를 완료할 시간이 충분한지 확인하십시오.

### 격리 모니터링

오류 수와 새 [격리](quarantines.md)이(가) 다른 게재와 일치하는지 확인하십시오.

### 게재 로그 분석

강조 표시된 오류 종류(차단 목록, DNS 문제, 스팸 방지 규칙 등)를 확인하려면 [게재 로그](delivery-dashboard.md#delivery-logs-and-history)를 자세히 참조하세요.

## 관련 항목

[Adobe 전달성 모범 사례 안내서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=ko){target="_blank"}에서는 전달성 전략, 정의, 지표 및 모범 사례에 대한 포괄적인 지침을 제공합니다.

[전달성 소개](about-deliverability.md)에서는 주요 전달성 개념과 Campaign에서 전달률을 향상시키는 방법을 소개합니다.

[게재 실패 및 바운스](delivery-failures.md)에서는 게재 실패의 다양한 유형과 Campaign에서 이를 처리하는 방법을 설명하고 일반적인 문제에 대한 문제 해결 지침을 포함합니다.

[격리 관리](quarantines.md)에서는 Campaign에서 보낸 사람의 평판을 보호하기 위해 격리된 주소를 관리하는 방법을 설명합니다.

[메시지 콘텐츠 제어](control-message-content.md)에서는 콘텐츠가 배달 가능성을 위해 최적화되었는지 확인하는 방법에 대한 지침을 제공합니다.
