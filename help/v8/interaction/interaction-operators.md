---
title: 운영자 프로필
description: 오퍼 관리 운영자 만들기
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 1%

---

# 운영자 프로필 {#operator-profiles}

두 가지 유형의 연산자가 캠페인 상호 작용을 사용할 수 있습니다. **오퍼 관리자** 및 **게재 관리자**. 각 페이지에는 특정 권한 및 제한 사항이 있습니다. 에서 Campaign 운영자 및 권한에 대해 자세히 알아보십시오 [이 페이지](../start/permissions.md).

* 다음 **[!UICONTROL Offer manager]** 오퍼를 만들고 유지 관리합니다.
* 다음 **[!UICONTROL Delivery manager]** 오퍼 승인 및 사용

## 오퍼 관리자 연산자 만들기{#offer-manager}

1. 연산자를 만듭니다.

   ![](../assets/do-not-localize/book.png) Campaign에서 연산자를 만드는 단계는 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. 로 이동합니다. **[!UICONTROL Groups and named rights]** 창 **[!UICONTROL Add]** 을(를) 선택하고 을(를) 선택합니다. **[!UICONTROL Offer manager]** 그룹에 속해 있어야 합니다.

오퍼 관리자에 할당된 권한을 사용하여 다음 작업을 수행할 수 있습니다.

* 수정 **[!UICONTROL Design]** 환경.
* 보기 **[!UICONTROL Live]** 환경.
* 관리 함수(사전 정의된 공간 및 필터)를 구성합니다.
* 카테고리를 만들고 변경합니다.
* 오퍼를 만듭니다.
* 오퍼 자격 을 구성합니다.
* 오퍼를 승인합니다.

워크플로우에서 오퍼를 사용하는 경우 오퍼를 **[!UICONTROL Administrator]** 또는 **[!UICONTROL Offer managers]** 작업 흐름을 실행할 연산자 그룹입니다.

>[!NOTE]
>
>**오퍼 관리자** 검토자가 지정되지 않았거나 오퍼 템플릿에서 검토자로 선언된 경우에만 오퍼를 승인할 수 있습니다.

## 게재 관리자 연산자 만들기 {#delivery-manager}

1. 연산자를 만듭니다.

   ![](../assets/do-not-localize/book.png) Campaign에서 연산자를 만드는 단계는 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. 로 이동합니다. **[!UICONTROL Groups and named rights]** 창 **[!UICONTROL Add]** 을(를) 선택하고 을(를) 선택합니다. **[!UICONTROL Delivery manager]** 그룹에 속해 있어야 합니다.

게재 관리자에게 할당된 권한을 통해 다음 작업을 수행할 수 있습니다.

* 표시 **[!UICONTROL Live]** 환경.
* 오퍼 카테고리를 표시하고 수정합니다.
* 검토자인 경우 오퍼를 승인합니다.

   >[!NOTE]
   >
   >**게재 관리자** 오퍼는 오퍼 구성에서 검토자로 선언된 경우에만 승인할 수 있습니다.

## 상호 작용 연산자별 권한 매트릭스 {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>오퍼 관리자(디자인 환경)</strong><br /> </td> 
   <td> <strong>오퍼 관리자(라이브 환경)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>트리 구조 수준</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 편집 중인 오퍼/라이브 오퍼<br /> </td> 
   <td> 읽기/쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 수신자 - 환경<br /> </td> 
   <td> 읽기/쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 관리<br /> </td> 
   <td> 읽기/쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> Spaces<br /> </td> 
   <td> 읽기/쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 사전 정의된 오퍼 필터<br /> </td> 
   <td> 읽기/쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 유형화<br /> </td> 
   <td> 읽기/쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 유형화 규칙<br /> </td> 
   <td> 읽기/쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 오퍼 카탈로그<br /> </td> 
   <td> 읽기/쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 오퍼 카테고리<br /> </td> 
   <td> 읽기/쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>배달 관리자(디자인 환경)</strong><br /> </td> 
   <td> <strong>게재 관리자(라이브 환경)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>트리 구조 수준</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 편집 중인 오퍼/라이브 오퍼<br /> </td> 
   <td> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 수신자 - 환경<br /> </td> 
   <td> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 관리<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Spaces<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 사전 정의된 오퍼 필터<br /> </td> 
   <td> 읽기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 유형화<br /> </td> 
   <td> 읽기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 유형화 규칙<br /> </td> 
   <td> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 오퍼 카탈로그<br /> </td> 
   <td> 읽기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 오퍼 카테고리<br /> </td> 
   <td> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
 </tbody> 
</table>
