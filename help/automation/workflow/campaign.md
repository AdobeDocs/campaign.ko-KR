---
product: campaign
title: 캠페인
description: 캠페인
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
topic-tags: technical-workflows
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 3%

---


# 캠페인{#campaign}

아래에 설명된 워크플로는 기본적으로 **Campaign** 모듈과 함께 설치됩니다.

>[!CAUTION]
>
>캠페인 프로세스를 캠페인 수준에서 실행하려면 이러한 워크플로우를 시작해야 합니다.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블</strong><br /> </td> 
   <td> <strong>내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">비용 계산</span> <br /> </td> 
   <td> <span class="uicontrol">budgetMgt</span> <br /> </td> 
   <td> 이 워크플로우에서는 예산, 계획, 프로그램, 캠페인, 게재 및 작업에 대한 경비 및 비용 라인의 계산을 시작합니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">재고: 주문 및 알림</span> <br /> </td> 
   <td> <span class="uicontrol">stockMgt</span> <br /> </td> 
   <td> 이 워크플로우에서는 주문 라인에서 재고 계산을 시작하고 경고 경고 임계값을 관리합니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">캠페인의 게재에 대한 작업</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryMgt</span> <br /> </td> 
   <td> 이 워크플로우는 승인된 게재를 트리거하고 외부 게재에 대한 서비스 공급자의 사후 처리를 시작합니다. 승인 알림과 미리 알림도 보냅니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">캠페인 작업</span> <br /> </td> 
   <td> <span class="uicontrol">operationMgt</span> <br /> </td> 
   <td> 이 워크플로우는 마케팅 캠페인(론치 타기팅, 파일 추출 등)에 대한 작업을 관리합니다. 반복 및 정기 캠페인과 관련된 워크플로우도 만듭니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 서비스 공급자의 <span class="uicontrol">작업</span> <br /> </td> 
   <td> <span class="uicontrol">supplierMgt</span> <br /> </td> 
   <td> 게재가 승인되면 이 워크플로우는 공급자 처리(라우터로의 이메일 전송 및 사후 처리)를 시작합니다. <br /> </td> 
  </tr> 
 </tbody> 
</table>

