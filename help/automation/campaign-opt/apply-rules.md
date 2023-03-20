---
product: campaign
title: 유형화 규칙 적용
description: 유형화 규칙을 적용하는 방법 알아보기
feature: Typology Rules
exl-id: 4ec3bbe1-fc4c-4b1e-989c-f4dcf8ee8d5e
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 8%

---

# 유형화 규칙 적용{#applying-rules}

## 게재에 유형화 적용 {#apply-a-typology-to-a-delivery}

생성한 유형화 규칙을 적용하려면 유형화에 해당 유형화를 연결한 다음 게재에서 이 유형화를 참조해야 합니다. 방법은 다음과 같습니다.

1. 캠페인 유형화를 만듭니다.

   유형화는 **[!UICONTROL Administration > Campaign Management > Typology management]** > **[!UICONTROL Typologies]** 캠페인 탐색기의 폴더.

1. 로 이동합니다. **[!UICONTROL Rules]** 탭에서 **[!UICONTROL Add]** 버튼을 클릭하고 이 유형화에 적용할 규칙을 선택합니다.

   ![](assets/campaign_opt_pressure_sample_1_6.png)

1. 유형화를 저장합니다. 기존 유형화 목록에 추가됩니까?
1. 규칙을 적용할 게재를 엽니다.
1. 게재 속성을 열고 **[!UICONTROL Typology]** 탭.
1. 드롭다운 목록에서 유형화를 선택합니다.

   ![](assets/campaign_opt_pressure_sample_1_7.png)

   >[!NOTE]
   >
   >이 템플릿을 사용하여 만든 모든 게재에 자동으로 적용되도록 게재 템플릿에서 유형화를 정의할 수 있습니다.

## 애플리케이션 조건 정의 {#define-application-conditions}

필요에 따라 규칙의 응용 프로그램 필드를 제한할 수 있습니다(제어 규칙 제외).

유형화 규칙이 연결된 특정 게재나 게재 대상 중 특정 수신자만 고려하도록 유형화 규칙을 구성할 수 있습니다.

규칙의 응용 프로그램 조건을 정의하려면 **[!UICONTROL Edit the rule application conditions...]** 링크 위치 **[!UICONTROL General]** 탭.

그런 다음 쿼리 편집기를 사용하여 필터링 조건을 정의합니다. 다음 예에서는 능력 규칙이 2013년 4월 1일 이전에 만든 레이블이나 게재에 &#39;offer&#39;라는 단어가 있는 게재만 다룹니다.

![](assets/campaign_opt_create_capacity_criterion.png)

