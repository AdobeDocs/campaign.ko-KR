---
title: Adobe Campaign 기본 제공 보고서
description: 기본 제공 보고서
feature: Reporting
role: User
exl-id: b63e6905-3bd4-4de4-9e7e-7638e5fc1192
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '1111'
ht-degree: 2%

---

# Adobe Campaign 기본 제공 보고서{#ootb-reports}

이 페이지에서는 Adobe Campaign 기본 제공 보고서, 해당 콘텐츠 및 컨텍스트 목록을 제공합니다. Adobe Campaign은 클라이언트 콘솔 또는 인터넷 브라우저로 액세스할 수 있는 다양한 기본 제공 보고서를 제공합니다.

다음 유형의 보고서를 사용할 수 있습니다.

* 전체 플랫폼에 대한 보고서입니다. [자세히 알아보기](global-reports.md)
* 게재 보고서. [자세히 알아보기](delivery-reports.md)

Campaign 홈페이지, 전용 보고서 대시보드 또는 게재 목록에서 기본 제공 보고서에 액세스할 수 있습니다. 보고서가 UI에 표시되는 방식은 컨텍스트에 따라 다릅니다.

주요 보고서 목록은 홈페이지에서 사용할 수 있으며, 이를 통해 게재 데이터에 빠르게 액세스할 수 있습니다. 이 목록은 필요에 따라 변경할 수 있습니다. 또한 보고서에 자신의 보고서를 추가하는 방법을 배울 수 있습니다 **[!UICONTROL Reports]** 탭.

이러한 사용자 지정 구성에 대한 자세한 내용은 다음을 참조하십시오. [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/configuring-access-to-the-report.html).


## 기본 제공 보고서 액세스 {#access-ootb-reports}

Campaign 기본 제공 보고서에 액세스하려면:

1. 다음 항목 선택 **[!UICONTROL Reports]** Adobe Campaign 인터페이스 탭

   ![](assets/reporting-access-from-home.png)

1. 검색 필드를 사용하여 표시된 보고서를 필터링합니다.

1. 그런 다음 표시할 보고서를 클릭합니다.

   ![](assets/edit-a-report.png)

1. 다음을 클릭합니다. **[!UICONTROL Back]** 화면 상단의 링크를 클릭하면 보고서 목록으로 돌아갑니다.

   ![](assets/back-button.png)

캠페인 또는 게재와 관련된 보고서는 해당 대시보드를 통해 액세스할 수 있습니다.

![](assets/reporting-on-delivery.png)

그 원칙은 목록, 서비스, 오퍼 등에도 동일하다. 아래와 같이:

![](assets/reporting-on-offer.png)


## 게재 보고서 {#reports-on-deliveries}

Adobe Campaign에서 제공하는 기본 제공 보고서는 아래 표에서 확인할 수 있습니다.

