---
product: campaign
title: 감사 추적
description: Campaign 감사 추적을 사용하여 인스턴스를 모니터링하는 방법 알아보기
feature: Audit Trail, Monitoring, Workflows
exl-id: 6a937575-42d4-4dc5-8168-43c25bb2cde6
source-git-commit: b4b361a4aabd1b33554166c2638989b99a02baec
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 2%

---

# 감사 추적{#audit-trail}

다음 **[!UICONTROL Audit trail]** Adobe Campaign의 기능은 인스턴스 내의 중요한 엔티티에 대한 모든 수정 사항의 세부 레코드(일반적으로 인스턴스의 원활한 작업에 상당한 영향을 주는 항목)를 제공합니다. 실시간 로그로 작동하면서 작업 및 이벤트가 발생할 때의 자세한 목록을 캡처합니다.

>[!NOTE]
>
>Adobe Campaign은 사용자 권한, 템플릿, 개인화 또는 캠페인 내에서 수행된 변경 사항을 감사하지 않습니다.\
>감사 추적은 인스턴스 관리자만 관리할 수 있습니다.

+++ 감사 추적 사용 가능한 엔터티에 대해 자세히 알아보기

* **스키마 감사 추적**: 스키마에 대한 변경 사항을 살펴보고 스키마가 수정된 사용자 및 수정된 시기를 식별할 수 있습니다.

  스키마에 대한 자세한 내용은 [페이지](../dev/schemas.md).

* **워크플로우 감사 추적** 은(는) 다음을 포함하여 워크플로와 관련된 모든 작업을 추적합니다.

   * 시작
   * 일시 정지
   * 정지
   * 다시 시작
   * 정리 - 작업 삭제 내역에 해당합니다.
   * 시뮬레이션 모드에서 시작 작업과 동일한 시뮬레이션
   * 지금 대기 중인 작업 실행 작업과 동일한 절전 모드 해제
   * 무조건 정지

  워크플로우에 대한 자세한 내용은 다음을 참조하십시오. [페이지](../../automation/workflow/about-workflows.md).

  워크플로우를 모니터링하는 방법에 대한 자세한 내용은 [전용 섹션](../../automation/workflow/monitor-workflow-execution.md).

