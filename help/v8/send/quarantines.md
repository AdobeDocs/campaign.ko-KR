---
title: Campaign의 격리 관리
description: Adobe Campaign의 격리 관리 이해
feature: Profiles, Monitoring
role: User, Data Engineer
level: Beginner
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: e45799f0f3849d53d2c5f593bc02954b3a55fc28
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 4%

---

# 격리 {#quarantine-management}

Adobe Campaign은 온라인 채널(이메일, SMS, 푸시 알림)에 대해 격리된 주소 목록을 관리합니다. 일부 인터넷 액세스 공급자는 잘못된 주소의 비율이 너무 높은 경우 이메일을 자동으로 스팸으로 간주합니다. 따라서 이러한 공급자에 의해 차단 목록에 추가하다에 추가되는 것을 피할 수 있습니다. 또한 격리를 통해 잘못된 전화번호를 게재에서 제외하면 SMS를 보내는 비용을 줄이는 데 도움이 됩니다.

주소 또는 전화번호가 격리되면 게재 분석 중에 수신자가 대상에서 제외됩니다. 이러한 연락처에게 자동화된 워크플로우 이메일을 포함한 마케팅 메시지를 보낼 수 없습니다. 격리된 주소도 목록에 있는 경우 해당 목록으로 보낼 때 제외됩니다. 예를 들어, 사서함이 가득 찼거나 주소가 존재하지 않거나 이메일 서버를 사용할 수 없는 경우 이메일 주소를 격리할 수 있습니다.

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

**격리** 에만 적용됩니다. **주소**, a **전화 번호**&#x200B;또는 **장치 토큰**, 프로필 자체에는 적용되지 않습니다. 예를 들어 이메일 주소가 격리된 프로필은 프로필을 업데이트하고 새 주소를 입력한 다음 게재 작업으로 다시 타겟팅될 수 있습니다. 마찬가지로, 두 프로필의 전화 번호가 같으면 해당 번호가 격리되면 둘 다 영향을 받습니다. 격리된 주소 또는 전화번호는 [제외 로그](#delivery-quarantines) (게재용) 또는 [격리 목록](#non-deliverable-bounces) (전체 플랫폼).

반면 프로필은 **차단 목록** 구독 취소(옵트아웃) 후와 마찬가지로, 지정된 채널에 대해: 이는 더 이상 이 채널에 의해 타깃팅되지 않음을 의미합니다. 따라서 이메일 채널에 대한 차단 목록에 추가하다의 프로필에 두 개의 주소가 있는 경우 두 주소 모두 게재에서 제외됩니다. 프로필이 차단 목록에 추가하다에 있는지 또는 의 하나 이상의 채널에 있는지 확인할 수 있습니다. **[!UICONTROL No longer contact]** 프로필 섹션 **[!UICONTROL General]** 탭. [자세히 알아보기](../audiences/view-profiles.md)

>[!NOTE]
>
>수신자가 메시지를 스팸으로 보고하거나 &quot;STOP&quot;과 같은 키워드를 사용하여 SMS 메시지에 회신하면 주소 또는 전화번호가 다음으로 격리됩니다. **[!UICONTROL Denylisted]**. 프로필이 그에 따라 업데이트됩니다.

<!--For the email channel, email addresses are quarantined. For the mobile app channel, device tokens are quarantined. For the SMS channel, phone numbers are quarantined.?-->

## 이메일, 전화 또는 장치가 격리로 전송되는 이유 {#quarantine-reason}

Adobe Campaign은 게재 실패 유형 및 이유에 따라 격리를 관리합니다. 오류 메시지 자격 조건 중에 할당됩니다. 게재 실패 관리에 대해 자세히 알아보기 [이 페이지에서](delivery-failures.md).

다음 두 가지 유형 또는 오류를 캡처할 수 있습니다.

