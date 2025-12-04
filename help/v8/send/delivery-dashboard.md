---
title: Campaign UI에서 게재 모니터링
description: 게재 목록에 액세스하고 게재 대시보드를 사용하여 게재를 모니터링하는 방법을 알아봅니다
feature: Monitoring
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 3%

---

# Campaign UI에서 게재 모니터링 {#delivery-dashboard}

캠페인이 효율적이고 고객에게 도달하도록 하려면 게재 모니터링이 필수적입니다. Adobe Campaign은 게재 목록 및 게재 대시보드를 통해 게재에 액세스하고 게재 성과를 모니터링할 수 있는 도구를 제공합니다.

## 게재 목록 액세스 {#list-of-deliveries}

트리의 **[!UICONTROL Campaign Management > Deliveries]** 노드를 통해 게재 목록에서 게재에 액세스할 수 있습니다.

![](assets/deliveries-list.png)

기본적으로 게재 목록에는 선택한 노드에서 만든 게재의 이름과 상태가 포함됩니다. 전송, 처리 및 성공적으로 전송된 메시지 수도 표시됩니다.

* **[!UICONTROL Messages to send]**&#x200B;의 수는 분석 후 배달되기 전에 타겟팅된 받는 사람 수에 해당합니다.
* **[!UICONTROL Success]** 열의 메시지 수는 서버에서 보내고 받는 사람이 받은 메시지 수에 해당합니다.
* **[!UICONTROL Processed]**&#x200B;개의 메시지 수는 받은 메시지 수와 오류가 있는 메시지 수를 더한 값에 해당합니다.

>[!NOTE]
>
>대량 게재의 경우 이러한 값을 업데이트할 수 있습니다. 이렇게 하려면 해당 게재를 선택한 다음 마우스 오른쪽 단추를 클릭합니다. **[!UICONTROL Action > Recompute delivery and tracking indicators...]**&#x200B;을(를) 선택한 다음 도우미를 사용하여 이 정보를 업데이트하세요.

## 게재 대시보드 개요 {#delivery-dashboard-overview}

**게재 대시보드**&#x200B;는 메시지를 보내는 동안 발생하는 게재 및 최종 문제를 모니터링하는 키입니다.

이를 통해 게재 정보를 검색하고 필요한 경우 편집할 수 있습니다. 게재가 전송되면 탭 콘텐츠가 더 이상 변경되지 않을 수 있습니다.

다음은 대시보드에서 사용할 수 있는 몇 가지 탭을 사용하여 모니터링할 수 있는 정보입니다.

