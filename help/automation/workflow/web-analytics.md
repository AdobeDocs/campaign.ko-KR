---
product: campaign
title: 웹 분석
description: 웹 분석 패키지에 대해 자세히 알아보기
feature: Workflows, Analytics Integration
version: Campaign v8, Campaign Classic v7
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 3%

---


# 웹 분석{#web-analytics}



아래에 설명된 워크플로는 기본적으로 **웹 분석 커넥터** 모듈과 함께 설치됩니다.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블</strong><br /> </td> 
   <td> <strong>내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">지표 및 캠페인 특성 전송</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsSendMetrics</span> <br /> </td> 
   <td> 이 워크플로우를 사용하면 Adobe® Analytics 커넥터를 통해 Adobe Campaign에서 Adobe Experience Cloud Suite로 이메일 캠페인 지표를 보낼 수 있습니다. 관련 지표는 다음과 같습니다. <strong>전송됨</strong>(iSent), <strong>총 열람 수</strong>(iTotalRecipientOpen), <strong>클릭한 총 수신자 수</strong>(iTotalRecipientClick), <strong>오류</strong>(iError), <strong>옵트아웃</strong>(옵트아웃)(iOptOut).<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">전환된 연락처 식별</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsFindConverted</span> <br /> </td> 
   <td> 이 워크플로우는 리마케팅 캠페인 후 구매를 완료한 사이트 방문자를 색인화합니다. 이 워크플로우에서 복구한 데이터는 <span class="uicontrol">리마케팅 효율성 보고서</span>에서 액세스할 수 있습니다( 참조). <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">이벤트 제거</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsPurgeWebEvents</span> <br /> </td> 
   <td> 이 워크플로우를 사용하면 <span class="uicontrol">수명</span> 필드에 구성된 기간에 따라 데이터베이스 필드에서 모든 이벤트를 삭제할 수 있습니다. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">웹 이벤트 복구</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsGetWebEvents</span> <br /> </td> 
   <td> 매시간마다 이 워크플로우는 주어진 사이트에서 인터넷 사용자 비헤이비어에 대한 세그먼트를 다운로드하여 Adobe Campaign 데이터베이스에 넣고 리마케팅 워크플로우를 시작합니다. <br /> </td> 
  </tr> 
 </tbody> 
</table>

