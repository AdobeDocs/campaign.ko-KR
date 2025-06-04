---
product: campaign
title: LINE 채널
description: LINE 채널
feature: Workflows, Line App
role: User
version: Campaign v8, Campaign Classic v7
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 2%

---


# LINE 채널{#line-channel}

아래에 설명된 워크플로는 기본적으로 **LINE 채널** 모듈과 함께 설치됩니다. 이 모듈에 대한 자세한 정보는 [이 페이지](../../v8/send/line.md)를 참조하세요.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블</strong><br /> </td> 
   <td> <strong>내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">LINE V2 액세스 토큰 업데이트</span> <br /> </td> 
   <td> <span class="uicontrol">updateLineV2AccessToken</span> <br /> </td> 
   <td> 이 워크플로는 액세스 토큰을 LINE V2.<br />로 새로 고칩니다. </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">차단된 LINE 사용자 삭제</span> <br /> </td> 
   <td> <span class="uicontrol">deleteBlockedLineUsersV2</span> <br /> </td> 
   <td> 이 워크플로우에서는 LINE V2 사용자가 180일 동안 LINE 공식 계정을 차단한 후 해당 사용자의 데이터를 삭제합니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">MID에서 LineUserID로 마이그레이션</span> <br /> </td> 
   <td> <span class="uicontrol">MIDToUserIDMigration</span> <br /> </td> 
   <td> 이 워크플로우는 LINE V1에서 LINE V2로 마이그레이션할 LINE V2 사용자 ID를 생성합니다.<br /> </td> 
  </tr> 
 </tbody> 
</table>