* [게재 요약](#delivery-summary)
* [게재 보고서](#delivery-reports)
* [게재 로그, 미러 페이지, 제외](#delivery-logs-and-history)
* [게재 추적 로그 및 내역](#tracking-logs)
* [게재 렌더링](#delivery-rendering)
* [게재 감사](#delivery-audit-)

![](assets/s_ncs_user_del_details.png)

**관련 항목:**

* [게재 실패 이해](delivery-failures.md)
* [격리 관리](quarantines.md)
* [게재 모범 사례](../start/delivery-best-practices.md)
* [게재 기능 관리](about-deliverability.md)

## 게재 요약 {#delivery-summary}

**[!UICONTROL Summary]** 탭에는 게재 특성(게재 상태, 사용한 채널, 보낸 사람 정보, 제목, 실행 관련 정보)이 포함되어 있습니다.

## 게재 보고서 {#delivery-reports}

**[!UICONTROL Reports]** 탭에서 액세스할 수 있는 **[!UICONTROL Summary]** 링크를 사용하면 게재 작업과 관련된 보고서 세트(일반 게재 보고서, 자세한 보고서, 게재 보고서, 실패한 메시지 배포, 열람률, 클릭 수 및 트랜잭션 등)를 볼 수 있습니다.

이 탭의 내용은 요구 사항에 따라 구성할 수 있습니다. 게재 보고서에 대한 자세한 정보는 [이 섹션](../reporting/delivery-reports.md)을 참조하세요.

![](assets/delivery-report.png)

## 게재 로그, 내역 및 제외 {#delivery-logs-and-history}

**[!UICONTROL Delivery]** 탭에는 이 게재의 발생 기록이 표시됩니다. 여기에는 게재 로그(예: 보낸 메시지 목록, 상태 및 관련 메시지)가 포함됩니다.

게재의 경우 게재가 실패한 수신자 또는 격리 중인 주소만 표시할 수 있습니다(예: ). 이렇게 하려면 **[!UICONTROL Filters]** 단추를 클릭하고 **[!UICONTROL By state]**&#x200B;을(를) 선택합니다. 그런 다음 드롭다운 목록에서 상태를 선택합니다. [게재 상태 페이지](delivery-statuses.md)에 다양한 상태가 나열됩니다.

>[!NOTE]
>
>게재 로그를 표시하는 목록은 Campaign의 모든 목록과 같이 사용자 지정할 수 있습니다. 예를 들어 게재에서 각 이메일을 전송한 IP 주소를 알기 위한 열을 추가할 수 있습니다. 목록 표시 구성에 대한 자세한 내용은 [이 섹션](../config/ui-settings.md#customize-lists)을 참조하세요.

![](assets/s_ncs_user_delivery_delivery_tab.png)

**[!UICONTROL Display the mirror page for this message...]** 링크를 사용하면 새 창의 목록에서 선택한 게재 내용에 대한 미러 페이지를 볼 수 있습니다.

미러 페이지는 HTML 콘텐츠가 정의된 게재에 대해서만 사용할 수 있습니다. 자세한 내용은 [미러 페이지에 연결](mirror-page.md)을 참조하세요.

![](assets/s_ncs_user_wizard_miror_page_link.png)

## 게재 추적 로그 및 내역 {#tracking-logs}

**[!UICONTROL Tracking]** 탭에 이 게재의 추적 기록이 나열됩니다. 이 탭에는 전송된 메시지에 대한 추적 데이터, 즉 Adobe Campaign에 의한 추적이 적용되는 모든 URL이 표시됩니다. 추적 데이터는 시간별로 업데이트됩니다.

>[!NOTE]
>
>게재에 대해 추적이 활성화되어 있지 않은 경우 이 탭이 표시되지 않습니다.

추적 구성은 게재 도우미의 적절한 단계에서 수행됩니다. [추적된 링크를 구성하는 방법](tracking.md)을 참조하세요.

**[!UICONTROL Tracking]** 데이터가 게재 보고서에 해석되어 있습니다. [이 섹션](../reporting/delivery-reports.md)을 참조하십시오.

![](assets/s_ncs_user_delivery_tracking_tab.png)

## 받은 편지함 렌더링 {#delivery-rendering}

**[!UICONTROL Inbox rendering]** 탭에서는 메시지를 받을 수 있는 다른 컨텍스트에서 메시지를 미리 보고 주요 데스크톱 및 응용 프로그램의 호환성을 확인할 수 있습니다.

이렇게 하면 메시지가 다양한 웹 클라이언트, 웹 메일 및 디바이스에서 최적의 방식으로 수신자에게 표시되도록 할 수 있습니다.

받은 편지함 렌더링에 대한 자세한 정보는 [이 페이지](inbox-rendering.md)를 참조하세요.


## 게재 감사 {#delivery-audit-}

**[!UICONTROL Audit]** 탭에는 게재 로그와 증명과 관련된 모든 메시지가 포함되어 있습니다.

**[!UICONTROL Refresh]** 단추를 사용하여 데이터를 업데이트할 수 있습니다. **[!UICONTROL Filters]** 단추를 사용하여 데이터에 대한 필터를 정의합니다.

특수 아이콘을 사용하면 오류나 경고를 식별할 수 있습니다. [게재 분석](delivery-analysis.md)을 참조하세요.

**[!UICONTROL Proofs]** 하위 탭에서는 보낸 증명 목록을 볼 수 있습니다.

![](assets/s_ncs_user_delivery_log_tab.png)

표시할 열을 선택하여 이 창과 **[!UICONTROL Delivery]** 및 **[!UICONTROL Tracking]** 탭의 정보를 수정할 수 있습니다. 이렇게 하려면 오른쪽 하단에 있는 **[!UICONTROL Configure list]** 아이콘을 클릭합니다. 목록 표시 구성에 대한 자세한 내용은 [이 섹션](../config/ui-settings.md#customize-lists)을 참조하세요.

## 게재 대시보드 동기화 {#delivery-dashboard-synchronization}

게재 대시보드에서 처리된 메시지 및 게재 로그를 확인하여 게재가 성공적으로 전송되었는지 확인할 수 있습니다.

일부 지표 또는 상태가 잘못되거나 최신 상태가 아닐 수 있습니다. 다음 솔루션으로 해결할 수 있습니다.

* 게재 상태가 올바르지 않으면 이 게재에 필요한 모든 승인이 수행되었는지 또는 **[!UICONTROL operationMgt]** 및 **[!UICONTROL deliveryMgt]** 기술 워크플로우가 오류 없이 실행되고 있는지 확인하십시오.

* 게재 카운터가 게재와 일치하지 않으면 Adobe Campaign 탐색기에서 관련 게재를 마우스 오른쪽 단추로 클릭하고 **[!UICONTROL Actions]** > **[!UICONTROL Recompute delivery and tracking indicators]**&#x200B;을(를) 선택하여 다시 동기화하여 표시기를 다시 계산해 보십시오. 지표 추적에 대한 자세한 내용은 이 [섹션](../reporting/delivery-reports.md#tracking-indicators)을 참조하세요.

게재 대시보드를 통해 다양한 보고서를 통해 게재를 추적할 수도 있습니다. 자세한 정보는 이 [섹션](../reporting/delivery-reports.md)을 참조하십시오.

>[!NOTE]
>
>Campaign v8 Managed Cloud Services 사용자는 Adobe에서 인프라를 모니터링하고 관리합니다. 게재 지표 또는 대시보드 동기화에 문제가 지속되는 경우 Adobe 고객 지원 센터에 문의하십시오.

## 느린 게재 문제 해결 {#troubleshooting-slow-deliveries}

**[!UICONTROL Send]** 단추를 클릭한 후 게재가 평소보다 오래 걸리는 것 같으면 다음과 같은 잠재적 원인을 확인하십시오.

### IP 주소 신뢰도 문제

일부 이메일 공급자가 IP 주소를 차단 목록에 추가하다에 추가했을 수 있습니다. 신뢰도 문제를 나타내는 바운스 메시지가 있는지 **[!UICONTROL Delivery]** 탭에서 게재 로그(broadlogs)를 확인하십시오. 신뢰도 관리에 대한 지침은 [전달성 모니터링](monitoring-deliverability.md) 섹션을 참조하십시오.

### 게재 크기 및 복잡성

게재가 너무 커서 빠르게 처리할 수 없습니다. 이 문제는 다음 경우에 발생할 수 있습니다.

각 수신자에 대해 중요한 데이터 처리가 필요한 대규모 JavaScript 개인화입니다.

큰 HTML 콘텐츠, 임베드된 이미지 또는 광범위한 개인화로 인해 게재 무게가 60KB를 초과합니다.

콘텐츠 지침 및 개인화 모범 사례에 대한 자세한 내용은 [게재 모범 사례](../start/delivery-best-practices.md)를 참조하세요. 최적의 성능을 위해 권장되는 최대 크기는 약 35KB입니다.

### 시스템 성능

시스템 문제로 인해 서버가 게재를 효율적으로 처리하지 못할 수 있습니다. 성능 문제가 의심되는 경우 게재 로그에서 시간 초과 오류 또는 통신 문제를 확인하십시오.

>[!NOTE]
>
>Campaign v8 Managed Cloud Services 사용자는 Adobe에서 서버 인프라 모니터링을 관리합니다. 게재 전송에서 지속적인 성능 문제가 발생하는 경우 게재 로그를 사용하여 Adobe 고객 지원 센터에 문의하십시오.

