---
title: CRM 커넥터 데이터 동기화
description: Campaign과 CRM 간의 데이터 관리
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 2a7ae88e-d47f-416b-84cd-986ab9be6aef
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 1%

---

# Campaign과 CRM 간에 데이터 동기화 {#data-synchronization}

Adobe Campaign과 CRM 간의 데이터 동기화는 **CRM 커넥터** 워크플로우 활동.

예를 들어 Microsoft Dynamics 데이터를 Adobe Campaign으로 가져오려면 다음 유형의 워크플로우를 만드십시오.

![](assets/ms-dyn-wf.png)

이 워크플로우는 Microsoft Dynamics를 통해 연락처를 가져오고, 기존 Adobe Campaign 데이터와 동기화하며, 중복 연락처를 삭제하고, Adobe Campaign 데이터베이스를 업데이트합니다.

다음 **[!UICONTROL CRM Connector]** 데이터를 동기화하려면 활동을 구성해야 합니다.

![](assets/crm-connector-ms-dyn.png)

이 활동을 사용하면 다음 작업을 수행할 수 있습니다.

* CRM에서 가져오기 - [추가 정보](#importing-from-the-crm)
* CRM으로 내보내기 - [추가 정보](#exporting-to-the-crm)
* CRM에서 삭제된 개체 가져오기 - [추가 정보](#importing-objects-deleted-in-the-crm)
* CRM에서 개체 삭제 - [추가 정보](#deleting-objects-in-the-crm)

![](assets/crm-remote-op.png)

동기화를 구성할 CRM과 일치하는 외부 계정을 선택한 다음 동기화할 개체를 선택합니다. 계정, 기회, 리드, 연락처 등

![](assets/crm-remote-obj.png)

이 활동의 구성은 수행할 프로세스에 따라 다릅니다. 다양한 구성은 아래에 자세히 설명되어 있습니다.

## CRM에서 가져오기 {#importing-from-the-crm}

Adobe Campaign에서 CRM을 통해 데이터를 가져오려면 다음 유형의 워크플로우를 만들어야 합니다.

![](assets/crm-wf-import.png)

1. 선택 **[!UICONTROL Import from the CRM]** 작업.
1. 에서 **[!UICONTROL Remote object]** 드롭다운 목록에서 가져올 객체를 선택합니다. 이 개체는 커넥터 구성 중에 Adobe Campaign에서 만든 테이블 중 하나와 일치합니다.
1. 에서 **[!UICONTROL Remote fields]** 섹션에서 가져올 필드를 입력합니다.

   필드를 추가하려면 **[!UICONTROL Add]** 도구 모음에서 버튼을 클릭한 다음 **[!UICONTROL Edit expression]** 아이콘.

   필요한 경우 **[!UICONTROL Conversion]** 열. 가능한 변환 유형은에 자세히 설명되어 있습니다 [이 섹션](#data-format).

   >[!CAUTION]
   >
   >CRM과 Adobe Campaign에서 개체를 연결하려면 CRM에 있는 레코드의 식별자가 필요합니다. 상자가 승인되면 자동으로 추가됩니다.
   >
   >CRM 측의 마지막 수정 날짜도 증분 데이터 가져오기에 필수입니다.

1. 필요에 따라 가져올 데이터를 필터링할 수 있습니다. 이렇게 하려면 **[!UICONTROL Edit the filter...]** 링크를 클릭합니다.

   다음 예에서는 Adobe Campaign은 2021년 11월 1일 이후 일부 활동이 기록된 연락처만 가져옵니다.

   ![](assets/crm-task-import-filter.png)

   >[!CAUTION]
   >
   >데이터 필터링 모드와 관련된 제한 사항은 [이 섹션](#filtering-data).

1. 을(를) 선택합니다 **[!UICONTROL Use automatic index...]** 날짜와 마지막 수정 내용에 따라 CRM과 Adobe Campaign 간의 증분 개체 동기화를 자동으로 관리하는 옵션입니다.

   이 작업에 대한 자세한 정보는 [이 섹션](#variable-management)을 참조하십시오.

### 변수 관리 {#variable-management}

를 활성화합니다 **[!UICONTROL Automatic index]** 마지막 가져오기 이후 수정된 객체만 수집할 옵션입니다.

![](assets/use-auto-index.png)

마지막 동기화 날짜는 기본적으로 구성 창에 지정된 옵션에 저장됩니다. **LASTIMPORT_&lt;%=instance.internalName%>_&lt;%=activityName%>**.

>[!NOTE]
>
>이 메모는 원본에만 적용됩니다 **[!UICONTROL CRM Connector]** 활동. 다른 CRM 활동의 경우 이 프로세스는 자동으로 수행됩니다.
>
>이 옵션은 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**. 텍스트 옵션이어야 하며 해당 값이 다음 형식과 일치해야 합니다. **yyyy/MM/dd hh:mm:ss**.
> 
>추가로 가져오려면 이 옵션을 수동으로 업데이트해야 합니다.

최신 변경 사항을 식별하기 위해 고려할 원격 CRM 필드를 지정할 수 있습니다.

기본적으로 다음 필드가 사용됩니다(지정된 순서로).

* Microsoft Dynamics의 경우: **수정 사항**,
* Salesforce.com의 경우: **마지막 수정 날짜**, **SystemModstamp**.

활성화 **[!UICONTROL Automatic index]** 옵션은 **[!UICONTROL JavaScript code]** 유형 활동. 이러한 활동은 다음과 같습니다.

* **vars.crmOptionName**: 마지막 가져오기 날짜가 포함된 옵션의 이름입니다.
* **vars.crmStartImport**: 마지막 데이터 가져오기의 시작 날짜(포함)입니다.
* **vars.crmEndDate**: 마지막 데이터 가져오기의 종료 날짜(제외).

   >[!NOTE]
   >
   >이 날짜는 다음 형식으로 표시됩니다. **yyyy/MM/dd hh:mm:ss**.

### 데이터 필터링 {#filtering-data}

다양한 CRM을 사용하여 효율적인 작업을 수행하려면 다음 규칙을 사용하여 필터를 만들어야 합니다.

* 각 필터링 수준은 하나의 유형의 연산자만 사용할 수 있습니다.
* AND NOT 연산자는 지원되지 않습니다.
* 비교는 null 값(&#39;is empty&#39;/&#39;is not empty&#39; type) 또는 숫자만 사용할 수 있습니다. 즉, 값(오른쪽 열)이 평가되고 이 평가의 결과는 숫자여야 합니다. 따라서 JOIN 유형 비교는 지원되지 않습니다.
* 오른쪽 열에 포함된 값은 JavaScript로 평가됩니다.
* 조인 비교는 지원되지 않습니다.
* 왼쪽 열의 표현식은 필드여야 합니다. 여러 표현식, 숫자 등의 조합일 수 없습니다.

### 정렬 기준 {#order-by}

Microsoft Dynamics 및 Salesforce.com에서는 가져올 원격 필드를 오름차순이나 내림차순으로 정렬할 수 있습니다.

이렇게 하려면 **[!UICONTROL Order by]** 열을 연결하고 목록에 추가합니다.

목록에 있는 열의 순서는 정렬 순서입니다.

![](assets/crm-import-order.png)

### 기록 식별 {#record-identification}

CRM에 포함된(및 필터링될 수 있는) 요소를 가져오는 대신 워크플로우에서 미리 계산된 모집단을 사용할 수 있습니다.

이렇게 하려면 **[!UICONTROL Use the population calculated upstream]** 옵션을 선택하고 원격 식별자를 포함하는 필드를 지정합니다.

그런 다음 가져올 인바운드 모집단의 필드를 아래와 같이 선택합니다.

![](assets/use-population-calc-upstream.png)

## CRM으로 내보내기 {#exporting-to-the-crm}

Adobe Campaign 데이터를 CRM에 내보내 전체 컨텐츠를 CRM 데이터베이스에 복사합니다.

데이터를 CRM에 내보내려면 다음 유형의 워크플로우를 만듭니다.

![](assets/crm-export-diagram.png)

1. 선택 **[!UICONTROL Export to CRM]** 작업.
1. 로 이동합니다. **[!UICONTROL Remote object]** 드롭다운 목록을 선택하고 내보낼 객체를 선택합니다. 이 개체는 커넥터 구성 중에 Adobe Campaign에서 만든 테이블 중 하나와 일치합니다.

   >[!CAUTION]
   >
   >의 내보내기 기능 **[!UICONTROL CRM Connector]** 활동은 CRM에 필드를 삽입하거나 업데이트할 수 있습니다. CRM에서 필드 업데이트를 활성화하려면 원격 테이블의 기본 키를 지정합니다. 키가 없으면 데이터가 업데이트되지 않고 삽입됩니다.

1. 내보내기 속도가 빨라야 하는 경우  **[!UICONTROL Export in Batches]** 선택 사항입니다.

   ![](assets/crm-export-batch.png)

1. 에서 **[!UICONTROL Mapping]** 섹션을 클릭합니다. **[!UICONTROL New]** 내보낼 필드와 CRM에서 매핑을 지정합니다.

   필드를 추가하려면 **[!UICONTROL Add]** 도구 모음에서 버튼을 클릭한 다음 **[!UICONTROL Edit expression]** 아이콘.

   >[!NOTE]
   >
   >필드에 대해 일치하는 항목이 없으면 값을 업데이트할 수 없습니다. CRM에 바로 삽입됩니다.

   필요한 경우 **[!UICONTROL Conversion]** 열. 가능한 변환 유형은에 자세히 설명되어 있습니다 [이 섹션](#data-format).

   >[!NOTE]
   >
   >내보낼 레코드 목록과 내보내기 결과는 워크플로우가 완료되거나 다시 시작할 때까지 액세스할 수 있는 임시 파일에 저장됩니다. 이렇게 하면 오류가 발생할 경우 프로세스를 안전하게 시작할 수 있습니다.

## 추가 구성 {#additional-configurations}

### 데이터 형식 {#data-format}

데이터 형식을 CRM으로 가져오거나 CRM에서 가져올 때 즉시 변환할 수 있습니다.

이렇게 하려면 일치하는 열에서 적용할 전환을 선택합니다.

![](assets/crm-task-import.png)

다음 **[!UICONTROL Default]** 모드 는 자동 데이터 전환을 적용합니다. 대부분의 경우 데이터 복사/붙여넣기와 같습니다. 하지만 시간대 관리는 적용됩니다.

가능한 기타 전환은 다음과 같습니다.

* **[!UICONTROL Date only]**: 날짜 + 시간 유형 필드를 삭제합니다.
* **[!UICONTROL Without time offset]**: 기본 모드에서 적용된 시간대 관리를 취소합니다.
* **[!UICONTROL Copy/Paste]**: 문자열(변환 없음)과 같은 원시 데이터를 사용합니다.

### 처리 오류 {#error-processing}

데이터 가져오기 또는 내보내기의 프레임워크 내에서 특정 프로세스를 오류 및 거부에 적용할 수 있습니다. 이렇게 하려면 **[!UICONTROL Keep the rejections in a file]** 및 **[!UICONTROL Process errors]** 옵션 **[!UICONTROL Behavior]** 탭.

![](assets/crm-export-options.png)

이러한 옵션은 관련 출력 전환을 추가합니다.

![](assets/crm-export-transitions.png)

그런 다음 관련 활동을 삽입하여 데이터를 처리합니다. 예를 들어 **대기** 활동 및 오류에 대한 다시 시도 예약.

다음 **[!UICONTROL Reject]** 출력 전환을 사용하면 오류 메시지 및 코드와 관련된 특정 열이 포함된 출력 스키마에 액세스할 수 있습니다. Salesforce.com의 경우 이 열은 **errorSymbol** (오류 기호, 오류 코드와 다름), **errorMessage** (오류 컨텍스트에 대한 설명)

## CRM에서 삭제된 개체 가져오기 {#importing-objects-deleted-in-the-crm}

CRM에서 삭제된 개체를 Adobe Campaign에 가져올 수 있습니다.

1. 선택 **[!UICONTROL Import objects deleted in the CRM]** 작업.
1. 로 이동합니다. **[!UICONTROL Remote object]** 드롭다운 목록을 선택하고 프로세스의 관련 객체를 선택합니다. 이 개체는 커넥터 구성 중에 Adobe Campaign에서 만든 테이블 중 하나와 일치합니다.
1. 에서 고려할 삭제 기간을 지정합니다 **[!UICONTROL Start date]** 그리고 **[!UICONTROL End date]** 필드(날짜가 포함되어 있음).

   >[!CAUTION]
   >
   >삭제 기간은 CRM 관련 제한 사항과 일치해야 합니다. 예를 들어 Salesforce.com의 경우 30일 전에 삭제된 요소는 복구할 수 없습니다.

## CRM에서 개체 삭제 {#deleting-objects-in-the-crm}

CRM에서 개체를 삭제하려면 삭제할 원격 요소의 기본 키를 지정합니다.

다음 **[!UICONTROL Behavior]** 탭에서는 거부 처리를 활성화할 수 있습니다. 이 옵션은 **[!UICONTROL CRM connector]** 활동. 자세한 내용은 [처리 오류](#error-processing).
