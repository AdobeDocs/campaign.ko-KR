---
product: campaign
title: 목록으로 보고서 보내기
description: 워크플로우를 사용하여 목록으로 보고서를 보내는 방법 알아보기
feature: Workflows
exl-id: 5bc576d0-cab7-4d26-a3a5-91982a00e356
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 3%

---

# 목록으로 보고서 보내기{#send-a-report-to-a-list}

이 사용 사례에서는 월별 기본 제공 세트를 생성하는 방법을 자세히 설명합니다 **[!UICONTROL Tracking indicators]** 수신자 목록으로 보내는 방법 및 PDF 형식으로 보고서를 보냅니다.

![](assets/use_case_report_intro.png)

이 사용 사례에 대한 기본 구현 단계는 다음과 같습니다.

* 이 보고서의 수신자 목록을 만듭니다. [자세히 알아보기](#step-1--create-the-recipient-list)
* 워크플로우를 실행할 때마다 새 게재를 만드는 게재 템플릿을 만듭니다. [자세히 알아보기](#step-2--create-the-delivery-template)
* 보고서를 PDF 형식으로 생성하여 수신자 목록으로 보내는 워크플로우를 만듭니다. [자세히 알아보기](#step-3--create-the-workflow)).

## 1단계: 수신자 목록 만들기 {#step-1--create-the-recipient-list}

타겟팅된 수신자 목록을 만들려면 아래 단계를 수행하십시오.

1. 다음 위치로 이동합니다. **[!UICONTROL Profiles and targets]** 탭에서 **[!UICONTROL Lists]** 링크를 클릭합니다.
1. **[!UICONTROL Create]** 버튼을 클릭합니다.
1. 선택 **[!UICONTROL New list]** 로 전송할 보고서에 대한 새 수신자 목록을 만듭니다.

목록 만들기에 대한 자세한 내용은 [이 섹션](../../v8/audiences/create-audiences.md).

## 2단계: 게재 템플릿 만들기 {#step-2--create-the-delivery-template}

게재 템플릿을 만들려면 아래 단계를 수행하십시오.

1. 다음 위치로 이동합니다. **[!UICONTROL Resources > Templates > Delivery templates]** Adobe Campaign 탐색기의 노드 및 **[!UICONTROL Email delivery]** 기본 제공 템플릿.

   게재 템플릿 만들기에 대한 자세한 내용은 [이 섹션](../../v8/send/create-templates.md).

1. 템플릿 매개 변수를 입력합니다. 레이블, target(이전에 만든 수신자 목록), 제목 및 콘텐츠

   워크플로우를 실행할 때마다 **[!UICONTROL Tracking indicators]** 보고서는 다음에 설명된 대로 업데이트됩니다. [3단계: 워크플로우 만들기](#step-3--creating-the-workflow)).

1. 게재에 최신 버전의 보고서를 포함하려면 **[!UICONTROL Calculated attachment]**:

   * 을(를) 클릭합니다. **[!UICONTROL Attachments]** 링크를 클릭하고 **[!UICONTROL Add]** 버튼을 클릭합니다. **[!UICONTROL Calculated attachment...]**&#x200B;을(를) 선택합니다.

      ![](assets/use_case_report_4.png)

   * 에서 **[!UICONTROL Type]** 드롭다운 목록에서 최신 옵션을 선택합니다. **[!UICONTROL File name is computed during delivery of each message (it may then depend on the recipient profile)]**.

      ![](assets/use_case_report_5.png)

      에 입력한 값 **[!UICONTROL Label]** 최종 게재에는 필드가 표시되지 않습니다.

   * 텍스트 영역에 파일의 액세스 경로와 이름을 입력합니다.

      ![](assets/use_case_report_6.png)

      >[!CAUTION]
      >
      >경로 및 이름은 **[!UICONTROL JavaScript code]** 워크플로우의 활동 유형(에 설명된 대로) [3단계: 워크플로우 만들기](#step-3--creating-the-workflow).

   * 을(를) 선택합니다 **[!UICONTROL Advanced]** 탭 및 확인 **[!UICONTROL Script the name of the file name displayed in the mails sent]**. 텍스트 영역에서 최종 게재에 있는 첨부 파일의 이름을 입력합니다.

      ![](assets/use_case_report_6b.png)

## 3단계: 워크플로우 만들기 {#step-3--creating-the-workflow}

이 사용 사례에 대해 다음 워크플로우를 만듭니다.

![](assets/use_case_report_8.png)

여기에서는 다음 세 가지 활동을 사용합니다.

* A **[!UICONTROL Scheduler]** 한 달에 한 번 워크플로우를 실행하는 활동,
* A **[!UICONTROL JavaScript code]** PDF 형식으로 보고서를 생성하는 활동,
* A **[!UICONTROL Delivery]** 이전에 만든 게재 템플릿을 참조하는 활동입니다.

이 워크플로우를 빌드하려면 아래 단계를 수행하십시오.

1. 다음 위치로 이동합니다. **[!UICONTROL Administration > Production > Technical workflows]** campaign 노드 아래에 워크플로우를 저장하고 새 폴더를 만듭니다.
1. 새 워크플로우를 만듭니다.

   ![](assets/use_case_report_7.png)

1. 다음을 추가하여 시작합니다 **[!UICONTROL Scheduler]** 활동을 입력하고 워크플로우가 해당 월의 첫 번째 월요일에 실행되도록 구성합니다.

   ![](assets/use_case_report_9.png)

   스케줄러 구성에 대한 자세한 내용은 [스케줄러](scheduler.md).

1. 그런 다음 **[!UICONTROL JavaScript code]** 유형 활동.

   ![](assets/use_case_report_10.png)

   편집 영역에 다음 코드를 입력합니다.

   ```sql
   var reportName = "indicators";
   var path = "/tmp/indicators.pdf";
   var exportFormat = "PDF";
   var reportURL = "<PUT THE URL OF THE REPORT HERE>";
   var _ctx = <ctx _context="global" _reportContext="deliveryFeedback" />
   var isAdhoc = 0;
   
   xtk.report.export(reportName, _ctx, exportFormat, path, isAdhoc);
   ```


   다음 변수를 사용하여 다음을 수행하십시오.

   * **var reportName**: 보고서의 내부 이름을 큰따옴표로 입력합니다. 이 경우 의 내부 이름입니다 **추적 표시기** 보고서가 &quot;deliveryFeedback&quot;입니다.
   * **var 경로**: 파일(&quot;tmp&quot;), 파일(&quot;deliveryFeedback&quot;)과 파일 확장명(&quot;.pdf&quot;)의 저장 경로를 입력합니다. 이 경우 내부 이름을 파일 이름으로 사용했습니다. 값은 큰따옴표 사이에 있어야 하고 &quot;+&quot; 문자로 구분해야 합니다.

      >[!CAUTION]
      >
      >파일을 서버에 저장해야 합니다. 과 같은 경로 및 같은 이름을 입력해야 합니다. **[!UICONTROL General]** 계산된 첨부 파일에 대한 편집 창의 탭(자세히 표시) [여기](#step-2--create-the-delivery-template)).

   * **var exportFormat**: 파일(&quot;PDF&quot;)의 내보내기 형식을 입력합니다.
   * **var_ctx** (컨텍스트): 이 경우에는 **[!UICONTROL Tracking indicators]** 글로벌 컨텍스트에서 보고합니다.

1. 을(를) 추가하여 마칩니다. **[!UICONTROL Delivery]** 활동을 만들 때 사용할 수 있는 옵션은 다음과 같습니다.

   ![](assets/use_case_report_11.png)

   * **[!UICONTROL Delivery]**: 선택 **[!UICONTROL New, created from a template]**&#x200B;을 누르고 이전에 만든 게재 템플릿을 선택합니다.
   * 대상 **[!UICONTROL Recipients]** 및 **[!UICONTROL Content]** 필드, 선택 **[!UICONTROL Specified in the delivery]**.
   * **[!UICONTROL Action to perform]**: 선택 **[!UICONTROL Prepare and start]**.
   * 확인 취소 **[!UICONTROL Generate an outbound transition]** 및 **[!UICONTROL Process errors]** 옵션.

1. 변경 사항을 저장하고 워크플로우를 시작합니다. 메시지가 첨부된 보고서와 함께 매월 첫 번째 월요일에 수신자 목록으로 전송됩니다.
