---
product: campaign
title: 생일 이메일 보내기
description: 워크플로우로 생일 전자 메일을 보내는 방법 알아보기
feature: Workflows
exl-id: c3a80871-e045-454c-b1ca-8f484d2e14e1
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 2%

---

# 생일 이메일 보내기{#sending-a-birthday-email}

이 사용 사례에서는 생일 날짜의 수신자 목록에 반복 이메일을 전송하는 방법을 설명합니다.

이 사용 사례를 설정하기 위해 다음 타겟팅 워크플로우를 만들었습니다.

![](assets/birthday-workflow_usecase_1.png)

이(일별 실행) 워크플로우는 현재 날짜에 생일이 있는 모든 수신자를 선택합니다.

이렇게 하려면 캠페인을 만들고 [캠페인 워크플로우](campaign-workflows.md).

그런 다음 아래 자세한 단계를 따르십시오.

## 생일인 수신자 식별 {#identifying-recipients-whose-birthday-it-is}

구성 후 **[!UICONTROL Scheduler]** 활동은 매일 시작되도록 생년월일이 현재 날짜와 같은 모든 수신자를 식별합니다.

그렇게 하려면 다음 단계를 적용합니다.

1. 끌어서 놓기 **[!UICONTROL Query]** 활동을 워크플로우에 입력하고 두 번 클릭합니다.
1. 을(를) 클릭합니다. **쿼리 편집** 링크 및 선택 **[!UICONTROL Filtering conditions]**.

   ![](assets/s_ncs_user_create_exp_exple00.png)

1. 의 첫 번째 셀을 클릭합니다 **[!UICONTROL Expression]** 열 및 클릭 **[!UICONTROL Edit expression]** 표현식 편집기를 엽니다.

   ![](assets/s_ncs_user_create_exp_exple.png)

1. 클릭 **[!UICONTROL Advanced selection]** 을 눌러 필터링 모드를 선택합니다.

   ![](assets/s_ncs_user_create_exp_exple_a.png)

1. 선택 **[!UICONTROL Edit the formula using an expression]** 을(를) 클릭합니다. **[!UICONTROL Next]** 표현식 편집기를 표시합니다.
1. 함수 목록에서 **[!UICONTROL Day]**: **[!UICONTROL Date]** 노드 아래에 있어야 합니다. 이 함수는 매개 변수로 전달된 날짜에 해당하는 일을 나타내는 숫자를 반환합니다.

   ![](assets/s_ncs_user_create_exp_exple01.png)

1. 사용 가능한 필드 목록에서 두 번 클릭합니다 **[!UICONTROL Birth date]**. 그러면 편집기의 위쪽 섹션에 다음 수식이 표시됩니다.

   ```
   Day(@birthDate)
   ```

   **[!UICONTROL Finish]**&#x200B;을(를) 클릭하여 확인합니다.

1. 쿼리 편집기에서 의 첫 번째 셀에서 **[!UICONTROL Operator]** 열, 선택 **[!UICONTROL equal to]**.

   ![](assets/s_ncs_user_create_exp_exple02.png)

1. 그런 다음 두 번째 열(**[!UICONTROL Value]**). **[!UICONTROL Edit expression]** 표현식 편집기를 엽니다.
1. 함수 목록에서 **[!UICONTROL Day]**: **[!UICONTROL Date]** 노드 아래에 있어야 합니다.
1. 를 두 번 클릭합니다. **[!UICONTROL GetDate]** 함수를 사용하여 현재 날짜를 검색합니다.

   ![](assets/s_ncs_user_create_exp_exple04.png)

   편집기의 상단 섹션에는 다음 공식이 표시됩니다.

   ```
   Day(GetDate())
   ```

   **[!UICONTROL Finish]**&#x200B;을(를) 클릭하여 확인합니다.

1. 이 절차를 반복하여 현재 달에 해당하는 생년월일을 검색합니다. 이렇게 하려면 **[!UICONTROL Add]** 버튼 및 3-10단계를 반복하여 바꿉니다. **[!UICONTROL Day]** with **[!UICONTROL Month]**.

   전체 쿼리는 다음과 같습니다.

   ![](assets/s_ncs_user_create_exp_exple03.png)

결과 연결 **[!UICONTROL Query]** 활동을 **[!UICONTROL Email delivery]** 활동을 통해 생일에 모든 수신자 목록으로 이메일을 보낼 수 있습니다.

## 2월 29일에 출생한 수신자 포함(선택 사항) {#including-recipients-born-on-february-29th--optional-}

2월 29일에 출생한 모든 수신자를 포함하려는 경우, 이 사용 사례에서는 윤년이든 아니든 생일에 수신자 목록에 반복 이메일을 보내는 방법을 설명합니다.

이 사용 사례에 대한 기본 구현 단계는 다음과 같습니다.

