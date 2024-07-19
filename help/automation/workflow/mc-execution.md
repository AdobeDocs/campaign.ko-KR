---
product: campaign
title: 메시지 센터(실행)
description: 메시지 센터(실행)
feature: Workflows
role: User
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 2%

---


# 메시지 센터(실행){#message-center-execution}

아래에 자세히 설명된 워크플로는 기본적으로 **메시지 센터 - 실행** 추가 기능과 함께 설치됩니다.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블</strong><br /> </td> 
   <td> <strong>내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">이벤트 상태 업데이트</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> 이 워크플로우를 통해 이벤트에 상태를 할당할 수 있습니다. 이벤트 상태는 다음과 같습니다. <br /> 
    <ul> 
     <li> <p><strong>보류 중</strong>: 이벤트가 큐에 있습니다. 아직 연결된 메시지 템플릿이 없습니다.</p> </li> 
     <li> <p><strong>게재 보류 중</strong>: 이벤트가 큐에 있고 메시지 템플릿이 연결되어 있으며 현재 게재에서 처리 중입니다.</p> </li> 
     <li> <p><strong>전송됨</strong>: 이 상태는 게재 로그에서 복사됩니다. 게재가 전송되었음을 의미합니다.</p> </li> 
     <li> <p><strong>게재에서 무시됨</strong>: 이 상태는 게재 로그에서 복사됩니다. 게재가 무시되었음을 의미합니다.</p> </li> 
     <li> <p><strong>게재 오류</strong>: 이 상태는 게재 로그에서 복사됩니다. 게재가 실패했다는 뜻입니다.</p> </li> 
     <li> <p><strong>이벤트가 포함되지 않음</strong>: 이벤트를 메시지 템플릿에 연결하지 못했습니다. 이벤트는 재처리되지 않습니다.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">일괄 처리 이벤트 처리</span> <br /> </td> 
   <td> <span class="uicontrol">batchEventsProcessing</span> <br /> </td> 
   <td> 이 워크플로우를 사용하면 메시지 템플릿과 연결하기 전에 일괄 처리 이벤트를 대기열에 넣을 수 있습니다. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">실시간 이벤트 처리</span> <br /> </td> 
   <td> <span class="uicontrol">rtEventsProcessing</span> <br /> </td> 
   <td> 이 워크플로우를 사용하면 실시간 이벤트를 메시지 템플릿과 연결하기 전에 대기열에 넣을 수 있습니다. <br /> </td> 
  </tr> 
 </tbody> 
</table>

