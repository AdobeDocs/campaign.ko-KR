---
product: campaign
title: 파일 전송
description: 파일 전송 워크플로우 활동에 대해 자세히 알아보십시오
feature: Workflows, Data Management
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 1%

---

# 파일 전송{#file-transfer}



다음 **파일 전송** 활동을 사용하면 서버에서 파일을 받거나 보내고, 파일이 있는지 테스트하거나, 파일을 나열할 수 있습니다. 사용되는 프로토콜은 Azure Blob Storage, Amazon Simple Storage Service(S3), FTP 또는 SFTP입니다.
S3, Azure Blob 저장 공간 또는 SFTP 연결을 통해 Adobe 실시간 고객 데이터 플랫폼을 통해 Adobe Campaign으로 세그먼트 데이터를 가져올 수도 있습니다. 자세한 내용은 다음을 참조하십시오 [설명서](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html).

>[!NOTE]
>
>SFTP 서버 사용에 대한 우수 사례 및 문제 해결 방법이 자세히 설명되어 있습니다.

## 속성 {#properties}

의 드롭다운 목록을 사용합니다 **[!UICONTROL Action]** 필드의 필드를 클릭하여 활동의 작업을 선택합니다.

![](assets/file_transfert_action.png)

구성은 선택한 작업에 따라 달라집니다.

1. **파일 수신 중**

   원격 서버에 저장된 파일을 수신하려면 **[!UICONTROL File download]** 에서 **[!UICONTROL Action]** 필드. 관련 필드에 해당 URL을 지정해야 합니다.

   ![](assets/file_transfert_edit.png)

   확인 **[!UICONTROL Use an external account]** 에 구성된 Azure Blob 저장소, S3, FTP 또는 SFTP 계정에서 계정을 선택하려면 다음을 수행하십시오 **[!UICONTROL Administration > Platform > External accounts]** 노드 아래에 있어야 합니다. 그런 다음 다운로드할 파일이 포함된 서버를 지정합니다.

   ![](assets/file_transfert_edit_external.png)

1. **파일 전송**

   서버에 파일을 보내려면 **[!UICONTROL File upload]** 에서 **[!UICONTROL Action]** 필드. 에서 대상 서버를 지정해야 합니다 **[!UICONTROL Remote server]** 편집기의 섹션. 매개 변수는 인바운드 파일과 동일합니다. 위의 내용을 참조하십시오.

   소스 파일은 이전 활동에서 가져올 수 있습니다. 이 경우 **[!UICONTROL Use the file generated by the previous activity]** 옵션을 선택해야 합니다.

   ![](assets/file_transfert_edit_send.png)

   하나 이상의 다른 파일도 이러한 문제를 일으킬 수 있습니다. 선택하려면 옵션을 선택 취소하고 를 클릭합니다 **[!UICONTROL Insert]**. 전송할 파일의 액세스 경로를 지정합니다. 다른 파일을 추가하려면 **[!UICONTROL Insert]** 다시 한 번 이제 각 파일에 자체 탭이 있습니다.

   ![](assets/file_transfert_source.png)

   화살표를 사용하여 탭의 순서를 변경합니다. 파일이 서버로 전송되는 순서와 관련이 있습니다.

   다음 **[!UICONTROL Keep history of files sent]** 옵션을 사용하면 전송된 파일을 추적할 수 있습니다. 이 기록은 디렉터리에서 액세스할 수 있습니다.

1. **파일이 있는지 테스트**

   파일이 있는지 테스트하려면 **[!UICONTROL Test to see if file exists]** 옵션 **[!UICONTROL Action]** 필드. 원격 서버의 구성은 파일 다운로드와 동일합니다. 자세한 내용은 다음을 참조하십시오 [섹션](#properties).

   ![](assets/file_transfert_edit_test.png)

1. **파일 목록**

   파일을 나열하려면 **[!UICONTROL File listing]** 옵션 **[!UICONTROL Action]** 필드. 원격 서버의 구성은 파일 수신 구성과 동일합니다. 자세한 내용은 다음을 참조하십시오 [섹션](#properties).

   다음 **[!UICONTROL List all files]** 옵션, 선택 시 사용 가능 **[!UICONTROL File listing]** 작업을 사용하면 서버에 있는 모든 파일을 이벤트 변수에 저장할 수 있습니다 **vars.파일명** 파일 이름은 `\n` 자.

모든 파일 전송 옵션에 대해 두 가지 가능한 옵션이 있습니다.

* 다음 **[!UICONTROL Process missing file]** 옵션이 지정된 디렉토리에 파일이 없을 경우 활성화되는 전환을 추가합니다.
* 다음 **[!UICONTROL Process errors]** 옵션이 [처리 오류](monitor-workflow-execution.md#processing-errors).

다음 **[!UICONTROL Advanced parameters...]** 링크를 통해 다음 옵션에 액세스할 수 있습니다.

![](assets/file_transfert_advanced.png)

* **[!UICONTROL Delete the source files after transfer]**

   원격 서버의 파일을 지웁니다. 이 옵션을 선택 취소하면 SFTP 디렉토리에서 보관된 컨텐츠의 크기를 수동으로 모니터링해야 합니다.

* **[!UICONTROL Use SSL]**

   파일을 전송하는 동안 SSL 프로토콜을 통해 보안 연결을 사용할 수 있습니다.

* **[!UICONTROL Display the session logs]**

   Azure Blob 저장 공간, S3, FTP 또는 SFTP 전송 로그를 복구하여 워크플로우 로그에 포함할 수 있습니다.

* **[!UICONTROL Disable passive mode]**

   데이터 전송에 사용할 연결 포트를 지정할 수 있습니다.

다음 **[!UICONTROL File historization settings...]** 링크를 통해 [웹 다운로드](web-download.md) (**[!UICONTROL File historization]** 단계).

## 입력 매개 변수 {#input-parameters}

* 파일

   보낸 파일의 전체 이름입니다.

## 출력 매개 변수 {#output-parameters}

* 파일

   받은 파일의 전체 이름(다음 경우) **[!UICONTROL Use the file generated by the previous activity]** 옵션이 선택되어 있습니다.