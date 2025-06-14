---
title: 이메일 미리 보기 및 테스트
description: 보내기 전에 게재의 유효성을 검사하는 방법 알아보기
feature: Personalization
role: User
level: Beginner
exl-id: 5b9fa90c-c23e-47a7-b2ca-de75da4da2ab
source-git-commit: 70af3bceee67082d6a1bb098e60fd2899dc74600
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 16%

---

# 이메일 미리 보기 및 테스트 {#preview-test}

메시지 콘텐츠가 정의되면 테스트 프로필을 사용하여 미리 보고 테스트할 수 있습니다. [개인 맞춤화된 콘텐츠](personalize.md)를 삽입한 경우 테스트 프로필 데이터를 사용하여 이 콘텐츠가 메시지에 어떻게 표시되는지 확인할 수 있습니다. 또한 메시지 콘텐츠나 개인화 설정에서 발생할 수 있는 오류를 탐지하려면 테스트 프로필로 증명을 보냅니다. 최신 콘텐츠의 유효성을 검사하려면 변경 사항이 있을 때마다 증명을 보내야 합니다.

## 콘텐츠 미리보기 {#preview-content}

증명을 보내기 전에 게재 창의 미리보기 섹션에서 메시지 콘텐츠를 확인하는 것이 좋습니다.

메시지 콘텐츠를 미리 보려면 아래 단계를 따르십시오.

1. 게재의 **미리 보기** 탭으로 이동합니다.
1. 개인화 데이터를 채울 프로필을 선택하려면 **[!UICONTROL Test personalization]** 단추를 클릭하십시오. 데이터베이스에서 특정 수신자를 선택하거나 시드 주소를 선택하거나 대상 모집단에서 프로필을 선택할 수 있습니다(이미 정의된 경우). 개인화하지 않고 콘텐츠를 확인할 수도 있습니다.

   ![](assets/test-personalization.png)

1. 메시지 렌더링을 확인할 수 있도록 미리 보기가 생성됩니다. 메시지 미리 보기에서 개인화된 요소는 선택한 테스트 프로필 데이터로 바뀝니다.

   ![](assets/test-personalization-with-a-recipient.png)

1. 다른 테스트 프로필을 선택하여 메시지의 각 변형에 대한 이메일 렌더링을 미리 봅니다.

## 교정쇄 보내기 {#send-proofs}

이메일 게재의 경우 증명을 전송하여 메시지 내용을 확인할 수 있습니다. 증명을 보내면 옵트아웃 링크, 미러 페이지, 기타 링크를 확인하고, 메시지의 유효성을 검사하고, 이미지가 표시되는지 확인하고, 발생할 수 있는 오류를 감지하는 등의 작업을 수행할 수 있습니다. 다른 디바이스에서 디자인과 렌더링을 확인할 수도 있습니다.

증명은 메시지를 주 대상자에게 보내기 전에 테스트하기 위해 사용할 수 있는 전용 메시지입니다. 증명의 수신자는 메시지의 렌더링, 내용, 개인화 설정, 구성 등 요소를 승인해야 합니다.

### 증명 수신자 {#proofs-recipients}

증명 타겟은 게재 템플릿에서 정의하거나 게재별로 정의할 수 있습니다. 두 경우 모두 **[!UICONTROL To]** 링크에서 대상 정의 화면으로 이동한 다음 **[!UICONTROL Target of the proofs]** 탭을 선택합니다.

![](assets/target-of-proofs.png)

**[!UICONTROL Targeting mode]** 드롭다운 목록에서 증명 대상 유형을 선택합니다.

* **[!UICONTROL Definition of a specific proof target]** 옵션을 사용하여 데이터베이스의 수신자를 증명 대상으로 선택합니다.
* **[!UICONTROL Substitution of the address]** 옵션을 사용하여 전자 메일 주소를 입력하고 대상 받는 사람 데이터를 사용하여 콘텐츠의 유효성을 검사합니다. 대체 주소는 수동으로 입력하거나 드롭다운 목록에서 선택할 수 있습니다. 연결된 열거형은 대체 주소(rcpAddress)입니다.
기본적으로 대체는 임의로 수행되지만 **[!UICONTROL Detail]** 아이콘을 통해 기본 대상에서 특정 받는 사람을 선택할 수 있습니다.

  ![](assets/target-of-proofs-substitution-details.png){width="800" align="left"}

  **[!UICONTROL Select a profile (must be included in the target)]** 옵션을 선택하고 받는 사람을 선택하십시오.

  ![](assets/target-of-proofs-substitution.png){width="800" align="left"}


* 시드 주소를 증명 대상으로 사용하려면 **[!UICONTROL Seed addresses]** 옵션을 사용하십시오. 이러한 주소는 파일에서 가져오거나 수동으로 입력할 수 있습니다.

  >[!NOTE]
  >
  >시드 주소는 기본 수신자 테이블(nms:recipient)에 속하지 않으며, 별도의 테이블에 생성됩니다. 새 데이터로 수신자 테이블을 확장하는 경우 동일한 데이터로 시드 주소 테이블을 확장해야 합니다.

  [이 섹션](../audiences/test-profiles.md)에서 시드 주소에 대해 자세히 알아보세요.

* 시드 주소와 특정 이메일 주소를 조합하려면 **[!UICONTROL Specific target and Seed addresses]** 옵션을 사용하십시오. 그런 다음 관련 구성이 두 개의 개별 하위 탭에서 정의됩니다.

### 교정쇄 보내기 {#proofs-send}

메시지 증명을 보내려면 아래 단계를 따르십시오.

1. 메시지 정의 화면에서 **[!UICONTROL Send a proof]** 단추를 클릭합니다.
1. **[!UICONTROL Send a proof]** 창에서 증명 수신자를 확인합니다.
1. 증명 메시지 준비를 시작하려면 **[!UICONTROL Analyze]**&#x200B;을(를) 클릭하십시오.

   ![](assets/send-proof-analyze.png){width="800" align="left"}

1. 게재 준비가 완료되면 **[!UICONTROL Confirm delivery]**&#x200B;을(를) 사용하여 증명 메시지를 보냅니다.

게재의 **[!UICONTROL Audit]** 탭으로 이동하여 증명 사본 게재를 확인하십시오.

메시지 콘텐츠를 수정할 때마다 증명을 보내는 것이 좋습니다.

>[!NOTE]
>
>보낸 증명에서 미러 페이지 링크가 활성화되지 않았습니다. 최종 메시지에서만 활성화됩니다.

### 증명 속성 {#proofs-properties}

증명 속성은 게재 속성 창의 **[!UICONTROL Advanced]** 탭에서 설정됩니다. **[!UICONTROL Proof properties...]** 링크로 이동하여 증명의 매개 변수와 레이블을 정의합니다. 다음을 유지하도록 선택할 수 있습니다.

* 증명 시 주소 복제
* 증명의 차단 목록에 추가된 주소
* 증명 시 격리된 주소

기본적으로 증명 메시지는 제목의 `Proof #N` 언급에 의해 식별됩니다. 여기서 `N`은(는) 증명 번호입니다. 이 숫자는 각 증명 게재 분석과 함께 증가합니다. 필요에 따라 `proof` 접두사를 변경할 수 있습니다.

![](assets/proof-parameters.png){width="800" align="left"}


## 사용 방법 비디오 {#video-proof}

이메일 게재에 대한 교정쇄를 보내고 확인하는 방법을 알아봅니다.

>[!VIDEO](https://video.tv.adobe.com/v/3447006?captions=kor)
