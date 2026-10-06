---
product: campaign
title: 캠페인
description: 캠페인
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
topic-tags: technical-workflows
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '157'
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

