---
product: campaign
title: 메시지 센터(제어)
description: 메시지 센터(제어)
feature: Workflows
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 10%

---


# 메시지 센터(제어){#message-center-control}

아래에 자세히 설명된 워크플로우는 매시간마다 실행되도록 예약되어 있습니다. 와 함께 설치됩니다. **메시지 센터 - 제어** 기본적으로 모듈입니다.


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
   <td> 이 워크플로우는 다음과 같습니다.<br /> 
    <ul> 
     <li> <p>작업으로 처리된 이벤트 목록을 복구합니다.</p> </li> 
     <li> <p>배달 메시지 자격을 복구하기 위해 NmsBroadLogMsg 테이블과 동기화합니다.</p> </li> 
     <li> <p>NmsBroadLogMsg 테이블과의 동기화가 완료되는 즉시 이벤트 게재 로그를 복구합니다.</p> </li> 
     <li> <p>는 배달 URL에 대한 추적을 복구하기 위해 NmsTrackingUrl 테이블과 동기화합니다.</p> </li> 
     <li> <p>NmsTrackingUrl 테이블과의 동기화가 완료되는 즉시 이벤트 추적 URL을 복구합니다.</p> </li> 
     <li> <p>게재를 보낸 후 3시간마다 격리된 모든 이메일 주소를 복구할 수 있습니다.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

