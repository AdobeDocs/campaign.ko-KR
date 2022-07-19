---
product: campaign
title: 웹 다운로드
description: 웹 다운로드 워크플로우 활동에 대해 자세히 알아보기
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 1%

---

# 웹 다운로드{#web-download}



다음 **웹 다운로드** 활동은 명시적 URL, 외부 계정 또는 Adobe Campaign 인스턴스에서 파일 다운로드를 시작합니다. HTTP 프로토콜이 사용됩니다. GET 또는 POST 다운로드일 수 있습니다.

## 속성 {#properties}

1. **웹 파일 선택**

   다운로드할 파일을 지정하려면 파일 URL을 입력하고 파일이 저장되는 외부 HTTP 계정을 사용하거나 Adobe Campaign 인스턴스를 통해 파일을 로드할 수 있습니다. 사용 가능한 매개 변수는 아래에 자세히 설명되어 있습니다.

   * 다운로드할 파일의 URL을 직접 입력하려면 **[!UICONTROL Explicit URL]** 옵션을 선택하고 해당 필드에 URL을 지정합니다. 이 URL은 변수 데이터로 생성할 수 있습니다.

      ![](assets/download_web_edit.png)

   * 를 사용하려면 **[!UICONTROL External account]**&#x200B;드롭다운 목록에서 계정을 선택하고 다운로드할 파일을 지정합니다.

      외부 계정은 **[!UICONTROL Administration > Platform > External accounts]** 노드 아래에 나열된 상태로 남아 있습니다. 계정 매개 변수는 **[!UICONTROL Edit link]** 아이콘.

      ![](assets/download_web_edit_external.png)

   * Adobe Campaign 인스턴스에서 파일을 다운로드하려면 다음을 선택합니다 **[!UICONTROL Adobe Campaign Instance]** 선택 사항입니다.

      ![](assets/download_web_edit_instance.png)

1. **파일 내역**

   다음 **[!UICONTROL File historization settings...]** 링크를 통해 파일 저장소 디렉토리 및 이 디렉토리의 제거 빈도를 지정할 수 있습니다.

   ![](assets/download_web_edit_hist.png)

   다음 옵션을 사용할 수 있습니다.

   * **[!UICONTROL Use a default storage directory]**: 파일은 항상 처리되기 전에 이동됩니다. 이 옵션을 선택하면 파일이 기본 스토리지 디렉토리( **vars** Adobe Campaign 설치 폴더의 디렉토리). 저장소 디렉토리를 지정하려면 상자를 선택 취소하고 해당 경로를 **[!UICONTROL Storage directory]** 필드
   * **[!UICONTROL Number of files]**: 저장소 디렉토리에 보관할 최대 파일 수를 입력합니다.
   * **[!UICONTROL Maximum size (in Mb)]**: 저장소 디렉토리의 최대 용량(MB)을 입력합니다.

   각 파일은 정의된 제거 규칙을 적용받기 전에 24시간 동안 유지됩니다. 제거는 활동이 시작되기 직전에 수행되므로 진행 중인 워크플로우 파일을 고려하지 않습니다.

   파일은 해당 페이지의 함수로 삭제됩니다(가장 오래된 파일부터 최신 파일까지). 가장 오래된 파일은 제거 규칙이 모두 확인될 때까지 삭제됩니다. 따라서 100개 파일 제한이 정의된 경우 스토리지 디렉토리에는 워크플로우가 시작되기 전에 항상 100개의 최신 파일과 진행 중인 워크플로에서 처리되는 파일이 포함됩니다.

   에 대한 제한을 더 이상 설정하지 않으려는 경우 **[!UICONTROL Number of files]** 및 **[!UICONTROL Maximum size (in Mb)]** 선택 사항에서 0을 값으로 입력합니다.

1. **고급 매개 변수**

   다음 **[!UICONTROL Advanced parameters...]** 링크를 통해 아래에 표시된 추가 옵션을 지정할 수 있습니다.

   ![](assets/download_web_edit_advanced.png)

   다음 **[!UICONTROL Process errors]** 옵션이 [처리 오류](monitor-workflow-execution.md#processing-errors).

## 출력 매개 변수 {#output-parameters}

* 파일 이름: 다운로드한 파일의 전체 이름입니다.