* **옵션 감사 추적** 을(를) 통해 활동 및 옵션에 대한 마지막 수정 사항을 확인할 수 있습니다.

  옵션에 대한 자세한 내용은 다음을 참조하십시오. [페이지](https://experienceleague.adobe.com/en/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options).

* **게재 감사 추적** 을(를) 통해 활동 및 게재에 수행된 마지막 수정 사항을 확인할 수 있습니다.

  게재에 대한 자세한 내용은 다음을 참조하십시오. [페이지](../start/create-message.md).

* **외부 계정** 기술 워크플로우 또는 캠페인 워크플로우와 같은 기술 프로세스에서 사용하는 외부 계정에 대한 수정 사항을 확인할 수 있습니다.

  외부 계정에 대한 자세한 내용은 다음을 참조하십시오. [페이지](../config/external-accounts.md).

* **게재 매핑** 을(를) 통해 활동 및 게재 매핑에 대한 최근 수정 사항을 모니터링할 수 있습니다.

  게재 매핑에 대한 자세한 내용은 다음을 참조하십시오 [페이지](../audiences/target-mappings.md).

* **웹 애플리케이션** 입력 및 선택 필드가 있는 페이지를 만드는 데 사용되는 Campaign V8에서 웹 양식에 대해 수정된 내용을 확인할 수 있으며, 여기에는 데이터베이스의 데이터가 포함될 수 있습니다.

  웹 애플리케이션에 대한 자세한 내용은 다음을 참조하십시오. [페이지](../dev/webapps.md).

* **오퍼** 을(를) 통해 활동 및 오퍼에 대한 마지막 수정 사항을 확인할 수 있습니다.

  오퍼에 대한 자세한 내용은 다음을 참조하십시오. [페이지](../interaction/interaction.md).

* **연산자** 을 사용하면 운영자에 대한 활동 및 최근 수정 사항을 모니터링할 수 있습니다.

  연산자에 대한 자세한 내용은 다음을 참조하십시오. [페이지](../interaction/interaction-operators.md).

+++

## 감사 추적 액세스 {#accessing-audit-trail}

인스턴스의 **[!UICONTROL Audit trail]**:

1. 액세스 **[!UICONTROL Explorer]** 인스턴스의 메뉴입니다.

1. 아래 **[!UICONTROL Administration]** 메뉴, 선택 **[!UICONTROL Audit]** 그러면 **[!UICONTROL Audit Trail]**.

   ![](assets/audit-trail-1.png)

1. 다음 **[!UICONTROL Audit trail]** 엔티티 목록이 있는 창이 열립니다. Adobe Campaign은 다른 엔티티에 대한 만들기, 편집 및 삭제 작업을 감사합니다.

   마지막 수정 사항에 대해 자세히 알아보려면 엔티티 중 하나를 선택합니다.

1. 다음 **[!UICONTROL Audit entity]** 창은 다음과 같이 선택한 엔티티에 대한 자세한 정보를 제공합니다.

   * **[!UICONTROL Type]**: 워크플로우, 옵션, 게재 또는 스키마.
   * **[!UICONTROL Entity]**: 활동의 내부 이름입니다.
   * **[!UICONTROL Modified by]**: 이 엔티티를 마지막으로 수정한 사람의 사용자 이름입니다.
   * **[!UICONTROL Action]**: 이 엔티티에서 마지막으로 수행된 작업(생성됨, 수정됨 또는 삭제됨)입니다.
   * **[!UICONTROL Modification date]**: 이 엔티티에 대해 마지막으로 수행된 작업의 날짜입니다.

   ![](assets/audit-trail-2.png)

>[!NOTE]
>
>기본적으로 보존 기간은 180일로 설정되어 있습니다. **[!UICONTROL Audit logs]**. 이 값은 배포 마법사에서 수정할 수 있습니다.

## 감사 추적 활성화/비활성화 {#enable-disable-audit-trail}

감사 추적은 예를 들어 데이터베이스에 일부 공간을 저장하려는 경우 특정 활동에 대해 쉽게 활성화하거나 비활성화할 수 있습니다.

방법은 다음과 같습니다.

1. 액세스 **[!UICONTROL Explorer]** 인스턴스의 메뉴입니다.

1. 아래 **[!UICONTROL Administration]** 메뉴, 선택 **[!UICONTROL Platform]** 그러면 **[!UICONTROL Options]**.

1. 활성화/비활성화하려는 엔티티에 따라 다음 옵션 중 하나를 선택합니다.

   * 워크플로우의 경우: **[!UICONTROL XtkAudit_Workflows]**
   * 스키마의 경우 **[!UICONTROL XtkAudit_DataSchema]**
   * 옵션의 경우: **[!UICONTROL XtkAudit_Option]**
   * 게재의 경우: **[!UICONTROL XtkAudit_Delivery]**
   * 외부 계정의 경우: **[!UICONTROL XtkAudit_ExtAccount]**
   * 게재 매핑용: **[!UICONTROL XtkAudit_DeliveryMapping]**
   * 웹 애플리케이션의 경우: **[!UICONTROL XtkAudit_WebApp]**
   * 오퍼의 경우: **[!UICONTROL XtkAudit_Offer]**
   * 연산자: **[!UICONTROL XtkAudit_Operator]**
   * 모든 엔티티에 대해: **[!UICONTROL XtkAudit_Enable_All]**

   ![](assets/audit-trail-3.png)

1. 변경 **[!UICONTROL Value]** 엔티티를 활성화하려면 1로 설정하고, 엔티티를 비활성화하려면 0으로 설정합니다.

   ![](assets/audit-trail-4.png)

1. **[!UICONTROL Save]**&#x200B;를 클릭합니다.
