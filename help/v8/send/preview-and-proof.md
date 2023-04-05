---
title: 이메일 미리 보기 및 테스트
description: 보내기 전에 게재의 유효성을 검사하는 방법을 알아봅니다
feature: Personalization
role: User
level: Beginner
source-git-commit: a6d2cb72968fe489a73f92f00f6a50be8ed3e997
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 4%

---

# 이메일 미리 보기 및 테스트 {#preview-test}

메시지가 정의되면 테스트 프로필을 사용하여 미리 보고 테스트할 수 있습니다. 삽입한 경우 [개인화된 콘텐츠](personalize.md)테스트 프로필 데이터를 사용하여 이 콘텐츠가 메시지에 어떻게 표시되는지 확인할 수 있습니다. 또한 메시지 콘텐츠 또는 개인화 설정에서 가능한 오류를 탐지하려면 테스트 프로필에 증명을 보냅니다. 최신 콘텐츠를 확인하려면 변경 사항이 있을 때마다 증명을 보내야 합니다.

## 컨텐츠 미리 보기{#preview-content}

증명을 보내기 전에 가장 좋은 방법은 게재 창의 미리 보기 섹션에서 메시지 콘텐츠를 확인하는 것입니다.

메시지 콘텐츠를 미리 보려면 아래 단계를 수행하십시오.

1. 다음 위치로 이동합니다. **미리 보기** 게재의 탭입니다.
1. 을(를) 클릭합니다. **[!UICONTROL Test personalization]** 단추를 클릭하여 개인화 데이터를 채울 프로필을 선택합니다. 데이터베이스의 특정 수신자를 선택하거나, 시드 주소를 선택하거나, 대상 모집단에서 프로필을 선택할 수 있습니다(이미 정의된 경우). 개인화 없이 콘텐츠를 확인할 수도 있습니다.

   ![](assets/test-personalization.png)

1. 메시지 렌더링을 확인할 수 있도록 미리 보기가 생성됩니다. 메시지 미리 보기에서 개인화된 요소는 선택한 테스트 프로필 데이터로 대체됩니다.

   ![](assets/test-personalization-with-a-recipient.png)

1. 다른 테스트 프로필을 선택하여 메시지의 각 변형에 대한 이메일 렌더링을 미리 봅니다.

## 증명 보내기 {#send-proofs}

이메일 게재의 경우 증명을 전송하여 메시지 콘텐츠를 확인할 수 있습니다. 증명을 보내면 옵트아웃 링크, 미러 페이지 및 기타 모든 링크를 확인하고, 메시지를 확인하고, 이미지가 표시되는지 확인하고, 가능한 오류 감지 등을 수행할 수 있습니다. 다른 장치에서 디자인과 렌더링을 확인할 수도 있습니다.

증명은 메시지를 주요 대상자에게 보내기 전에 테스트하기 위한 특정 메시지입니다. 증명의 수신자는 메시지를 승인해야 합니다. 렌더링, 컨텐츠, 개인화 설정, 구성

### 증명 수신자 {#proofs-recipients}

증명 타겟은 게재 템플릿에서 정의하거나 게재에만 정의할 수 있습니다. 두 경우 모두, **[!UICONTROL To]** 링크를 클릭하고 **[!UICONTROL Target of the proofs]** 탭.

![](assets/target-of-proofs.png)

증명 대상 유형은 **[!UICONTROL Targeting mode]** 드롭다운 목록.

* 를 사용하십시오 **[!UICONTROL Definition of a specific proof target]** 데이터베이스에서 수신자를 증명 대상으로 선택하는 옵션.
* 를 사용하십시오 **[!UICONTROL Substitution of the address]** 이메일 주소를 입력하고 target 수신자 데이터를 사용하여 컨텐츠의 유효성을 검사하는 옵션. 대체 주소를 수동으로 입력하거나 드롭다운 목록에서 선택할 수 있습니다. 연결된 열거형은 대체 주소(rcpAddress)입니다.
기본적으로 대체는 임의로 수행되지만, 기본 대상에서 특정 수신자를  **[!UICONTROL Detail]** 아이콘.

   ![](assets/target-of-proofs-substitution-details.png){width="800" align="left"}

   을(를) 선택합니다 **[!UICONTROL Select a profile (must be included in the target)]** 옵션을 선택하고 수신자를 선택합니다.

   ![](assets/target-of-proofs-substitution.png){width="800" align="left"}


* 를 사용하십시오 **[!UICONTROL Seed addresses]**  시드 주소를 증명 대상으로 사용하는 옵션. 이러한 주소는 파일에서 가져오거나 수동으로 입력할 수 있습니다.

   >[!NOTE]
   >
   >시드 주소는 기본 수신자 테이블(nms:recipient)에 속하지 않고 별도의 테이블에 생성됩니다. 수신자 테이블을 새 데이터로 확장하는 경우, 시드 주소 테이블과 동일한 데이터를 확장해야 합니다.

   의 시드 주소에 대해 자세히 알아보기 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target="_blank"}.

* 를 사용하십시오 **[!UICONTROL Specific target and Seed addresses]** 시드 주소와 특정 이메일 주소를 결합하는 옵션. 그런 다음 관련 구성이 두 개의 개별 하위 탭에서 정의됩니다.

### 증명 보내기{#proofs-send}

메시지 증명을 보내려면 아래 단계를 따르십시오.

1. 메시지 정의 화면에서 **[!UICONTROL Send a proof]** 버튼을 클릭합니다.
1. 에서 **[!UICONTROL Send a proof]** 창에서 증명 수신자를 확인합니다.
1. 클릭 **[!UICONTROL Analyze]** 증명 메시지 준비를 시작하려면

   ![](assets/send-proof-analyze.png){width="800" align="left"}

1. 게재 준비가 완료되면 **[!UICONTROL Confirm delivery]** 증명 메시지 전송을 시작하려면 다음을 수행하십시오.

다음 위치로 이동합니다. **[!UICONTROL Audit]** 게재의 탭에서 증명 사본 전달을 확인합니다.

메시지 콘텐츠를 매번 수정한 후 증명을 보내는 것이 좋습니다.

>[!NOTE]
>
>전송된 증명에서 미러 페이지에 대한 링크가 활성 상태가 아닙니다. 최종 메시지에서만 활성화됩니다.

### 증명 속성{#proofs-properties}

증명 속성은 **[!UICONTROL Advanced]** 전달 속성 창의 탭입니다. 다음 위치로 이동합니다. **[!UICONTROL Proof properties...]** 링크를 클릭하여 증명 매개 변수와 레이블을 정의합니다. 다음을 유지할 수 있습니다.

* 증명의 중복 주소
* 증명의 차단 목록에 추가된 주소
* 증명의 격리된 주소

기본적으로 증명 메시지는 `Proof #N` 주제에서, `N` 는 증명 번호입니다. 이 번호는 증명 게재 분석마다 증가합니다. 을 변경할 수 있습니다 `proof` 접두사를 사용하십시오.

![](assets/proof-parameters.png){width="800" align="left"}


## 방법 비디오 {#video-proof}

이메일 게재에 대한 증명을 보내고 확인하는 방법을 알아봅니다.

>[!VIDEO](https://video.tv.adobe.com/v/333404)
