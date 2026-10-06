---
product: campaign
title: 받은 편지함 렌더링 기술 워크플로우
description: 이 섹션에서는 받은 편지함 렌더링 패키지와 함께 설치되는 기술 워크플로우에 대해 설명합니다
feature: Workflows, Inbox Rendering
role: User, Admin
version: Campaign v8, Campaign Classic v7
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: 2317b1ea-6db4-58c7-851f-717a69c0f5c0
    internal-label: Inbox Rendering
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 3%
---

# 받은 편지함 렌더링(IR){#inbox-rendering}



아래에 설명된 워크플로는 기본적으로 **받은 편지함 렌더링(IR)** 모듈로 설치됩니다.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블</strong><br /> </td> 
   <td> <strong>내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>받은 편지함 렌더링에 대한 시드 네트워크 업데이트</strong><br /> </td> 
   <td> <span class="uicontrol">updateRenderingSeeds</span> <br /> </td> 
   <td> 이 워크플로는 받은 편지함 렌더링에 사용되는 전자 메일 주소를 업데이트하며 <strong>deliverability.neolane.net</strong>.<br />에 대해 HTTPS 포트가 열려 있는 경우에만 작동합니다. </td> 
  </tr> 
 </tbody> 
</table>

