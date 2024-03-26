---
product: campaign
title: 목록으로 보고서 보내기
description: 워크플로우가 있는 목록으로 보고서를 보내는 방법을 알아봅니다
feature: Workflows
exl-id: 5bc576d0-cab7-4d26-a3a5-91982a00e356
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 3%

---

# 목록으로 보고서 보내기{#send-a-report-to-a-list}

이 사용 사례에서는 즉시 사용할 수 있는 월별 생성 방법을 자세히 설명합니다 **[!UICONTROL Tracking indicators]** PDF 형식으로 보고하고 수신자 목록으로 보내는 방법을 알아봅니다.

![](assets/use_case_report_intro.png)

이 사용 사례의 주요 구현 단계는 다음과 같습니다.

* 이 보고서의 수신자 목록을 만듭니다. [자세히 알아보기](#step-1--create-the-recipient-list)
* 워크플로우가 실행될 때마다 새 게재를 만드는 게재 템플릿을 만듭니다. [자세히 알아보기](#step-2--create-the-delivery-template)
* PDF 형식으로 보고서를 생성하여 수신자 목록으로 전송하는 워크플로우를 만듭니다. [자세히 알아보기](#step-3--create-the-workflow)).

## 1단계: 수신자 목록 만들기 {#step-1--create-the-recipient-list}

타겟팅된 수신자 목록을 만들려면 아래 단계를 수행하십시오.

1. 다음으로 이동 **[!UICONTROL Profiles and targets]** 탭을 클릭하고 **[!UICONTROL Lists]** 링크를 클릭합니다.
1. **[!UICONTROL Create]** 버튼을 클릭합니다.
1. 선택 **[!UICONTROL New list]** 및 (으)로 보낼 보고서에 대한 새 수신자 목록을 만듭니다.

목록 만들기에 대한 자세한 내용은 [이 섹션](../../v8/audiences/create-audiences.md).

## 2단계: 게재 템플릿 만들기 {#step-2--create-the-delivery-template}

게재 템플릿을 만들려면 아래 단계를 수행하십시오.

1. 다음으로 이동 **[!UICONTROL Resources > Templates > Delivery templates]** Adobe Campaign 탐색기의 노드 및 복제 **[!UICONTROL Email delivery]** 기본 제공 템플릿입니다.

   게재 템플릿 만들기에 대한 자세한 내용은 [이 섹션](../../v8/send/create-templates.md).

1. 템플릿 매개 변수(레이블, 대상(이전에 만든 수신자 목록), 제목 및 컨텐츠)를 입력합니다.

   워크플로우가 실행될 때마다 **[!UICONTROL Tracking indicators]** 보고서가에 설명된 대로 업데이트됩니다. [3단계: 워크플로우 만들기](#step-3--creating-the-workflow)).

1. 게재에 최신 버전의 보고서를 포함하려면 를 추가해야 합니다. **[!UICONTROL Calculated attachment]**:

   * 다음을 클릭합니다. **[!UICONTROL Attachments]** 링크를 클릭하고 옆에 있는 화살표를 클릭합니다 **[!UICONTROL Add]** 단추를 클릭합니다. **[!UICONTROL Calculated attachment...]**&#x200B;을(를) 선택합니다.

     ![](assets/use_case_report_4.png)

   * 다음에서 **[!UICONTROL Type]** 드롭다운 목록에서 최신 옵션을 선택합니다. **[!UICONTROL File name is computed during delivery of each message (it may then depend on the recipient profile)]**.

     ![](assets/use_case_report_5.png)

     에 입력한 값 **[!UICONTROL Label]** 최종 게재에는 필드가 표시되지 않습니다.

   * 텍스트 영역에 파일의 액세스 경로와 이름을 입력합니다.

     ![](assets/use_case_report_6.png)

     >[!CAUTION]
     >
     >경로 및 이름은 다음에 입력한 것과 동일해야 합니다 **[!UICONTROL JavaScript code]** 에 설명된 대로 워크플로우의 활동을 입력합니다. [3단계: 워크플로우 만들기](#step-3--creating-the-workflow).

   * 다음 항목 선택 **[!UICONTROL Advanced]** tab 키 및 check **[!UICONTROL Script the name of the file name displayed in the mails sent]**. 텍스트 영역에 최종 게재에 있는 첨부 파일의 이름을 입력합니다.

     ![](assets/use_case_report_6b.png)

## 3단계: 워크플로우 만들기 {#step-3--creating-the-workflow}

이 사용 사례에 대해 다음 워크플로우를 만듭니다.

![](assets/use_case_report_8.png)

세 가지 활동을 사용합니다.

* A **[!UICONTROL Scheduler]** 활동은 한 달에 한 번 워크플로우를 실행합니다.
* A **[!UICONTROL JavaScript code]** 활동은 PDF 형식으로 보고서를 생성합니다.
* A **[!UICONTROL Delivery]** 이전에 만든 게재 템플릿을 참조하는 활동.

이 워크플로우를 빌드하려면 아래 단계를 수행합니다.

1. 다음으로 이동 **[!UICONTROL Administration > Production > Technical workflows]** campaign의 노드가 워크플로를 저장하고 새 폴더를 만들고 탐색합니다.
1. 새 워크플로우를 만듭니다.

   ![](assets/use_case_report_7.png)

1. 을(를) 추가하여 시작 **[!UICONTROL Scheduler]** 활동을 입력하고 그 달의 첫 번째 월요일에 워크플로우가 실행되도록 구성합니다.

   ![](assets/use_case_report_9.png)

   스케줄러 구성에 대한 자세한 내용은 다음을 참조하십시오. [스케줄러](scheduler.md).

1. 그런 다음 를 추가합니다. **[!UICONTROL JavaScript code]** 활동을 입력합니다.

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


   (다음 변수 사용)

   * **var reportName**: 보고서의 내부 이름을 큰따옴표로 입력하십시오. 이 경우 의 내부 이름 **추적 표시기** 보고서는 &quot;deliveryFeedback&quot;입니다.
   * **var 경로**: 파일의 저장 경로(&quot;tmp&quot;), 파일에 지정할 이름(&quot;deliveryFeedback&quot;) 및 파일 확장자(&quot;.pdf&quot;)를 입력합니다. 이 경우 파일 이름으로 내부 이름을 사용했습니다. 값은 큰따옴표 사이여야 하며 &quot;+&quot; 문자로 구분해야 합니다.

     >[!CAUTION]
     >
     >파일을 서버에 저장해야 합니다. 과 동일한 경로와 이름을 입력해야 합니다. **[!UICONTROL General]** 계산된 첨부 파일의 편집 창 탭(자세히 표시) [여기](#step-2--create-the-delivery-template)).

   * **var exportFormat**: 파일의 내보내기 형식(&quot;PDF&quot;)을 입력합니다.
   * **var _ctx** (컨텍스트): 이 경우 **[!UICONTROL Tracking indicators]** 전역 컨텍스트에서 보고합니다.

1. 을(를) 추가하여 완료 **[!UICONTROL Delivery]** 다음 옵션을 사용하는 활동:

   ![](assets/use_case_report_11.png)

   * **[!UICONTROL Delivery]**: 선택 **[!UICONTROL New, created from a template]**&#x200B;을(를) 클릭하고 이전에 만든 게재 템플릿을 선택합니다.
   * 의 경우 **[!UICONTROL Recipients]** 및 **[!UICONTROL Content]** 필드, 선택 **[!UICONTROL Specified in the delivery]**.
   * **[!UICONTROL Action to perform]**: 선택 **[!UICONTROL Prepare and start]**.
   * 선택 취소 **[!UICONTROL Generate an outbound transition]** 및 **[!UICONTROL Process errors]** 옵션.

1. 변경 사항을 저장하고 워크플로우를 시작합니다. 첨부된 보고서와 함께 이 달의 첫 번째 월요일에 수신자 목록으로 메시지가 전송됩니다.
