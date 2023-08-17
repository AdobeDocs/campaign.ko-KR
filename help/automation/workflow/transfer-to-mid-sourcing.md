---
product: campaign
title: 중간 소싱으로 전송
description: 중간 소싱 워크플로우로 전송에 대해 자세히 알아보기
feature: Workflows
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 13%

---


# 중간 소싱으로 전송{#transfer-to-mid-sourcing}

아래에 설명된 워크플로우는 **중간 소싱으로 전송** 기본적으로 모듈입니다.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블</strong><br /> </td> 
   <td> <strong>내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">중간 소싱 (게재 카운터)</span> <br /> </td> 
   <td> <span class="uicontrol">defaultMidSourcesDlv</span> <br /> </td> 
   <td> <p>이 워크플로우는 중간 소싱 서버의 게재에 대한 카운트 정보를 수집합니다. 카운트 정보에는 전송된 게재 수 등과 같은 일반 게재 지표가 포함됩니다.</p> <p>열림 등의 추적 정보는 포함되지 않습니다.</p> <p>기본적으로 10분마다 트리거됩니다.</p> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">중간 소싱(게재 로그)</span> <br /> </td> 
   <td> <span class="uicontrol">defaultMid소싱로그</span> <br /> </td> 
   <td> 이 워크플로우는 중간 소싱 서버에서 게재 로그를 수집합니다. 기본적으로 매시간 트리거됩니다.<br /> </td> 
  </tr> 
 </tbody> 
</table>

