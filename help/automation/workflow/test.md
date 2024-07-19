---
product: campaign
title: 테스트
description: 테스트 워크플로우 활동에 대해 자세히 알아보기
feature: Workflows
exl-id: 0d4d13f6-7128-44d3-ad5c-4ed02257ee64
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 1%

---

# 테스트{#test}



**Test** 형식 활동은 연결된 조건을 충족하는 첫 번째 전환을 활성화합니다. 충족된 조건이 없고 **[!UICONTROL Use the default fork]** 옵션이 활성화된 경우 기본 전환이 활성화됩니다.

조건은 &#39;true&#39; 또는 &#39;false&#39;로 평가해야 하는 JavaScript 표현식입니다. 식을 입력하려면 조건 이름 오른쪽에 있는 아이콘을 클릭한 다음 **[!UICONTROL Edit...]**&#x200B;을(를) 선택합니다.

![](assets/edit_test.png)

워크플로 JavaScript을 통해 액세스할 수 있는 응용 프로그램 서버의 모든 추가 JavaScript 함수 및 SOAP 메서드에 대한 자세한 내용은 [JSAPI 설명서](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=ko){target="_blank"}를 참조하십시오.

이 편집기에서 직접 변수를 삽입할 수도 있습니다. 변수를 사용하여 작업하는 방법에 대한 자세한 내용은 [이 섹션](javascript-scripts-and-templates.md#variables)을 참조하세요.

활동 속성 편집 창에서 조건을 추가, 삭제 또는 정렬할 수 있지만 전환에서 수정할 수도 있습니다.

계산의 결과를 다른 조건에서 재사용하려면 활동의 초기화 스크립트에서 계산하는 것이 가능합니다. 결과는 조건 스크립트(task.vars.xxx)에서 액세스할 수 있도록 작업의 변수에 저장해야 합니다.
