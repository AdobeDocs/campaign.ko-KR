---
product: campaign
title: LINE 채널
description: LINE 채널
feature: Workflows
role: User
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 27%

---


# LINE 채널{#line-channel}

아래에 설명된 워크플로우는 **LINE 채널** 기본적으로 모듈입니다. 이 모듈에 대한 자세한 내용은 [이 페이지](../../v8/send/line.md).

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
   <td> 이 워크플로우는 액세스 토큰을 LINE V2로 새로 고칩니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">차단된 LINE 사용자 삭제</span> <br /> </td> 
   <td> <span class="uicontrol">deleteBlockedLineUsersV2</span> <br /> </td> 
   <td> 이 워크플로우에서는 180일 동안 LINE 공식 계정을 차단한 후 LINE V2 사용자의 데이터를 삭제합니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">MID에서 LineUserID로 마이그레이션</span> <br /> </td> 
   <td> <span class="uicontrol">MIDToUserIDMigration</span> <br /> </td> 
   <td> 이 워크플로우는 LINE V1에서 LINE V2로 마이그레이션할 LINE V2 사용자의 ID를 생성합니다.<br /> </td> 
  </tr> 
 </tbody> 
</table>

