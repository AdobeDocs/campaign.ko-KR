---
product: campaign
title: 메시지 센터(제어)
description: 메시지 센터(제어)
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 1%

---


# 메시지 센터(제어){#message-center-control}

아래에 자세히 설명된 워크플로우는 매시간 실행되도록 예약되어 있습니다. 기본적으로 **메시지 센터 - 컨트롤** 모듈과 함께 설치됩니다.


<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블</strong><br /> </td> 
   <td> <strong>내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 메시지 센터 &lt;external_account_name&gt;<br /> </td> 
   <td> mcSynch_&lt;external_account_name&gt;<br /> </td> 
   <td> 이 워크플로:<br /> 
    <ul> 
     <li> <p>작업에서 처리된 이벤트 목록을 복구합니다.</p> </li> 
     <li> <p>게재 메시지 자격을 복구하려면 NmsBroadLogMsg 테이블과 동기화합니다.</p> </li> 
     <li> <p>nmsBroadLogMsg 테이블과의 동기화가 완료되는 즉시 이벤트 게재 로그를 복구합니다.</p> </li> 
     <li> <p>는 게재 URL에 대한 추적을 복구하기 위해 NmsTrackingUrl 테이블과 동기화합니다.</p> </li> 
     <li> <p>nmsTrackingUrl 테이블과의 동기화가 완료되는 즉시 이벤트 추적 URL을 복구합니다.</p> </li> 
     <li> <p>게재를 보낸 후 3시간마다 격리된 모든 이메일 주소를 복구할 수 있습니다.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