이러한 보고서의 콘텐츠에 대한 자세한 내용은 [이 섹션](delivery-reports.md).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블 및 내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
   <td> <strong>스키마</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 사용자 활동(recipientActivity)<br /> </td> 
   <td> 기간별 열람, 클릭 및 거래 분류.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 게재 처리량(처리량)<br /> </td> 
   <td> 게재 처리량 차트(메시지/시간 및 Mbit/초).<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 실패 및 바운스(오류)<br /> </td> 
   <td> 원인 및 도메인별로 바운스 및 게재 불가<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 지표 추적(deliveryFeedback)<br /> </td> 
   <td> 수신자 행동을 추적하기 위한 주요 지표의 요약입니다.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 추적 표시기(mobileAppDeliveryFeedback)<br /> </td> 
   <td> 모바일 애플리케이션 게재 지표 추적.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 브라우저 (browserStatistics)<br /> </td> 
   <td> 메시지를 클릭한 수신자가 사용하는 브라우저에 대한 통계입니다.<br /> </td> 
   <td> xtk:none<br /> </td> 
  </tr> 
  <tr> 
   <td> 소셜 네트워크에 공유(deliveryForward)<br /> </td> 
   <td> 활동 및 메일 열기 통계 공유.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 핫 클릭(hoturl)<br /> </td> 
   <td> 메시지와 클릭률을 중첩하여 표시합니다.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 가설 보고서(deliveryHypothesis)<br /> </td> 
   <td> 게재 가설에 대한 측정 요약 정보를 표시합니다.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 게재 통계(statisticsPerDelivery)<br /> </td> 
   <td> 이메일 도메인당 통계(처리된 메시지, 전달된 메시지, 하드 바운스, 소프트 바운스, 클릭 수, 구독 취소).<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 활동 통계 공유(forwardActivities)<br /> </td> 
   <td> 기간별 공유 활동, 열기 및 구독 분석.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 추적 통계(trackingStatistics)<br /> </td> 
   <td> 거래 비율 보고서를 열고, 누르고, 엽니다.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 게재 요약(deliverySending)<br /> </td> 
   <td> 게재 지표 요약: 타겟, 제외 및 보낸 메시지.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 게재 요약(deliveryStatistics)<br /> </td> 
   <td> 선택한 게재에 대한 요약 테이블: 타겟, 제외 및 보낸 메시지.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 운영 체제(osStatistics)<br /> </td> 
   <td> 메시지를 클릭한 수신자가 사용하는 운영 체제에 대한 통계입니다.<br /> </td> 
   <td> xtk:none<br /> </td> 
  </tr> 
  <tr> 
   <td> 반응성 비율(deliveryFeedbackSocial)<br /> </td> 
   <td> 전달 반응성 속도 및 반응 분석.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> URL 및 클릭 처리량(topUrlDelivery)<br /> </td> 
   <td> 대부분의 반응형 URL 및 연관된 클릭 스트림입니다.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 캠페인에 대한 보고서 {#reports-on-campaigns}

캠페인에 대한 보고서는 **nms:operation** 테이블.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블 및 내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 사용자 활동(operationRecipientActivity)<br /> </td> 
   <td> 기간별 열기, 클릭 및 거래에 대한 분류는 Campaign에 따라 다릅니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 게재 처리량(operationThroughput)<br /> </td> 
   <td> 게재 처리량 차트는 Campaign에 따라 메일/시간 및 Mbit/s 단위로 다릅니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 캠페인 경비(budgetOperationExpenses)<br /> </td> 
   <td> 캠페인 라인 항목을 Campaign에 따라 자세히 표시합니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 실패 및 바운스 수(operationErrors)<br /> </td> 
   <td> 원인 및 도메인별 바운스 및 비게재 항목은 Campaign에 따라 다릅니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 비용 라인 탐색(budgetExplorerOperation)<br /> </td> 
   <td> 비용 라인에 대한 설명 분석은 MRM에 따라 다릅니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 지표 추적(operationFeedback)<br /> </td> 
   <td> 주요 추적 지표 개요: 열기, 클릭 수 및 트랜잭션. Campaign에 따라 다릅니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 소셜 네트워크에 공유(operationForward)<br /> </td> 
   <td> 활동 및 메일 열기 통계 공유는 캠페인에 따라 다릅니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 가설 보고서(operationHypothesis)<br /> </td> 
   <td> Campaign에 따라 캠페인 게재에 대한 가설 측정 요약을 표시합니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 활동 통계 공유(forwardActivityOpt)<br /> </td> 
   <td> 기간당 공유 활동, 열기 및 구독에 대한 분석은 Campaign에 따라 다릅니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 게재 요약(operationStatistics)<br /> </td> 
   <td> 캠페인 게재의 요약 차트(타겟, 제외 및 보낸 메시지).<br /> </td> 
  </tr> 
  <tr> 
   <td> URL 및 클릭 처리량(operationTopUrlDelivery)<br /> </td> 
   <td> 대부분의 반응형 URL 및 관련 클릭 스트림은 Campaign에 따라 다릅니다.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 서비스에 대한 보고서 {#reports-on-services}

서비스에 대한 보고서는 **nms:service** 테이블.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블 및 내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Fan 인수(socialAcquisitionsByWebapp)<br /> </td> 
   <td> 잠재 고객 확보를 가능하게 한 웹 애플리케이션은 무엇입니까? 소셜 마케팅 추가 기능에 따라 다릅니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 구독 분류(mobileAppDistribution)<br /> </td> 
   <td> 모바일 애플리케이션당 활성 구독 분류는 모바일 앱 채널 추가 기능에 따라 다릅니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 구독 추적(subscriptionsProgress)<br /> </td> 
   <td> 정보 서비스 구독의 발전<br /> </td> 
  </tr> 
  <tr> 
   <td> 반응성 속도(socialReactionRate)<br /> </td> 
   <td> 최신 게재의 반응성 비율은 얼마입니까? 소셜 마케팅 추가 기능에 따라 다릅니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 반응성 비율(mobileAppReactivityRate)<br /> </td> 
   <td> 최신 게재에 대한 반응성 비율은 모바일 앱 채널 추가 기능에 따라 다릅니다.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 예산 보고서 {#budget-reports}

Adobe Campaign에서 제공하는 기본 제공 보고서는 아래 표에서 확인할 수 있습니다.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블 및 내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
   <td> <strong>스키마</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 프로그램에 연결된 비용(budgetProgramCost)<br /> </td> 
   <td> 프로그램 비용 분류.<br /> </td> 
   <td> nms:program<br /> </td> 
  </tr> 
  <tr> 
   <td> 예산 진화(budgetEvolution)<br /> </td> 
   <td> 약정 수준별 예산 비용의 발전.<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> 예산의 누적 진화(budgetCumulativeEvolution)<br /> </td> 
   <td> 누적된 예산비용이 공동체로 분해되는 진화<br /> 연고 레벨. </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> 비용 라인 탐색(budgetExplorerBudget)<br /> </td> 
   <td> 비용 라인에 대한 설명 분석.<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> 비용 라인 탐색(budgetExplorer)<br /> </td> 
   <td> 비용 라인에 대한 설명 분석.<br /> </td> 
   <td> nms:costLine<br /> </td> 
  </tr> 
  <tr> 
   <td> 비용 라인 탐색(budgetExplorerPlan)<br /> </td> 
   <td> 비용 라인에 대한 설명 분석.<br /> </td> 
   <td> nms:plan<br /> </td> 
  </tr> 
  <tr> 
   <td> 비용 라인 탐색(budgetExplorerProgram)<br /> </td> 
   <td> 비용 라인에 대한 설명 분석.<br /> </td> 
   <td> nms:program<br /> </td> 
  </tr> 
  <tr> 
   <td> 예산 요약(예산)<br /> </td> 
   <td> 기본 비용, 경비 범주 및 예산에 대한 스냅샷.<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 시뮬레이션에 대한 보고서 {#reports-on-simulations}

시뮬레이션에 대한 보고서는 **nms:simulation** 테이블.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블 및 내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 시뮬레이션 제외 세부 정보(dlvSimuLossDetail)<br /> </td> 
   <td> 모든 제외 원인에 대한 자세한 표.<br /> </td> 
  </tr> 
  <tr> 
   <td> 등급별 오퍼 분류(offerSimulationRanking)<br /> </td> 
   <td> 시뮬레이션에서의 오퍼를 등급별로 분류합니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 시뮬레이션 요약(dlvSimuLossSummary)<br /> </td> 
   <td> 시뮬레이션 볼륨 및 제외 요약.<br /> </td> 
  </tr> 
  <tr> 
   <td> 중복 통계(dlvSimuOverlapping)<br /> </td> 
   <td> 게재 대상 중복 볼륨.<br /> </td> 
  </tr> 
  <tr> 
   <td> 시뮬레이션으로 인한 제외 요약(dlvSimuLossSimu)<br /> </td> 
   <td> 시뮬레이션으로 인한 제외 테이블.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 웹 애플리케이션에 대한 보고서 {#reports-on-web-applications}

웹 애플리케이션에 대한 보고서는 **nms:WebApp** 테이블.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블 및 내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 설명서(surveyDictionary)<br /> </td> 
   <td> 설문 조사 구조에 대한 설명은 설문 조사 관리자 추가 기능에 따라 다릅니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 기본(surveyProperties)<br /> </td> 
   <td> 설문 조사 속성<br /> </td> 
  </tr> 
  <tr> 
   <td> 응답 분류(surveyDistribution)<br /> </td> 
   <td> 질문에 대한 응답 분류.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 기타 ootb 보고서 {#other-ootb-reports}

다음 보고서도 기본으로 제공됩니다. 자세한 내용은 관련 기능에 대한 문서를 참조하십시오.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>레이블 및 내부 이름</strong><br /> </td> 
   <td> <strong>설명</strong><br /> </td> 
   <td> <strong>스키마</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 오퍼 분석(offerAnalysis)<br /> </td> 
   <td> 날짜 및 채널당 오퍼 분석 은 상호 작용 추가 기능에 따라 다릅니다.<br /> </td> 
   <td> nms:offer<br /> </td> 
  </tr> 
  <tr> 
   <td> 리마케팅 효율성(remarketingEffect)<br /> </td> 
   <td> 리마케팅 효율성 측정<br /> </td> 
   <td> nms:webEvent<br /> </td> 
  </tr> 
  <tr> 
   <td> 소셜 잠재 고객 확보 기록(socialVisitorStatistics)<br /> </td> 
   <td> twitter 및 Facebook 잠재 고객 확보 기록은 소셜 마케팅 추가 기능에 따라 다릅니다.<br /> </td> 
   <td> nms:visitor<br /> </td> 
  </tr> 
  <tr> 
   <td> 최근 제안 추적(recentPropositions)<br /> </td> 
   <td> 실시간 제안 추적<br /> </td> 
   <td> nms:propositionRcp<br /> </td> 
  </tr> 
 </tbody> 
</table>
