---
title: 워크플로 제어
description: API를 사용하여 워크플로우를 제어하는 방법을 알아봅니다.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: 79eacc31-d5a2-4e13-aa0b-744d7ab7004f
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 11%

---

# 워크플로 제어 {#controlling-a-workflow}

워크플로 ID 및 필수 실행 명령이 포함된 POST 요청을 통해 REST API에서 직접 워크플로를 제어할 수 있습니다.

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Adobe Campaign에서 워크플로우 ID를 변경하면 API 요청이 더 이상 작동하지 않습니다.

워크플로를 제어하는 데 사용할 수 있는 네 가지 실행 명령은 다음과 같습니다.

* 시작
* 일시 정지
* 재개
* 정지

실행 명령에 대한 자세한 내용은 [Campaign 설명서](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html)를 참조하세요.

<br/>

***샘플 요청***

* 워크플로우를 시작합니다.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"start"}'
  ```

  <!-- + réponse -->

* 워크플로우를 중지합니다.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"stop"}'
  ```

  <!-- + réponse -->
