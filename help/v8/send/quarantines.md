---
title: Campaign의 격리 관리
description: Adobe Campaign의 격리 관리 이해
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: 1ff06c69a4118afa228522d580dd5caa36a69275
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 5%

---

# 격리 {#quarantine-management}

Adobe Campaign은 온라인 채널(이메일, SMS, 푸시 알림)에 대해 격리된 주소 목록을 관리합니다. 일부 인터넷 액세스 제공 업체는 잘못된 주소의 비율이 너무 높은 경우 이메일을 자동으로 스팸으로 간주합니다. 따라서 격리 를 사용하면 이러한 제공 업체에 의해 차단 목록에 추가되지 않습니다. 또한 격리를 통해 잘못된 전화번호를 게재에서 제외하면 SMS를 보내는 비용을 줄이는 데 도움이 됩니다.

주소나 전화번호가 격리되면 게재 분석 중에 수신자가 대상에서 제외됩니다. 자동화된 워크플로우 이메일을 포함한 마케팅 메시지를 해당 연락처에 보낼 수 없습니다. 격리된 주소도 목록에 있으면 해당 목록에 전송할 때 제외됩니다. 예를 들어, 사서함이 가득 찼거나, 주소가 존재하지 않거나, 전자 메일 서버를 사용할 수 없는 경우 전자 메일 주소를 격리할 수 있습니다.

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

**격리** 에만 적용 **주소**, **전화 번호**&#x200B;또는 **장치 토큰**&#x200B;하지만 프로필 자체가 아닙니다. 예를 들어, 프로필의 이메일 주소가 격리되면 프로필을 업데이트하여 새 주소를 입력하면 게재 작업 시 다시 타겟팅될 수 있습니다. 마찬가지로, 두 프로필에 동일한 전화 번호가 있는 경우 해당 번호가 격리되면 두 프로필 모두에 영향을 줍니다. 격리된 주소 또는 전화 번호는 [제외 로그](#delivery-quarantines) (게재의 경우) 또는 [격리 목록](#non-deliverable-bounces) (전체 플랫폼에 대해)

반면 프로필은 **차단 목록** 구독 취소(옵트아웃) 이후와 마찬가지로, 지정된 채널에 대해 다음과 같이 하십시오. 이것은 그들이 더 이상 어떤 것에 의해 타깃팅되지 않는다는 것을 의미합니다. 따라서 이메일 채널에 대한차단 목록에 두 개의 이메일 주소가 있는 경우 두 개의 주소가 게재에서 제외됩니다. 프로필이에서 하나 이상차단 목록의 채널에 있는지 확인할 수 있습니다 **[!UICONTROL No longer contact]** 프로필의 섹션 **[!UICONTROL General]** 탭. [자세히 알아보기](../audiences/view-profiles.md)

>[!NOTE]
>
>수신자가 메시지를 스팸으로 보고하거나 &quot;STOP&quot; 등의 키워드로 SMS 메시지에 회신하면 해당 주소나 전화번호가 **[!UICONTROL Denylisted]**. 해당 프로필은 그에 따라 업데이트됩니다.

<!--For the email channel, email addresses are quarantined. For the mobile app channel, device tokens are quarantined. For the SMS channel, phone numbers are quarantined.?-->

## 전자 메일, 휴대폰 또는 장치가 격리되는 이유는 무엇입니까 {#quarantine-reason}

Adobe Campaign은 게재 실패 유형 및 그 이유에 따라 격리를 관리합니다. 오류 메시지 자격 중에 할당됩니다. 게재 실패 관리에 대해 자세히 알아보기 [이 페이지에서](delivery-failures.md).

두 가지 유형 또는 오류를 캡처할 수 있습니다.

