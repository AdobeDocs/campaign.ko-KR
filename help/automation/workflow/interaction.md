---
product: campaign
title: 인터랙션
description: 인터랙션
feature: Workflows, Interaction
role: User, Admin
version: Campaign v8, Campaign Classic v7
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 3%

---


# 인터랙션{#interaction}

아래에 설명된 워크플로는 기본적으로 **오퍼 엔진(상호 작용)** 추가 기능으로 설치됩니다.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블</strong><br /> </td> 
   <td> <strong>내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">전체 집계 계산(propositionrcp 큐브)</span> <br /> </td> 
   <td> <span class="uicontrol">agg_nmspropositionrcp_full</span> <br /> </td> 
   <td> 이 워크플로우는 <strong>오퍼 제안</strong> 큐브에 대한 <strong>전체</strong> 집계를 업데이트합니다. 기본적으로 매일 오전 6시에 트리거됩니다. 이 집계는 채널, 게재, 마케팅 오퍼 및 날짜 차원을 캡처합니다.<br /> <strong>오퍼 제안</strong> 큐브를 사용하여 오퍼를 기반으로 보고서를 생성합니다.<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">MessageCenter 전체 집계 계산</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> 이 워크플로는 <strong>메시지 센터</strong> 큐브에 대한 <strong>전체</strong> 집계를 업데이트합니다. 기본적으로 매일 오전 3시에 트리거됩니다. 이 집계는 채널, 날짜, 상태 및 이벤트 유형과 같은 차원을 캡처합니다.<br /> 그러면 <strong>메시지 센터</strong> 큐브를 사용하여 이벤트를 기반으로 보고서를 생성합니다. <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

[이 섹션](../../v8/reporting/gs-cubes.md)에서 큐브 및 합계에 대해 자세히 알아보세요.

