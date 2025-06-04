---
product: campaign
title: 대기
description: 대기 워크플로우 활동에 대해 자세히 알아보기
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: a9bcb214-5c87-4b26-804a-22b868905022
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 1%

---

# 대기{#wait}



**대기** 활동은 몇 초에서 몇 개월 사이의 시간 지연 후에 전환을 활성화합니다. 대기 작업은 다른 작업의 실행을 차단하지 않습니다. 워크플로우는 이 작업이 보류 중인 동안 작업을 동시에 실행할 수 있습니다.

아래 예와 같이 편집기를 사용하여 레이블 및 대기 시간을 입력할 수 있습니다.

![](assets/edit_wait.png)

**[!UICONTROL Duration]** 필드에서 값을 원하는 단위로 표현할 수 있습니다(연산자의 지역 설정에 따라).

* 지역 설정이 지정되지 않은 경우: **s**(초), **m**(분), **h**(시간), **d**(일), **y**(년) 승인 시 값은 가장 읽기 쉬운 단위로 자동 변환됩니다.

  기본 단위는 일(**d**)입니다.

* 반면, 예를 들어 지역 설정이 &#39;Français&#39;로 설정된 경우: 초 동안 **s**, 분 동안 **mn**, 시간 동안 **h**, 일 동안 **j**, 개월 동안 **m**, 년 동안 **a**. 승인 시 값은 자동으로 가장 읽기 쉬운 단위로 변환됩니다. 위의 예에서 **90s**&#x200B;은(는) **1mn 30s**(으)로 변환되었습니다.

  기본 단위는 일(**d**)입니다.
