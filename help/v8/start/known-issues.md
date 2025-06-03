---
title: Campaign v8 알려진 문제
description: 최신 Campaign 릴리스의 알려진 문제
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
source-git-commit: 41e39e046ec77de8b5e657ba76645898ff1cd2d7
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 2%

---

# 알려진 문제{#known-issues}

이 페이지에는 **최신 Campaign v8 릴리스**&#x200B;에서 식별된 알려진 문제가 나열됩니다. 또한 Campaign v8에서 발생하는 제한 사항은 [이 페이지의 ](ac-guardrails.md)에 나열되어 있습니다.


>[!NOTE]
>
>Adobe은 자체 재량에 따라 이 알려진 문제 목록을 게시합니다. 고객 보고서 수, 심각도 및 해결 방법 가용성을 기반으로 합니다. 발생한 문제가 목록에 없으면 이 페이지의 게시 기준에 맞지 않을 수 있습니다.

## Campaign v8.3.8{#8.3-issues}

### 데이터 Source 활동 문제 변경 {#issue-2}

#### 설명{#issue-2-desc}

Campaign **Query** 및 **데이터 변경 Source** 활동을 사용하여 Snowflake 클라우드 데이터베이스에 데이터를 삽입할 때 데이터에 백슬래시 문자가 있으면 프로세스가 실패합니다. 소스 문자열이 이스케이프되지 않고 데이터가 Snowflake에서 올바르게 처리되지 않습니다.

이 문제는 백슬래시 문자가 문자열 끝에 있는 경우에만 발생합니다(예: `Barker\`).


#### 재생 단계{#issue-2-repro}

1. 클라이언트 콘솔에 연결하고 워크플로우를 만듭니다.
1. **쿼리** 활동을 추가하고 구성합니다.
1. 위에서 설명한 특성을 사용하여 데이터를 선택합니다.
1. **데이터 변경 Source** 활동을 추가하고 Snowflake 클라우드 데이터베이스를 선택하도록 구성합니다.
1. 워크플로우를 실행하고 워크플로우 로그를 확인하여 오류를 확인합니다.


#### 오류 메시지{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

#### 해결 방법{#issue-2-workaround}

해결 방법은 문자열 끝에 백슬래시 문자가 포함된 데이터를 제외하거나 소스 파일에서 제거하는 것입니다.


#### 내부 참조{#issue-2-ref}

참조: NEO-45549


### 데이터 로드(파일) 활동이 서버에 파일을 업로드하지 못했습니다. {#issue-3}

#### 설명{#issue-3-desc}

**데이터 로드(파일)** 활동을 사용하여 Campaign 서버에 파일을 업로드할 때 프로세스가 100%에서 중지되지만 종료되지 않습니다.

#### 재생 단계{#issue-3-repro}

1. 클라이언트 콘솔에 연결하고 워크플로우를 만듭니다.
1. **데이터 로드(파일)** 활동을 추가하고 구성합니다.
1. **서버에 업로드** 옵션을 선택하십시오.
1. 로컬 컴퓨터에서 파일을 선택하고
1. **업로드** 클릭


#### 오류 메시지{#issue-3-error}

이 프로세스는 절대 끝나지 않습니다.

#### 해결 방법{#issue-3-workaround}

해결 방법은 이전 클라이언트 콘솔을 사용하는 것입니다. 그런 다음 서버에 파일을 업로드할 수 있습니다.

Campaign 관리자는 [Adobe 소프트웨어 배포](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Aversion&amp;1_group.propertyvalues.operation=equals&amp;1_group.propertyvalues.0_values=target-version%3Acampaign%2F8&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&amp;orderby.sort=desc&amp;layout=list&amp;p.offset=0&amp;p.limit=4){target="_blank"}에서 Campaign v8.3.1 클라이언트 콘솔을 다운로드할 수 있습니다.

이 페이지](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=ko){target="_blank"}에서 Adobe 소프트웨어 배포 [에 액세스하는 방법을 알아보세요.

이 페이지에서 클라이언트 콘솔 [을(를) 업그레이드하는 방법](connect.md)

#### 내부 참조{#issue-3-ref}

참조: NEO-47269

