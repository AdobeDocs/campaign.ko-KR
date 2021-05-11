---
solution: Campaign
product: Adobe Campaign
title: 캠페인 상호 작용 연산자
description: 오퍼 관리 연산자 만들기
feature: 개요
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 4bc62dcf806abd71e8230ce209d9151a4188b62e
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 1%

---


# 연산자 프로필 {#operator-profiles}

두 유형의 연산자는 캠페인 상호 작용을 사용할 수 있습니다.**오퍼 관리자** 및 **배달 관리자**&#x200B;입니다. 각각의 권한은 특정한 권한과 제한을 가집니다. [이 페이지](../start/permissions.md)의 캠페인 연산자 및 권한에 대해 자세히 알아보십시오.

* **[!UICONTROL Offer manager]**&#x200B;은 오퍼를 만들고 유지 관리합니다.
* **[!UICONTROL Delivery manager]**&#x200B;이(가) 오퍼를 승인하고 사용합니다.

## 오퍼 관리자 연산자 만들기{#offer-manager}

1. 새 연산자를 만듭니다.

   :arrow_upper_right:Campaign에서 연산자를 만드는 단계는 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)에 자세히 설명되어 있습니다.

1. **[!UICONTROL Groups and named rights]** 창으로 이동하여 **[!UICONTROL Add]**&#x200B;을 클릭하고 **[!UICONTROL Offer manager]** 그룹을 선택합니다.

오퍼 관리자에 지정된 권한을 사용하여 사용자는 다음 작업을 수행할 수 있습니다.

* **[!UICONTROL Design]** 환경을 수정합니다.
* **[!UICONTROL Live]** 환경을 봅니다.
* 관리 함수(사전 정의된 공간 및 필터)를 구성합니다.
* 카테고리 만들기 및 변경.
* 오퍼를 만듭니다.
* 오퍼 자격 조건을 구성합니다.
* 오퍼를 승인합니다.

오퍼가 워크플로우에 사용되는 경우 워크플로우를 실행하려면 연산자를 **[!UICONTROL Administrator]** 또는 **[!UICONTROL Offer managers]** 연산자 그룹에 추가해야 합니다.

>[!NOTE]
>
>**오퍼 관리자**&#x200B;는 리뷰어가 지정되지 않았거나 오퍼가 기반이 되는 오퍼 템플릿에서 리뷰어로 선언된 경우에만 오퍼를 승인할 수 있습니다.

## 배달 관리자 연산자 {#delivery-manager} 만들기

1. 새 연산자를 만듭니다.

   :arrow_upper_right:Campaign에서 연산자를 만드는 단계는 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)에 자세히 설명되어 있습니다.

1. **[!UICONTROL Groups and named rights]** 창으로 이동하여 **[!UICONTROL Add]**&#x200B;을 클릭하고 **[!UICONTROL Delivery manager]** 그룹을 선택합니다.

배달 관리자에게 할당된 권한은 다음 작업을 수행할 수 있도록 하거나 활성화합니다.

* **[!UICONTROL Live]** 환경을 표시합니다.
* 오퍼 카테고리를 표시하고 수정합니다.
* s/가 해당 검토자 중 하나로 지정된 경우 오퍼를 승인합니다.

   >[!NOTE]
   >
   >**배달 관리자**&#x200B;는 오퍼 구성 중에 검토자로 선언된 경우에만 오퍼를 승인할 수 있습니다.

## 상호 작용 연산자 {#recap-of-rights-according-to-operator}당 사용 권한 행렬

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>오퍼 관리자(디자인 봉투)</strong><br /> </td> 
   <td> <strong>오퍼 관리자(Live Env)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>트리 구조 수준</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 편집 중인 오퍼/실시간 오퍼<br /> </td> 
   <td> 읽기 / 쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 수신자 - 환경<br /> </td> 
   <td> 읽기 / 쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 관리<br /> </td> 
   <td> 읽기 / 쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 공백<br /> </td> 
   <td> 읽기 / 쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 사전 정의된 오퍼 필터<br /> </td> 
   <td> 읽기 / 쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> Typedics<br /> </td> 
   <td> 읽기 / 쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 유형화 규칙<br /> </td> 
   <td> 읽기 / 쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 오퍼 카탈로그<br /> </td> 
   <td> 읽기 / 쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> 오퍼 카테고리<br /> </td> 
   <td> 읽기 / 쓰기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>배달 관리자(디자인 환경)</strong><br /> </td> 
   <td> <strong>배달 관리자(Live Env.)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>트리 구조 수준</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 편집 중인 오퍼/실시간 오퍼<br /> </td> 
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
   <td> 공백<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 사전 정의된 오퍼 필터<br /> </td> 
   <td> 읽기<br /> </td> 
   <td> 읽기<br /> </td> 
  </tr> 
  <tr> 
   <td> Typedics<br /> </td> 
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
