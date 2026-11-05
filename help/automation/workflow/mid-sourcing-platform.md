---
product: campaign
title: 중간 소싱 플랫폼
description: 중간 소싱 플랫폼
feature: Workflows
role: User
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
source-git-commit: 8a7bf8408d15e0bd9e1c3e72f7846bf9a79c6885
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 1%
---

# 중간 소싱 플랫폼{#mid-sourcing-platform}



아래에 설명된 워크플로는 기본적으로 **중간 소싱 플랫폼** 모듈과 함께 설치됩니다.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블</strong><br /> </td> 
   <td> <strong>내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">게재 표시기</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryIndicators</span> <br /> </td> 
   <td> 이 워크플로우는 게재에 대한 게재 추적 지표를 업데이트합니다. 이 워크플로우는 기본적으로 매 시간마다 트리거됩니다.<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>중간 소싱 서버의 로그 보존 기간은 게재 유효 기간에 **indicatorsDuration** 값을 더한 기간보다 길어야 합니다. 그렇지 않으면 이전 로그가 삭제되면 게재 지표가 감소하며 낮은 값이 마케팅 인스턴스와 동기화됩니다. 예를 들어 유효 기간이 5일이고 **indicatorsDuration**&#x200B;이 30일인 경우 유지 기간을 36일 이상으로 설정하십시오.