* **하드 오류**: 이메일 주소, 전화번호 또는 장치는 즉시 격리됩니다.
* **소프트 오류**: 소프트 오류의 경우 오류 카운터가 증가하며, 전자 메일, 전화 번호 또는 장치 토큰이 격리될 수 있습니다. Campaign에서 다음을 수행합니다 [다시 시도](delivery-failures.md#retries): 오류 카운터가 제한 임계값에 도달하면 주소, 전화 번호 또는 장치 토큰이 격리됩니다. [자세히 알아보기](delivery-failures.md#retries)

격리된 주소 목록에서 **[!UICONTROL Error reason]** 필드는 선택한 주소가 격리된 이유를 나타냅니다. [자세히 알아보기](#identifying-quarantined-addresses-for-the-entire-platform)


사용자가 이메일을 스팸 처리하면 해당 메시지는 Adobe에서 관리하는 기술 사서함으로 자동 리디렉션됩니다. 그러면 사용자의 이메일 주소가 자동으로 **[!UICONTROL Denylisted]** 상태로 격리됩니다. 이 상태는 주소만 참조하고, 프로필은에 차단 목록 없습니다. 따라서 사용자는 계속해서 SMS 메시지와 푸시 알림을 수신합니다. 의 피드백 루프에 대해 자세히 알아보십시오 [게재 모범 사례 안내서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops).

>[!NOTE]
>
>Adobe Campaign의 격리는 대소문자를 구분합니다. 이메일 주소를 소문자로 가져와야 이후에 다시 타겟팅되지 않습니다.

## 격리된 주소 액세스 {#access-quarantined-addresses}

특정 게재 또는 플랫폼 전체에 대해 격리된 주소를 표시할 수 있습니다.

### 게재를 위한 격리{#delivery-quarantines}

게재 준비 단계 동안 게재 대시보드의 게재 로그에 격리 주소가 나열됩니다.

각 게재에 대해 **[!UICONTROL Delivery summary]** 보고서: 게재 대상의 격리 주소 수를 표시하며 다음과 같이 표시됩니다.

* 게재 분석 중 격리된 주소 수,
* 게재 작업 후 격리된 주소 수입니다.

### 비산출물 및 반송 주소{#non-deliverable-bounces}

격리된 주소 목록을 보려면 **전체 플랫폼**, Campaign 관리자는  **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**. 이 섹션에는 격리된 요소의 목록이 표시됩니다 **이메일**, **SMS** 및 **푸시 알림** 채널입니다.

![](assets/tech-quarantine.png)

>[!NOTE]
>
>시간이 지남에 따라 격리 수가 증가합니다. 예를 들어 이메일 주소의 수명을 3년으로 보고 수신자 표가 매년 50%씩 증가할 경우, 격리 증가는 다음과 같이 계산할 수 있습니다.
>
>1년말: (1)&#42;0.33)/(1+0.5)=22%.
>
>2년 말: (1.22)&#42;0.33)+0.33)/(1.5+0.75)=32.5%.

또한 **[!UICONTROL Non-deliverables and bounces]** 기본 제공 보고서, **보고서** 이 홈 페이지의 섹션에는 격리된 주소, 발생한 오류 유형 및 도메인별 실패 분류에 대한 정보가 표시됩니다. 특정 전달에 대한 데이터를 필터링하거나 필요에 따라 이 보고서를 사용자 지정할 수 있습니다.

에서 바운스 주소에 대해 자세히 알아보십시오 [게재 가능성 모범 사례 안내서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html)

### 격리된 전자 메일 주소 {#quarantined-recipient}

수신자의 이메일 주소 상태를 조회할 수 있습니다.

이렇게 하려면 수신자 프로필을 선택하고 **[!UICONTROL Deliveries]** 탭. 해당 수신자에 대한 모든 게재의 경우, 주소가 실패했는지, 분석 중 격리되었는지 등을 확인할 수 있습니다.

각 폴더에 대해 전자 메일 주소가 격리된 수신자만을 **[!UICONTROL Quarantined email address]** 아래와 같이 기본 제공 필터:

![](assets/quarantine-filter.png)


## 격리된 주소 제거 {#remove-a-quarantined-address}

특정 조건과 일치하는 주소는 격리 목록에서 **데이터베이스 정리** 기본 제공 워크플로우입니다.

다음과 같은 경우 주소가 격리 목록에서 자동으로 제거됩니다.

* 의 주소 **[!UICONTROL With errors]** 게재가 성공하면 상태가 격리 목록에서 제거됩니다.
* 의 주소 **[!UICONTROL With errors]** 10일 이상 전에 마지막 소프트 바운스가 발생한 경우 상태가 격리 목록에서 제거됩니다. 소프트 오류 관리에 대한 자세한 내용은 [이 섹션](#soft-error-management).
* 의 주소 **[!UICONTROL With errors]** 다음으로 바운스된 상태 **[!UICONTROL Mailbox full]** 30일 후 격리 목록에서 오류가 제거됩니다.

그러면 상태가 **[!UICONTROL Valid]**.

>[!CAUTION]
>
>주소가 있는 수신자 **[!UICONTROL Quarantine]** 또는 **[!UICONTROL Denylisted]** 이메일이 수신되더라도 상태는 제거되지 않습니다.

격리 목록에서 주소를 수동으로 제거할 수도 있습니다. 주소를 격리하려면 다음을 수행할 수 있습니다.

* 상태를 로 변경 **[!UICONTROL Valid]** 에서 **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]** 노드 아래에 있어야 합니다.

   ![](assets/tech-quarantine-status.png)

* 상태를 로 변경 **[!UICONTROL Allowlisted]**: 이 경우 주소는 격리 목록에 남아 있지만 오류가 발생하는 경우에도 체계적으로 타겟팅됩니다.

>[!CAUTION]
>
>격리 목록에서 주소를 제거하면 다시 이 주소로 보내집니다. 이로 인해 게재 능력과 IP 평판에 심각한 영향을 줄 수 있으므로 IP 주소 또는 전송 도메인이 차단될 수 있습니다. 격리된 주소 제거를 고려할 때 추가 주의가 필요합니다. 도움이 필요한 경우 Adobe 지원 센터에 문의하십시오.
