---
product: campaign
title: 포크
description: 포크 워크플로우 활동에 대해 자세히 알아보기
feature: Workflows
role: User
exl-id: 7b94776c-2478-4e12-82a6-c94be12e7e22
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 1%

---

# 포크{#fork}



**[!UICONTROL Fork]** 활동을 사용하여 여러 아웃바운드 전환을 만들고 동일한 워크플로우 내에서 독립적으로 여러 활동을 실행할 수 있습니다.

>[!IMPORTANT]
>
>**[!UICONTROL Fork]** 활동 후에 추가하는 아웃바운드 전환은 동시에 실행되지 않습니다. 이 동작은 워크플로우 성능에 영향을 줄 수 있습니다. 여러 활동을 독립적으로 실행해야 하는 경우 **[!UICONTROL Fork]** 활동을 사용하십시오. 필요한 경우 워크플로우의 후속 부분 전에 아웃바운드 활동에 가입할 수 있습니다.

**[!UICONTROL Fork]** 활동 및 관련 활동을 구성하려면 다음 단계를 수행합니다.

1. **[!UICONTROL Fork]** 활동을 열고 아웃바운드 전환의 이름과 레이블을 정의합니다.

   ![](assets/s_user_segmentation_fork.png)

1. 각 아웃바운드 전환을 열고 구성합니다.
1. 아웃바운드 전환에 참여하려면 AND-join 활동을 추가합니다(선택 사항). [자세히 알아보기](and-join.md).

   워크플로우의 후속 부분은 조인된 아웃바운드 전환이 완료될 때만 실행됩니다.

## 예: 세그먼테이션

이 예제에서는 서로 다른 전자 메일이 서로 다른 모집단 그룹으로 전송됩니다. 쿼리 다음에 **[!UICONTROL Fork]** 활동을 사용하여 두 가지 작업을 동시에 수행합니다.

* 쿼리 결과 저장
* 결과를 세그먼트화하여 여러 게재 보내기

  ![포크 활동은 두 쿼리의 교차를 따르며 목록 업데이트 활동 및 분할 활동 앞에 옵니다.](assets/wkf_fork_example.png)

워크플로우는 다음 활동으로 구성됩니다.

1. **[!UICONTROL Query]** 활동

   두 개의 인구 집단이 선정됩니다: 여성과 파리지앵이죠.

1. **[!UICONTROL Intersection]** 활동

   쿼리 결과의 교차, 즉 파리 여성이 선택됩니다.

1. **[!UICONTROL Fork]** 활동

   계산된 모집단은 저장되고 동시에 두 개의 그룹으로 분할됩니다.

   1. 18세에서 40세 사이의 파리의 여자
   1. 40세 이상의 파리 여성

1. **[!UICONTROL Delivery]** 활동

   각 모집단 그룹에 다른 전자 메일이 전송됩니다.

## 사용 사례: 생일 이메일 보내기

생일 받는 사람 목록으로 되풀이하는 이메일이 전송됩니다. **[!UICONTROL Fork]** 활동은 윤년에 2월 29일에 태어난 수신자를 포함하는 데 사용됩니다. 이 사용 사례에 대해 [자세히 알아보세요](send-a-birthday-email.md).

![포크 활동은 테스트 활동 뒤에 있으며 두 쿼리 활동 앞에 있습니다.](assets/birthday-workflow_usecase_1.png)

## 사용 사례: 워크플로우를 통해 콘텐츠 자동화


그런 다음 각 아웃바운드 전환을 구성한 다음 필요한 경우 [AND-join](and-join.md) 활동을 사용하여 함께 연결할 수 있습니다. 이렇게 하면 **[!UICONTROL Fork]** 활동의 아웃바운드 전환이 완료된 경우에만 나머지 워크플로우가 실행됩니다.

## 관련 항목

* [AND-결합 활동](and-join.md)
* [사용 사례: 생일 이메일](send-a-birthday-email.md)
