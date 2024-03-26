---
title: Adobe Campaign을 사용하여 X(Twitter)에 메시지 게시
description: Adobe Campaign 소셜 마케팅 모듈을 사용하여 X(이전의 Twitter)에 메시지를 게시하고 팔로워에게 직접 메시지를 보내는 방법을 알아봅니다
role: User
level: Beginner, Intermediate
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: f463c5747b844544ba561a63e4cb0359c0c258c8
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 2%

---


# Adobe Campaign을 사용하여 X(Twitter)에 메시지 게시 {#post-tw-messages}

Adobe Campaign에는 **소셜 마케팅** X(이전에는 Twitter)를 통해 고객 및 잠재 고객과 상호 작용할 수 있는 모듈입니다.

통합이 구성되면 다음과 같은 작업을 수행할 수 있습니다.

* 팔로워에게 다이렉트 메시지 보내기
* X 계정에 게시
* 프로필 데이터를 복구하여 새 연락처를 수집하면 타겟팅 캠페인을 수행하고 가능한 경우 크로스 채널 전략을 구현할 수 있습니다. 이 작업을 수행하려면 사용자의 동의가 필요합니다.


X 계정을 Adobe Campaign과 통합하는 구성 단계는에 설명되어 있습니다 [이 페이지](../connect/ac-tw.md).

## X 게시물 만들기 및 게시 {#publish-on-tw}

아래 단계에 따라 X 계정에 메시지를 게시하십시오.

1. X 게재 만들기

   를 기반으로 새 게재 만들기 **[!UICONTROL Tweet (twitter)]** 게재 템플릿.

   ![](assets/tw-new-delivery.png)

1. 주 대상 선택

   게시물을 보낼 계정을 선택합니다.

   ![](assets/tw-define-target.png)

   1. **[!UICONTROL To]** 링크를 클릭합니다.
   1. **[!UICONTROL Add]** 버튼을 클릭합니다.
   1. **[!UICONTROL A Twitter account]**&#x200B;을(를) 선택합니다.
   1. 다음에서 **[!UICONTROL Folder]** 필드에서 X 계정이 포함된 서비스 폴더를 선택합니다. 그런 다음 트윗을 보낼 X 계정을 선택합니다.

