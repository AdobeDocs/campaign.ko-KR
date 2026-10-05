---
product: campaign
title: 중간 소싱으로 전송
description: 중간 소싱 워크플로우로 전송에 대해 자세히 알아보기
feature: Workflows
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
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 1%
---

# 중간 소싱으로 전송{#transfer-to-mid-sourcing}

아래에 설명된 워크플로는 기본적으로 **중간 소싱으로 전송** 모듈과 함께 설치됩니다.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블</strong><br /> </td> 
   <td> <strong>내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">중간 소싱(게재 카운터)</span> <br /> </td> 
   <td> <span class="uicontrol">defaultMidSourcingDlv</span> <br /> </td> 
   <td> <p>이 워크플로우는 중간 소싱 서버의 게재에 대한 카운트 정보를 수집합니다. 카운트 정보에는 전송된 게재 수 등과 같은 일반 게재 지표가 포함됩니다.</p> <p>열림 등의 추적 정보는 포함되지 않습니다.</p> <p>기본적으로 10분마다 트리거됩니다.</p> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">중간 소싱(게재 로그)</span> <br /> </td> 
   <td> <span class="uicontrol">defaultMidSourcingLog</span> <br /> </td> 
   <td> 이 워크플로우는 중간 소싱 서버에서 게재 로그를 수집합니다. 기본적으로 매 시간마다 트리거됩니다.<br /> </td> 
  </tr> 
 </tbody> 
</table>