>[!NOTE]
>
>필터링 규칙의 경우 필터링 기준의 응용 프로그램 조건을 선택할 수 있습니다. 게재 또는 게재 아웃라인에 따라 달라질 수 있습니다. [자세히 알아보기](filtering-rules.md#condition-a-filtering-rule)

## 계산 빈도 조정 {#adjust-calculation-frequency}

중재는 데이터베이스 정리 워크플로우를 통해 매일 밤 자동으로 다시 실행됩니다. 그러나 이 기간을 초과하여 값을 저장할 수 있습니다.

실제로, 일부 계산에서는 일별로 변경되지 않는 값을 사용합니다. 따라서 매일 데이터를 다시 계산하고 아무 것도 없이 데이터베이스를 과부화하는 것은 상관없습니다. 예를 들어 프로세스가 고객 성향 점수와 주별 구매 정보로 마케팅 데이터베이스를 증가시키는 경우 이러한 값을 기반으로 하는 데이터를 매일 다시 계산하지 않아도 됩니다.

이렇게 하려면 **[!UICONTROL Frequency]** 필드 **[!UICONTROL General]** 탭에서는 타깃팅이 저장되는 최대 기간을 정의할 수 있습니다. 기본적으로 값 **0** 일별 재중재 다음에 실행될 때까지 계산이 유효함을 나타냅니다.

이 기간 이상의 결과를 저장하려면 **[!UICONTROL Frequency]** 필드: 이 기간이 만료되면 모든 규칙이 다시 적용됩니다.

다음 **[!UICONTROL Re-apply the rule at the start of personalization]** 옵션을 사용하면 에 지정된 기간을 포함하여 개인화 단계 동안 규칙을 자동으로 적용할 수 있습니다. **[!UICONTROL Frequency]** 필드는 여전히 유효합니다.

## 규칙 애플리케이션 단계 선택 {#selecting-the-rule-application-phase}

유형화 규칙은 게재의 타겟팅, 분석 및 개인화 단계 동안 특정 시퀀스에 적용됩니다.

### 실행 순서 {#execution-order}

표준 작업 모드에서는 규칙은 다음 순서로 적용됩니다.

1. 타겟팅 시작 시 적용되는 경우에는 규칙을 제어합니다.
1. 필터링 규칙:

   * 주소 자격에 대한 기본 애플리케이션 규칙: 정의된 주소 / 확인되지 않은 주소 / / 격리된 주소 / 차단 목록 주소 품질.
   * 사용자가 정의한 필터링 규칙.
   * 주소 또는 식별자의 중복 제거 규칙(필요한 경우 적용됨)입니다.

1. 압력 규칙.
1. 용량 규칙.
1. 타겟팅 끝에 적용되는 경우에는 규칙을 제어합니다.
1. 규칙이 개인화 시작 시 적용되는 경우 규칙을 제어합니다. 사용자 규칙(필터링/압력/정전용량)이 만료되어 다시 계산해야 하는 경우 이 단계 동안 적용됩니다.
1. 규칙이 개인화 끝에 적용되는 경우 규칙을 제어합니다.

>[!NOTE]
>
>Campaign Interaction 모듈을 사용하여 작업하는 경우, 오퍼 엔진 호출 동안 오퍼 자격 규칙이 필터링 규칙(게재 아웃라인에 있는 오퍼에 대해)이나 개인화 단계 동안 동시에 적용됩니다.

의 해당 필드를 사용하여 동일한 유형의 규칙의 실행 시퀀스를 조정할 수 있습니다 **[!UICONTROL General]** 규칙의 탭입니다. 동일한 메시지 처리 단계 동안 여러 규칙이 실행될 때 **[!UICONTROL Execution sequence]** 필드.

예를 들어 실행 순서가 20인 압력 규칙이 실행 순서가 30인 압력 규칙 전에 실행됩니다.

### 제어 규칙 {#control-rules}

대상 **[!UICONTROL Control]** 규칙을 사용하면 게재 라이프사이클의 어느 지점에서(타깃팅 전 또는 후, 분석 종료 시 개인화 시작 시) 규칙을 적용할 것인지 결정할 수 있습니다. 의 드롭다운 목록에서 적용할 값을 선택합니다 **[!UICONTROL Phase]** 필드, **[!UICONTROL General]** 유형화 규칙의 탭입니다.

![](assets/campaign_opt_define_control_phase.png)

가능한 값은 다음과 같습니다.

* **[!UICONTROL At the start of targeting]**

   오류가 발생하는 경우 개인화 단계가 실행되지 않도록 하려면 여기에서 제어 규칙을 적용할 수 있습니다.

* **[!UICONTROL After targeting]**

   제어 규칙을 적용하려면 대상의 볼륨을 알고 있어야 하는 경우 이 단계를 선택합니다.

   예: **[!UICONTROL Check proof size]** 각 타깃팅 단계 이후에 제어 규칙이 적용됩니다. 증명 수신자가 너무 많으면 이 규칙은 메시지 개인화를 방지합니다.

* **[!UICONTROL At the start of personalization]**

   제어 시 메시지 개인화 승인이 필요한 경우 이 단계를 선택해야 합니다. 메시지 개인화는 분석 단계 동안 수행됩니다.

* **[!UICONTROL At the end of the analysis]**

   확인 시 메시지 개인화를 완료해야 하는 경우 이 단계를 선택합니다.

## 추가 구성 {#additional-configurations}

### 보내는 SMTP 트래픽 제어 {#control-outgoing-smtp-traffic}

옵션으로 **[!UICONTROL Managing affinities with IP addresses]** 이 친화성을 MTA(게재 서버)에 연결하는 필드입니다. 이를 통해 특정 게재에 대한 이메일 수를 기계 또는 출력 주소로 제한할 수 있습니다.

![](assets/campaign_opt_select_ip_affinity.png)

>[!NOTE]
>
>친화성 관리가 **[!UICONTROL Filtering]** 유형화.

<!--
>Affinities are defined in the instance configuration file, on the Adobe Campaign server. For more on this, refer to [this section](../../installation/using/about-initial-configuration.md).-->

### 캠페인 최적화 및 분산 마케팅 {#campaign-optimization-and-distributed-marketing}

다음 **[!UICONTROL Distributed Marketing]** 탭에서는 공유 캠페인이 순서 및/또는 예약될 때 적용되는 유형화 및/또는 규칙의 재매핑을 정의할 수 있습니다. 로컬 엔티티(중앙 엔티티에 대해 정의된 엔티티에 연결된 유형화/규칙이 중앙 엔티티에 연결된 규칙/유형화를 대체합니다. 다시 매핑을 사용하면 중앙 엔티티 규칙을 캠페인을 순서를 지정하는 로컬 엔티티에 조정할 수 있습니다.

![](assets/simu_campaign_opti_distrib_mkg.png)

>[!NOTE]
>
>유형화 및 유형화 규칙에서 **[!UICONTROL Distributed Marketing]** 라이센스에 이 옵션이 포함되어 있는 경우 탭이 추가됩니다. 사용권 계약을 확인하십시오.\
>분산 마케팅에 대한 자세한 내용은 [이 섹션](../distributed-marketing/about-distributed-marketing.md).