* 수신자 선택
* 윤년인지 여부를 선택합니다
* 2월 29일에 출생한 수신자 선택

이 사용 사례를 설정하기 위해 다음 타겟팅 워크플로우를 만들었습니다.



올해 **윤년이 아닙니다** 워크플로우는 3월 1일에 실행되며, 어제(2월 29일) 생일이 되었을 모든 수신자를 선택하고 수신자 목록에 추가해야 합니다. 다른 경우에는 추가 작업이 필요하지 않습니다.

### 1단계: 수신자를 선택합니다 {#step-1--selecting-the-recipients}

구성 후 **[!UICONTROL Scheduler]** 활동이 시작되므로 워크플로우가 매일 시작될 수 있으며 기념일이 현재 날짜인 모든 수신자를 식별합니다.

>[!NOTE]
>
>금년이 윤년이면 2월 29일에 출생한 모든 수신자가 자동으로 포함됩니다.

![](assets/birthday-workflow_usecase_2.png)

생일이 현재 날짜에 해당하는 수신자 선택 [생일인 수신자 식별](#identifying-recipients-whose-birthday-it-is) 섹션을 참조하십시오.

### 2단계: 윤년인지 여부를 선택합니다 {#step-2--select-whether-or-not-it-is-a-leap-year}

다음 **[!UICONTROL Test]** 활동을 통해 윤년인지 여부 및 현재 날짜가 3월 1일인지 여부를 확인할 수 있습니다.

테스트가 확인되면(년은 윤년이 아니라 - 2월 29일이 없고 - 현재 날짜가 실제로 3월 1일) **[!UICONTROL True]** 전환이 활성화되고 2월 29일에 출생한 수신자는 3월 1일 게재에 추가됩니다. 그렇지 않으면 **[!UICONTROL False]** 전환이 활성화되고 현재 날짜에서 태어난 수신자만 게재를 받습니다.

아래 코드를 복사하여 **[!UICONTROL Initialization script]** 섹션 **[!UICONTROL Advanced]** 탭.

```
function isLeapYear(iYear)
{
    if(iYear/4 == Math.floor(iYear/4))
    {
        if(iYear/100 != Math.floor(iYear/100))
        {
            // Divisible by 4 only -> Leap Year
            return 1;
        }
        else
        {
            if(iYear/400 == Math.floor(iYear/400))
            {
                // Divisible by 4, 100 and 400 -> Leap year
                return 1;
            }
        }
    }
    // all others: no leap year
    return 0;
}

// Return today's date and time
var currentTime = new Date()
// returns the month (from 0 to 11)
var month = currentTime.getMonth() + 1
// returns the day of the month (from 1 to 31)
var day = currentTime.getDate()
// returns the year (four digits)
var year = currentTime.getFullYear()

// is current year a leap year?
vars.currentIsALeapYear = isLeapYear(year);

// is current date the first of march?
if(month == 3 && day == 1) {
  // today is 1st of march
vars.firstOfMarch = 1;
}
```

![](assets/birthday-workflow_usecase_3.png)

에 다음 조건을 추가합니다. **[!UICONTROL Conditional forks]** 섹션:

```
vars.currentIsALeapYear == 0 && vars.firstOfMarch == 1
```

![](assets/birthday-workflow_usecase_4.png)

### 3단계: 2월 29일에 출생한 수신자를 선택합니다. {#step-3--select-any-recipients-born-on-february-29th}

만들기 **[!UICONTROL Fork]** 활동 및 아웃바운드 전환 중 하나를 **[!UICONTROL Query]** 활동.

이 쿼리에서 생년월일이 2월 29일인 모든 수신자를 선택합니다.

![](assets/birthday-workflow_usecase_5.png)

결과를 와 결합 **[!UICONTROL Union]** 활동.

두 결과의 연결 **[!UICONTROL Test]** 활동은 다음과 같이 분기됩니다 **[!UICONTROL Email delivery]** 활동은 비윤년 2월 29일에 출생한 대상에게도 생일에 모든 수신자 목록으로 이메일을 보냅니다.

## 반복 게재 만들기 {#creating-a-recurring-delivery-in-a-targeting-workflow}

추가 **반복 게재** 활동을 전송할 생일 이메일 템플릿을 기반으로 합니다.

>[!CAUTION]
>
>워크플로우를 실행하려면 캠페인 패키지와 관련된 기술 워크플로우를 시작해야 합니다. 자세한 내용은 [기술 워크플로우 목록](technical-workflows.md) 섹션을 참조하십시오.
>
>캠페인에 대해 승인 단계를 활성화하면 이러한 단계를 확인한 후에만 게재가 전송됩니다. 자세한 내용은 섹션을 참조하십시오.

![](assets/birthday-workflow_usecase_1.png)