* **하드 오류**: 이메일 주소, 전화번호 또는 장치가 즉시 격리됩니다.
* **소프트 오류**: 소프트 오류는 오류 카운터를 증가시키고 이메일, 전화 번호 또는 장치 토큰을 격리할 수 있습니다. Campaign의 성과 [다시 시도](delivery-failures.md#retries): 오류 카운터가 제한 임계값에 도달하면 주소, 전화 번호 또는 장치 토큰이 격리됩니다. [자세히 알아보기](delivery-failures.md#retries)

격리된 주소 목록에서 **[!UICONTROL Error reason]** 필드는 선택한 주소가 격리된 이유를 나타냅니다. [자세히 알아보기](#identifying-quarantined-addresses-for-the-entire-platform)


사용자가 이메일을 스팸 처리하면 메시지는 자동으로 Adobe이 관리하는 기술 사서함으로 리디렉션됩니다. 그러면 사용자의 이메일 주소가 자동으로 **[!UICONTROL Denylisted]** 상태로 격리됩니다. 이 상태는 주소만 참조하고, 프로필은 푸시 차단 목록에 있지 않으므로 SMS 메시지와 알림을 계속 수신하게 됩니다. 에서 피드백 루프에 대해 자세히 알아보세요. [게재 모범 사례 안내서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops){target="_blank"}.

>[!NOTE]
>
>Adobe Campaign의 격리는 대소문자를 구분합니다. 이메일 주소를 소문자로 가져와야 이후에 다시 타겟팅되지 않습니다.

## 격리된 주소 액세스 {#access-quarantined-addresses}

특정 게재 또는 플랫폼 전체에 대해 격리된 주소를 표시할 수 있습니다.

### 게재 격리{#delivery-quarantines}

격리 주소는 게재 준비 단계 동안 게재 대시보드의 게재 로그에 나열됩니다.

각 게재에 대해 다음을 확인할 수도 있습니다 **[!UICONTROL Delivery summary]** 보고서: 게재 대상에 격리된 주소 수를 표시하고 다음을 표시합니다.

* 게재 분석 중 격리된 주소 수
* 게재 작업 후 격리된 주소 수입니다.

### 비게재 항목 및 바운스 주소{#non-deliverable-bounces}

격리된 주소 목록을 보려면 **전체 플랫폼**, Campaign 관리자는 다음을 찾을 수 있습니다.  **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**. 이 섹션에는 다음에 대해 격리된 요소가 나열되어 있습니다. **이메일**, **SMS** 및 **푸시 알림** 채널.

![](assets/tech-quarantine.png)

>[!NOTE]
>
>격리 횟수는 시간이 지남에 따라 증가합니다. 예를 들어 이메일 주소의 수명을 3년으로 보고 수신자 표가 매년 50%씩 증가하는 경우 다음과 같이 격리 증가를 계산할 수 있습니다.
>
>1년말: (1)&#42;0.33)/(1+0.5)=22%.
>
2년말: (1.22&#42;0.33)+0.33)/(1.5+0.75)=32.5%.

또한 **[!UICONTROL Non-deliverables and bounces]** 기본 제공 보고서, 다음에서 사용 가능: **보고서** 이 홈 페이지의 섹션에는 격리된 주소, 발생한 오류 유형 및 도메인별 실패 분류에 대한 정보가 표시됩니다. 특정 게재에 대한 데이터를 필터링하거나 필요에 따라 이 보고서를 사용자 지정할 수 있습니다.

의 바운스 주소에 대해 자세히 알아보기 [전달성 모범 사례 안내서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html){target="_blank"}.

### 격리된 이메일 주소 {#quarantined-recipient}

모든 수신자의 이메일 주소 상태를 조회할 수 있습니다.

이렇게 하려면 수신자 프로필을 선택하고 **[!UICONTROL Deliveries]** 탭. 해당 수신자에 대한 모든 게재에 대해 주소가 실패했는지, 분석 중에 격리되었는지 등을 확인할 수 있습니다.

각 폴더에 대해 전자 메일 주소가 격리된 수신자만 **[!UICONTROL Quarantined email address]** 기본 제공 필터, 아래 참조:

![](assets/quarantine-filter.png)


## 격리된 주소 제거 {#remove-a-quarantined-address}

특정 조건과 일치하는 주소는 다음을 통해 격리 목록에서 자동으로 삭제됩니다. **데이터베이스 정리** 기본 제공 워크플로우입니다.

다음과 같은 경우 주소가 격리 목록에서 자동으로 제거됩니다.

* 의 주소 **[!UICONTROL With errors]** 게재가 성공하면 격리 목록에서 상태가 제거됩니다.
* 의 주소 **[!UICONTROL With errors]** 마지막 소프트 바운스가 10일 이상 전에 발생한 경우 상태가 격리 목록에서 제거됩니다. 소프트 오류 관리에 대한 자세한 내용은 [이 섹션](#soft-error-management).
* 의 주소 **[!UICONTROL With errors]** 와 함께 반송된 상태 **[!UICONTROL Mailbox full]** 30일 후 격리 목록에서 오류가 제거됩니다.

상태가 다음으로 변경됨: **[!UICONTROL Valid]**.

>[!CAUTION]
>
에 주소가 있는 수신자 **[!UICONTROL Quarantine]** 또는 **[!UICONTROL Denylisted]** 이메일을 수신하더라도 상태는 제거되지 않습니다.

격리 목록에서 주소를 수동으로 제거할 수도 있습니다. 격리에서 주소를 제거하려면 다음을 수행할 수 있습니다.

* 상태를 다음으로 변경 **[!UICONTROL Valid]** 다음에서 **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]** 노드.

  ![](assets/tech-quarantine-status.png)

예를 들어 이메일이 수신자에게 성공적으로 전달될 수 없기 때문에 이메일이 바운스로 잘못 표시되는 ISP 중단과 같은 경우 격리 목록에서 대량 업데이트를 수행해야 할 수 있습니다.

이렇게 하려면 워크플로우를 만들고 격리 테이블에 쿼리를 추가하여 영향을 받는 모든 수신자를 격리 목록에서 제거하고 향후 Campaign 이메일 게재에 포함할 수 있도록 필터링합니다.

다음은 이 쿼리에 대한 권장 지침입니다.

* **오류 텍스트(격리 텍스트)** 에는 &quot;Momen_Code10_InvalidRecipient&quot;가 포함되어 있습니다.
* **이메일 도메인(@domain)** domain1.com과 같음 또는 **이메일 도메인(@domain)** domain2.com과 같음 또는 **이메일 도메인(@domain)** domain3.com과 같음
* **업데이트 상태(@lastModified)** 다음 또는 이후 `MM/DD/YYYY HH:MM:SS AM`
* **업데이트 상태(@lastModified)** 다음 또는 이전 `MM/DD/YYYY HH:MM:SS PM`

영향을 받는 수신자 목록이 있으면 **[!UICONTROL Update data]** 상태를 다음으로 설정할 활동 **[!UICONTROL Valid]** 따라서 다음을 통해 격리 목록에서 제거됩니다. **[!UICONTROL Database cleanup]** 워크플로,. 격리 테이블에서 삭제할 수도 있습니다.

