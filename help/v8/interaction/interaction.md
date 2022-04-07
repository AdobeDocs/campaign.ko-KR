---
title: Campaign 상호 작용 - 오퍼 관리
description: Get started with Offer management
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 4da3e69a-6230-4c94-a6f1-4e8c01e854ba
source-git-commit: 8417b1b4b7370e2a2eed76e9f1ac395eccf0ac66
workflow-type: tm+mt
source-wordcount: '1608'
ht-degree: 1%

---

# 실시간 상호 작용 관리

Campaign에는 **상호 작용** 단일 또는 여러 개의 특정 오퍼를 제안하여 주어진 연락처에 대한 상호 작용 중에 실시간으로 응답할 수 있는 모듈입니다. 이러한 오퍼는 간단한 커뮤니케이션 메시지, 하나 또는 여러 제품 또는 서비스에 대한 특별 오퍼일 수 있습니다.

You can create an offer catalog which interfaces with your outbound channels (email, direct mail, SMS) to select the best offer to send to a contact in a given context. 수신자를 위한 최상의 오퍼 선택은 **자격 규칙**. 관련 오퍼 집합에서 오퍼의 선택은 우선순위 규칙을 사용하여 결정됩니다. 오퍼 프레젠테이션 규칙은 연락처의 내역을 고려하여 연락처가 동일한 오퍼를 여러 번 받지 않도록 합니다.

상호 작용을 통해 오퍼 카탈로그를 만들고 관리할 수 있고, 오퍼에 연결된 자격 규칙 및 애플리케이션 테마를 구성할 수 있습니다. 선택한 채널에 따라 다양한 렌더링 기능 덕분에 오퍼 콘텐츠를 개인화할 수 있습니다. 마지막으로 시뮬레이션 모듈을 사용하여 오퍼 프레젠테이션의 영향을 계산할 수 있습니다.

![](assets/interaction-cycle.png)

