---
product: campaign
title: Adobe Campaign의 전달성 모니터링
description: Adobe Campaign의 전달성 모니터링에 대한 도구 및 지침에 대해 알아봅니다
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 11c8c4c51c7901ba0d119323c564a64b940428b7
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 2%

---

# 게재 가능성 모니터링{#monitoring-deliverability}

아래에서는 Adobe Campaign에서 제공하는 다양한 모니터링 도구에 대한 세부 정보와 Adobe Campaign에서 제공하는 기능을 활용하여 플랫폼의 전달성을 모니터링하는 방법에 대한 몇 가지 추가 지침을 확인할 수 있습니다.

## 모니터링 도구 {#monitoring-tools}

Adobe Campaign에서는 아래 나열된 모든 게재 기능 도구에 액세스할 수 있습니다.

* [받은 편지함 렌더링 보고서](inbox-rendering.md)를 사용하면 주요 이메일 클라이언트에서 메시지를 미리 보고 콘텐츠와 평판을 검사할 수 있습니다.

* **[!UICONTROL Delivery throughput]** 보고서는 지정된 기간 동안 전체 플랫폼의 처리량에 대한 개요를 제공합니다. 자세한 내용은 [이 섹션](../reporting/global-reports.md#delivery-throughput)을 참조하십시오.
* 각 게재는 다른 인터넷 서비스 공급자(ISP)에 대한 브로드캐스트 통계 보고서를 생성합니다. 다음 숫자를 포함하여 전달성에 영향을 줄 수 있는 일부 데이터 품질 및 신뢰도 지표를 표시합니다.
   * **[!UICONTROL Hard bounces]**&#x200B;은(는) 데이터 품질을 나타냅니다. 이 숫자는 2% 미만이어야 합니다.
   * **[!UICONTROL Soft bounces]**&#x200B;은(는) 평판을 나타냅니다. 이 숫자는 특정 ISP의 경우 10%보다 커서는 안 됩니다.

  <!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

* 일반적으로 [게재 대시보드](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#sending-messages){target="_blank"}를 통해 다음에 액세스할 수 있습니다.
   * 전송 세부 정보 및 성공적으로 전송, 처리 및 전송된 메시지 수를 보여 주는 게재 요약
   * 제외된 타겟 및 이유를 보여 주는 게재 로그 및 기록
   * 열기 및 클릭 수와 같은 추적 정보를 표시하는 추적 로그.

## 모니터링 지침 {#monitoring-guidelines}

다음은 게재 가능성 모니터링에 대한 몇 가지 추가 지침입니다.

* 전체 플랫폼에 대한 [게재 처리량](../reporting/global-reports.md#delivery-throughput)을(를) 정기적으로 확인하여 원본 설정과 일치하는지 확인하십시오.
* 게재 템플릿에 [다시 시도](delivery-failures.md#retries)가 올바르게 설정되었는지(다시 시도 기간 30분 및 20번 이상 다시 시도) 확인하십시오.
* [바운스](delivery-failures.md#bounce-mail-qualification) 사서함에 액세스할 수 있고 계정이 곧 만료되지 않는지 정기적으로 확인하십시오.
* [게재 대시보드](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#sending-messages){target="_blank"}에서 액세스할 수 있는 각 게재 처리량을 확인하여 게재 콘텐츠의 유효성과 일치하는지 확인합니다(예: &#39;플래시 판매&#39;는 일 수가 아닌 분 단위로 제공되어야 함). 는 메시지를 보내는 동안 게재 및 잠재적인 문제를 모니터링하는 주요 도구입니다.
* [예약된 일괄 처리](configure-and-send.md#sending-using-multiple-waves)를 사용하는 경우 다음 예약된 일괄 처리가 트리거되기 전에 각 일괄 처리를 완료할 시간이 충분한지 확인하십시오.
* 오류 수와 새 [격리](quarantines.md)이(가) 다른 게재와 일치하는지 확인하십시오.
* 강조 표시된 오류 종류(차단 목록, DNS 문제, 스팸 방지 규칙 등)를 확인하려면 [게재 로그](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#delivery-logs-and-history){target="_blank"}를 자세히 참조하세요.