1. 증명 대상 선택

   다음 **[!UICONTROL Target of the proofs]** 탭에서는 최종 게재 전에 테스트 게재에 사용할 X 계정을 정의할 수 있습니다.

   에 자세히 설명됨 [구성 단계](../connect/ac-tw.md#tw-test-account), 증명 전송 전용의 비공개 테스트 X 계정을 만들어야 합니다.

   >[!NOTE]
   >
   >모든 게재에 대해 동일한 X 테스트 계정을 사용하는 경우 **[!UICONTROL Tweet]** 게재 템플릿, 을 통해 액세스 **[!UICONTROL Resources > Templates > Delivery templates]** 노드. 그러면 각 새 게재에 대해 기본적으로 증명 대상이 입력됩니다.

1. 게시물의 콘텐츠 정의

   게시물의 내용을 **[!UICONTROL Content]** 탭.

   ![](assets/tw-delivery-content.png)

   >[!CAUTION]
   >
   >X에 게시할 때 제한 사항이 적용됩니다.
   >
   >* 메시지는 140자를 초과할 수 없습니다.
   >* HTML 형식이 지원되지 않습니다.
   >

1. 게시물 미리 보기

   찾아보기 **[!UICONTROL Preview]** 게시물 렌더링을 확인하는 탭입니다.

   ![](assets/tw-delivery-preview.png)

   1. 다음을 클릭합니다. **[!UICONTROL Preview]** 탭.
   1. 다음을 클릭합니다. **[!UICONTROL Test personalization]** 드롭다운 메뉴 및 선택 **[!UICONTROL Service]**.
   1. 다음에서 **[!UICONTROL Folder]** 필드에서 X 계정이 포함된 서비스 폴더를 선택합니다.

1. 증명 보내기

   트윗을 게시하기 전에 게시 증명을 보내 유효성을 검사하십시오. 그런 다음 비공개 X 테스트 페이지에서 게시의 정확한 렌더링을 가져올 수 있습니다.

1. 메시지 게시

   1. 콘텐츠가 승인되면 **[!UICONTROL Send]** 단추를 클릭합니다.
   1. 선택 **[!UICONTROL Deliver as soon as possible]** 을(를) 클릭하고 **[!UICONTROL Analyze]** 단추를 클릭합니다.
   1. 분석이 완료되면 결과를 확인합니다.
   1. 클릭 **[!UICONTROL Confirm delivery]**&#x200B;을 클릭한 다음 을 클릭합니다 **[!UICONTROL Yes]**.

## 팔로워에게 다이렉트 메시지 보내기 {#direct-tw-messages}

다음 **[!UICONTROL Synchronize Twitter accounts]** 기술 워크플로우에서는 직접 메시지를 보낼 수 있도록 X 팔로워 목록을 복구합니다. [자세히 알아보기](../connect/ac-tw.md#synchro-tw-accounts)

팔로워에게 직접 메시지를 보내려면 아래 단계를 따르십시오.

1. 다음을 기반으로 X 게재 만들기 **[!UICONTROL Tweet (Direct Message)]** 기본 제공 게재 템플릿.

1. 주 대상 선택

   ![](assets/tw-dm-define-target.png)

   1. 다음 항목 선택 **[!UICONTROL To]** 링크 및 **[!UICONTROL Add]** 단추를 클릭합니다.

   1. 타깃팅 유형 선택

      * 선택 **[!UICONTROL Twitter subscribers]** 모든 팔로워에게 다이렉트 메시지를 보냅니다.

      * 선택 **[!UICONTROL Filter conditions]** 쿼리를 정의하고 결과를 확인합니다. 에서 필터를 만드는 방법 알아보기 [이 섹션](../audiences/create-filters.md#advanced-filters).

1. 다음에서 증명 대상 선택 **[!UICONTROL Target of the proofs]** 탭: 이 계정은 다이렉트 메시지 증명을 받게 됩니다.

   에 자세히 설명됨 [구성 단계](../connect/ac-tw.md#tw-test-account), 증명 전송 전용의 비공개 테스트 X 계정을 만들어야 합니다.


   >[!NOTE]
   >
   >모든 DM 증명을 동일한 X 계정에 전송하려는 경우 **[!UICONTROL Tweet (Direct Message)]** 게재 템플릿, 을 통해 액세스 **[!UICONTROL Resources > Templates > Delivery templates]** 노드.

1. 에 메시지 내용 입력 **[!UICONTROL Content]** 탭.

   ![](assets/tw-dm-content.png)

   개인화 필드는 이메일 게재와 동일한 방식으로 사용할 수 있습니다(예: 메시지 본문에 팔로워의 이름을 추가). [이 섹션](../send/personalize.md)에서 자세히 알아보십시오.

1. 메시지 미리 보기

   찾아보기 **[!UICONTROL Preview]** 게시물 렌더링을 확인하는 탭입니다.

   ![](assets/tw-dm-preview.png)

   1. 다음을 클릭합니다. **[!UICONTROL Preview]** 탭.
   1. 다음을 클릭합니다. **[!UICONTROL Test personalization]** 드롭다운 메뉴 및 선택 **[!UICONTROL Visitor Subscription]**.
   1. 미리보기를 테스트할 X 계정을 선택합니다.

1. 증명 보내기

   메시지를 보내기 전에 다음 방법으로 유효성을 검사해야 합니다. [테스트 계정에 증명 보내기](../send/preview-and-proof.md): 그런 다음 개인 X 계정에서 메시지의 정확한 렌더링을 가져오고 콘텐츠 및 개인화를 확인할 수 있습니다.

1. 다이렉트 메시지 보내기

   1. 콘텐츠가 승인되면 **[!UICONTROL Send]** 단추를 클릭합니다.
   1. 선택 **[!UICONTROL Deliver as soon as possible]** 을(를) 클릭하고 **[!UICONTROL Analyze]** 단추를 클릭합니다.
   1. 분석이 완료되면 결과를 확인합니다.
   1. 클릭 **[!UICONTROL Confirm delivery]**&#x200B;을 클릭한 다음 을 클릭합니다 **[!UICONTROL Yes]**.

>[!CAUTION]
>
>하루에 250개 이상의 다이렉트 메시지를 보낼 수 없습니다. 이 임계값을 초과하지 않도록 하기 위해 를 웨이브로 제공할 수 있습니다. 자세한 내용은 다음을 참조하십시오. [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#sending-using-multiple-waves){target="_blank"}.


## 추적 데이터 액세스 {#tw-tracking}

기본 제공 **[!UICONTROL Tweet]** 게재 템플릿, 추적은 기본적으로 활성화됩니다.

추적 데이터는 게재 보고서 및 **[!UICONTROL Edit > Tracking]** 게재 및 서비스 탭.

추적 구성은 이메일 게재와 동일합니다. 다음에서 자세히 알아보기 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=ko){target="_blank"}.