먼저, 고객과 회사 간에 통신 채널을 통해 접촉이 발생합니다. 웹 사이트(아웃바운드 상호 작용), 이메일, SMS, 푸시 알림(인바운드 상호 작용)일 수 있습니다. [자세히 알아보기](#interaction-types)

이 연락처는 오퍼 엔진에 대한 호출을 생성합니다. (1)

오퍼 엔진에 대한 호출이 발생하면 제안에 대한 오퍼 설정 수에 따라 오퍼 카탈로그에서 하나 또는 여러 오퍼가 선택됩니다. (2)

그런 다음 자격 규칙이 적용됩니다. 우수 오퍼는 고객의 자격 규칙, 오퍼 시작 및 종료 날짜, 프로필 데이터 및 실시간 행동을 기반으로 선택됩니다. (3)

제공된 오퍼의 중복을 방지하기 위해 프로필 제안 내역은 선택 후 업데이트됩니다. (4)

Finally, the best offer is proposed to the target. (5)

## 오퍼 시작

시작할 주요 단계는 아래에 나와 있습니다.

### 플랫폼 구성

시작하기 전, 캠페인으로 **관리자**&#x200B;를 채울 때는 디자인 환경에서 다음 작업을 수행해야 합니다.

1. 사용자 프로필을 만듭니다. [자세히 알아보기](interaction-operators.md)
1. (선택 사항) 각 타깃팅 차원에 대한 오퍼 환경을 만듭니다. [자세히 알아보기](interaction-env.md)
1. 각 환경에 대한 유형화 규칙을 만듭니다. [자세히 알아보기](interaction-offer.md#offer-presentation)
1. 각 환경에 대한 오퍼 공간을 만들고 렌더링 기능을 구성합니다. [추가 정보](interaction-offer-spaces.md)
식별된 모드의 단일 채널로 공간이 정의된 경우 이 스페이스의 고급 매개 변수를 지정해야 합니다.

   >[!NOTE]
   >
   >식별된 모드의 단일 채널로 공간이 정의된 경우 이 스페이스의 고급 매개 변수를 지정해야 합니다.

1. 하나 또는 여러 오퍼를 제공하고 업데이트할 인바운드 상호 작용에 대한 오퍼 엔진을 구성합니다.

   다양한 통합 모드는 [이 섹션](interaction-present-offers.md).

   >[!NOTE]
   >
   >인바운드 웹 채널에서 오퍼 공간을 만드는 경우 이 오퍼를 표시하도록 웹 사이트를 구성해야 합니다.

### 오퍼 카탈로그 만들기 및 게시 {#managing-the-offer-catalog-}

로서의 **오퍼 관리자** 다음을 수행해야 합니다.

1. 디자인 환경에서 오퍼 카테고리를 만듭니다. [자세히 알아보기](interaction-offer-catalog.md#creating-offer-categories)
1. 디자인 환경에서 오퍼를 만듭니다. [자세히 알아보기](interaction-offer.md)
1. 하나 또는 여러 공간에 오퍼를 승인하고 게시하여 게재 관리자의 라이브 환경에서 사용할 수 있도록 합니다. [자세히 알아보기](interaction-offer.md#approve-offers)

### 오퍼 카탈로그 사용 {#using-the-offer-catalog-}

로서의 **게재 관리자**  다음을 수행해야 합니다.

1. 캠페인 만들기.
1. 캠페인 또는 게재에서 오퍼를 참조합니다. [자세히 알아보기](interaction-send-offers.md)

## 용어집

시작하기 전에 오퍼별 용어 및 관련 지침을 살펴보십시오.

* **환경**: 오퍼 카탈로그 및 후크(오퍼 공간)를 포함하는 를 설정합니다. Create one environment by targeting dimension. 환경에는 두 가지 유형이 있습니다.

   * **Design environment**: environment in which offers are created and/or typology rules are defined (rules that will determine the offers to present or not present to a targeted person). 오퍼의 타겟팅할 개인 테이블과 모든 오퍼 제안을 저장하는 테이블도 이 테이블에 정의되어 있습니다. The **[!UICONTROL Design environment]** node contains offer space sub-folders, pre-defined filters, and offer categories. 에 대해 **[!UICONTROL Design environment]** 해당 읽기 전용이 한 개 있습니다 **[!UICONTROL Live environment]**, 동일함 **[!UICONTROL Design environment]**.
   * **라이브 환경**: 에 연결된 환경 **[!UICONTROL Design environment]**. 이 팩에는 을 통해 콘텐츠 및 자격 조건을 승인한 읽기 전용 오퍼가 포함되어 있습니다 **[!UICONTROL Design environment]**. 웹 사이트에 표시하거나 메시지에 삽입할 수 있습니다.

* **오퍼 공간**: 오퍼가 노출된 위치를 정의하는 폴더입니다. 공백을 정의할 때 다음을 수행할 수 있습니다.
   * 채널 선택
   * 단일 모드에서 사용할 수 있도록 선택합니다(기본적으로). 일괄 처리 모드에만 해당)
   * 렌더링 함수를 사용하여 오퍼의 컨텐츠를 작성합니다
   * 표시할 오퍼 지정

   공백은 채널과 오퍼 엔진 간의 인터페이스입니다.

   >[!CAUTION]
   >
   >오퍼 공간은 통신 채널이 아니며, 채널상의 특정 박람회 위치와 일치합니다. 예를 들어, 웹 사이트에 노출된 오퍼는 동일한 페이지에서 두 개의 공백을 포함할 수 있습니다. 이 경우 동일한 채널에 두 개의 공백이 있습니다.
   >
   >Spaces must be defined in the specifications and must not be modified during the project.

* **Offer catalog**: set of offers defined in Adobe Campaign that can be selected during an interaction. The catalog is organized hierarchically with each node corresponding to a category.
* **카테고리**: 자연, 자격 날짜 및 애플리케이션 테마를 기반으로 오퍼를 구성하는 환경의 오퍼 카탈로그에 연결된 폴더입니다. A category can contain sub-categories, which inherit all the characteristics of the parent category. 카테고리에 대해 자격 규칙을 정의하여 여러 오퍼에 대해 공유할 수 있습니다.
* **애플리케이션 테마**: 오퍼의 선택을 하나 또는 두 카테고리로 제한하여 인바운드 또는 아웃바운드 채널에 표시될 때 오퍼를 필터링할 수 있는 카테고리에 정의된 키워드입니다.

   >[!NOTE]
   >
   >하위 카테고리는 상위 카테고리에서 식별된 테마를 상속합니다.

* **자격 규칙**: 유효 기간, 대상 및 중량에 대해 환경, 카테고리 또는 오퍼에 적용되는 제한. 오퍼를 사용하면 오퍼가 타깃팅된 연락처와 일치하는지 확인할 수 있습니다.

   환경에서 자격 규칙에는 오퍼와 타깃팅할 사람에게 적용된 프레젠테이션 규칙이 포함됩니다.

   카테고리에서 자격 규칙을 사용하여 다음을 수행할 수 있습니다. 시간별 카테고리의 유효성을 제한하고, 응용 프로그램 테마를 정의하고, 타깃팅할 사람을 결정합니다. 그들은 또한 주어진 시간 동안 승수 가중치를 받을 수 있습니다. 이렇게 하면 다른 카테고리에서 오퍼에 대한 규칙을 공유할 수 있으므로 오퍼를 간편하게 관리할 수 있습니다.

   In the offers, eligibility rules let you limit the validity of offers in time and determine the people to target.

* **중재**: 환경에 표시할 오퍼 선택(적합한 오퍼). The arbitrage principle ranks offers by priority according to the criteria defined in the categories, offers, and context offers.
* **연락처**: 인바운드 상호 작용의 연락처. During engine call processing, the contact is associated to a targeting dimension. 연락처에는 두 가지 유형이 있습니다.

   * **[!UICONTROL Identified contact]** : 채널에서 자발적으로 식별된 연락처. 아웃바운드 상호 작용에서 연락처는 자동으로 식별됩니다.
   * **[!UICONTROL Anonymous contact]** : a contact that has not voluntarily subscribed through the channel but can be implicitly identified through a cookie. 이 용어는 들어오는 상호 작용에만 사용됩니다.

      >[!NOTE]
      >
      >Non-identified, anonymous contacts are attributed to the visitor targeting dimension.

* **Outbound interaction**: call to the Offer engine from a contact list (used for delivering emails, direct mail, etc.). The same rules and processes are applied to each contact. 이러한 유형의 상호 작용은 일반적으로 일괄 처리 모드에서 처리됩니다.
* **인바운드 상호 작용**: 채널에서 연락처의 작업으로 생성된 수신 호출에 따른 상호 작용 이러한 유형의 상호 작용은 일반적으로 단일 모드에서 처리됩니다.
* **일괄 처리 모드**: 배치 모드에서는 연락처 세트에 가장 적합한 오퍼를 선택할 수 있습니다. 자격/우선 순위 규칙은 집합의 모든 연락처에 적용됩니다. 이 모드는 일반적으로 아웃바운드 상호 작용에 적용됩니다.
* **단일 모드**: 한 번에 하나의 연락처가 처리됩니다. 이 모드는 일반적으로 인바운드 상호 작용 및 트랜잭션 메시지에 적용됩니다.
* **식별 모드**: 은 연락처의 상태를 나타냅니다.

   * **[!UICONTROL explicit]** : 연락처는 채널 인터페이스에 로그인되어 식별됩니다.
   * **[!UICONTROL implicit]** : 연락처는 쿠키(영구 또는 세션)로 식별됩니다. 익명 또는 식별된 연락처로 처리할 수 있습니다.
   * **[!UICONTROL anonymous]** : 연락처를 식별할 수 없습니다.

* **적합한 오퍼**: 오퍼는 대상에 일관되게 제공할 수 있는 업스트림으로 정의된 제한 사항을 충족합니다.
* **프레젠테이션 규칙**: 오퍼 환경에서 참조되는 유형화 규칙으로서, 제안 내역을 고려하여 일부 오퍼를 제외할 수 있습니다.
* **두께**: 오퍼의 관련성을 정확하게 계산하여 가장 관련성이 높은 오퍼를 선택할 수 있는 공식입니다. 가중치는 오퍼에 정의됩니다. 적용 가능한 오퍼는 가중치 순서를 줄일 때 고려됩니다.
* **렌더링 함수**: 오퍼에 정의된 속성을 기반으로 오퍼 표현을 구성하기 위해 오퍼 공간에 정의된 함수입니다. 다음과 같은 세 가지 렌더링 기능 모드가 있습니다. HTML, XML 및 텍스트
* **오퍼 제안**: 지정된 공간의 연락처에 하나 또는 여러 오퍼를 제공하는 것으로 구성된 작업 결과(예: 웹 사이트의 배너, 이메일 또는 SMS). 이 결과는 오퍼 제안 테이블에 저장됩니다. 하지만, 제안을 저장하는 것은 필수가 아니다.
* **시뮬레이션**: 오퍼를 실제로 보내기 전에 타겟팅된 수신자에 대한 오퍼 프레젠테이션을 테스트할 수 있는 모듈입니다.
* **미리 보기**: 폴더에 표시된 오퍼의 미리 보기. 오퍼 설정 창이나 연락처 프로필에서 액세스할 수 있습니다.
* **사전 정의된 필터**: 사전 정의된 필터링 규칙은 오퍼 매개 변수(예: 오퍼 코드)를 고려할 수 있습니다. 오퍼를 만든 후에 다시 사용할 수 있습니다.
* **오퍼 표시**: 오퍼를 표시하는 데 채널에서 사용하는 정보입니다. 오퍼 표시는 오퍼가 표시되거나 인터페이스에 직접 입력된 공간(예: HTML 블록)의 렌더링 함수에서 작성할 수 있습니다. 오퍼는 공백으로 표시될 수 있습니다.
* **전환 프로세스**: 연락처가 명시적으로 및/또는 암시적으로 식별되지 않은 경우 익명 환경으로 호출을 리디렉션할 책임이 있는 식별된 환경의 활성화된 프로세스입니다.
