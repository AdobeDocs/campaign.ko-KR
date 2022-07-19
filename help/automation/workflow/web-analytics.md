---
product: campaign
title: 웹 분석
description: 웹 분석 패키지에 대해 자세히 알아보기
feature: Workflows, Analytics Integration
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 3%

---


# 웹 분석{#web-analytics}



아래 자세히 설명된 워크플로우는 **웹 Analytics 커넥터** 기본적으로 모듈입니다. 이 모듈에 대한 자세한 내용은 이 를 참조하십시오.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블</strong><br /> </td> 
   <td> <strong>내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">지표 및 캠페인 속성 보내기</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsSendMetrics</span> <br /> </td> 
   <td> 이 워크플로우에서는 Adobe® Analytics 커넥터를 통해 Adobe Campaign에서 Adobe Experience Cloud Suite로 이메일 캠페인 표시기를 보낼 수 있습니다. 관련 지표는 다음과 같습니다. <strong>전송</strong> (iSent), <strong>총 열기 수</strong> (iTotalRecipientOpen), <strong>클릭한 총 수신자 수</strong> (iTotalRecipientClick), <strong>오류</strong> (iError), <strong>옵트아웃</strong> (옵트아웃) (iOptOut)<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">전환된 연락처 식별</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsFindConverted</span> <br /> </td> 
   <td> 이 워크플로우는 재마케팅 캠페인 후 구매를 마친 사이트 방문자를 인덱싱합니다. 이 워크플로우에서 복구한 데이터는 <span class="uicontrol">리마케팅 효율성 보고서</span> ( 이 참조). <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">이벤트 삭제</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsPurgeWebEvents</span> <br /> </td> 
   <td> 이 워크플로우에서는 <span class="uicontrol">수명</span> 필드. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">웹 이벤트 복구</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsGetWebEvents</span> <br /> </td> 
   <td> 매시간마다 이 워크플로우는 주어진 사이트의 인터넷 사용자 동작에 있는 세그먼트를 다운로드하고, Adobe Campaign 데이터베이스에 지정하고, 리마케팅 워크플로우를 시작합니다. <br /> </td> 
  </tr> 
 </tbody> 
</table>

