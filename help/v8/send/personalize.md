---
title: 콘텐츠 개인화
description: 메시지 콘텐츠를 개인화하는 방법 알아보기
feature: Personalization
role: User
level: Beginner
source-git-commit: 4885f15c71d2be27dc32a239fb22abc3a96503c7
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 5%

---

# 콘텐츠 개인화 {#personalize-content}

Adobe Campaign은 모든 마케팅 캠페인을 최대한 활용하기 위해 고객에게 수준에 맞는 맞춤형 콘텐츠를 제공하는 방법을 제공합니다. 프로필 데이터를 기반으로 개인화 기능을 통해 다양한 그룹 및 개인을 위한 사용자 지정 경험을 만들 수 있습니다. 보유한 데이터 및 정보를 활용하여 메시지를 특정 수신자에게 적용할 수 있습니다. 그것은 그들의 이름, 관심, 그들이 사는 곳, 그들이 산 것 등이 될 수 있습니다.

Adobe Campaign 개인화 간소화: 단일 수신자를 사용하여 각 수신자에 대해 사용자 지정된 다양한 유형의 콘텐츠를 표시할 수 있습니다 [이메일 템플릿](create-templates.md). 구매 확인 또는 장바구니 포기 이메일과 같은 트랜잭션 메시지에 단일 이메일 템플릿 내에 각 개인을 위한 제품 목록 정보를 포함합니다.


## 개인화 전략 {#personalization-strategy}

Campaign을 사용하여 다이내믹 컨텐츠를 만들고 개인화된 메시지를 보낼 수 있습니다. 개인화 기능을 결합하여 메시지를 개선하고 사용자 지정 사용자 경험을 만들 수 있습니다.

다음을 수행하여 메시지 콘텐츠를 개인화할 수 있습니다.

* 동적 삽입 **개인화 필드**

   개인화 필드는 메시지의 첫 번째 수준 개인화에 사용됩니다. 개인화 편집기에서 데이터베이스에서 사용할 수 있는 필드를 선택할 수 있습니다. 게재의 경우 수신자, 메시지 또는 게재와 관련된 필드를 선택할 수 있습니다. 이러한 개인화 속성은 제목 줄이나 메시지 본문에 삽입할 수 있습니다. [자세히 알아보기](personalization-fields.md)

   다음 구문은 콘텐츠에 수신자의 도시를 삽입합니다. &lt;%= recipient.location.city %>.

* 사전 정의된 삽입 **콘텐츠 블록**

   Campaign에는 게재에 삽입할 수 있는 특정 렌더링을 포함하는 개인화 블록 세트가 포함되어 있습니다. 예를 들어 메시지의 미러 페이지에 로고, 인사말 또는 링크를 추가할 수 있습니다. 콘텐츠 블록은 개인화 편집기의 전용 항목에서 사용할 수 있습니다. [자세히 알아보기](personalization-blocks.md)

* 만들기 **조건부 콘텐츠**

   예를 들어 수신자의 프로필을 기반으로 다이내믹 개인화를 추가하도록 조건부 콘텐츠를 구성합니다. 특정 조건이 true일 때 텍스트 블록 및/또는 이미지가 삽입됩니다. [자세히 알아보기](conditions.md)

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## 보호 및 권장 사항{#perso-guardrails}

### 개인화 시간 초과{#perso-timeout}

게재 보호를 개선하기 위해 개인화 단계에 대한 시간 초과 기간을 설정할 수 있습니다.

에서 **[!UICONTROL Delivery]** 의 탭 **[!UICONTROL Delivery properties]**&#x200B;를 채울 최대 값(초)을 선택합니다 **[!UICONTROL Maximum personalization run time]** 선택 사항입니다.

미리 보기 또는 전송 중에 개인화 단계가 이 필드에서 설정한 최대 시간을 초과하는 경우 오류 메시지와 함께 프로세스가 중단되고 게재가 실패합니다.

기본값은 5초입니다.

이 옵션을 0으로 설정하면 개인화 단계에 대한 시간 제한이 없습니다.


### 내부 변수{#internal-variables}

다음 변수는 개인화에 사용할 수 있지만 수정하면 안 되는 내부 변수입니다. **게재**, **메시지**, **dataSource**, **targetData**, **공급자**, **쿠폰**, **couponValue**, **제안**.


## 튜토리얼 비디오 {#personalization-video}

다양한 유형의 다이내믹 콘텐츠를 파악하고 개인화 블록 및 조건문을 만들어 게재에 적용하는 방법을 알아봅니다.


>[!VIDEO](https://video.tv.adobe.com/v/335734?quality=12)