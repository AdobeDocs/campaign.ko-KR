---
title: 게재 상태
description: 게재 대시보드에서 사용할 수 있는 상태에 대해 자세히 알아보기
feature: Monitoring, Deliverability
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 2%

---

# 게재 상태 {#delivery-statuses}

게재가 전송되면 게재 대시보드에 전송 성공 여부를 모니터링할 수 있는 상태가 표시됩니다. 가능한 상태는 아래 섹션에 자세히 설명되어 있습니다.

![](assets/delivery-status.png)

발생할 수 있는 다양한 게재 실패와 이를 해결하는 방법에 대한 자세한 내용은 [게재 실패 이해](delivery-failures.md)를 참조하십시오.

**관련 항목:**

* [이메일 전송 및 모니터링](send.md)
* [게재 실패 이해](delivery-failures.md)
* [게재 기능 시작](about-deliverability.md)

## 게재 상태 목록 {#list-delivery-statuses}

<table> 
 <thead> 
  <tr> 
   <th> 상태<br /> </th> 
   <th> 정의 및 솔루션<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 보냄<br /> </td> 
   <td> 게재가 메시지 공급자에게 올바르게 전송되었지만 받는 사람이 받을 필요는 없습니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 무시됨<br /> </td> 
   <td> 주소 오류로 인해 수신자에게 게재가 전송되지 않았습니다. 차단 목록, 격리, 제공되지 않거나 중복되었습니다. <br /> </td> 
  </tr> 
  <tr> 
   <td> 실패<br /> </td> 
   <td> 잘못된 주소 또는 전체 받은 편지함 등으로 인해 게재가 수신자에게 도달하지 못했습니다. 또한 스키마가 게재 매핑과 일치하지 않을 때 오류를 생성할 수 있으므로 개인화 블록의 문제와 연결할 수도 있습니다. <a href="delivery-failures.md" target="_blank">게재 오류 이해</a><br />를 참조하세요. </td> 
  </tr>
  <tr> 
   <td> 보류 중<br /> </td> 
   <td> 게재를 보낼 준비가 되었으며 게재 서버(MTA)에서 처리합니다. <a href="#pending-status" target="_blank">보류 중 상태</a>.<br /> 보기 </td> 
  </tr> 
  <tr> 
   <td> 적용할 수 없음<br /> </td> 
   <td> 서버(MTA)에서 게재를 고려했지만 처리되지 않았습니다.<br /> </td> 
  </tr>  
  <tr> 
   <td> 게재 취소됨<br /> </td> 
   <td> 연산자가 게재를 취소했습니다.<br /> </td> 
  </tr> 
  <tr> 
   <td> 서비스 공급자가 고려함<br /> </td> 
   <td> SMS 게재의 경우 SMS 서비스 공급자가 게재를 수신했습니다.<br /> 전자 메일 게재의 경우 메시지가 Campaign에서 MTA(메일 전송 에이전트)로 전달되었습니다.</td> 
  </tr> 
  <tr> 
   <td> 모바일에서 수신됨<br /> </td> 
   <td> 받는 사람이 모바일 장치에서 SMS를 받았습니다.<br /> </td> 
  </tr>
  <tr> 
   <td> 서비스 공급자<br />에게 전송됨 </td> 
   <td> 게재를 SMS 서비스 공급자에게 보냈지만 아직 받지 못했습니다.<br />
   </td> 
  </tr> 
  <tr> 
   <td> 준비됨<br /> </td> 
   <td> 모바일 채널과 같은 외부 커넥터에만 사용되는 중개 상태. '보류 중' 상태를 따르며 다음 상태를 결정하는 외부 커넥터입니다.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Adobe Campaign 이메일의 전달성을 최적화하는 방법에 대해 알아보려면 [이 섹션](about-deliverability.md)을 참조하세요. 전달성에 대한 자세한 내용은 [Adobe 전달성 모범 사례 안내서](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=ko)를 참조하세요.

## 보류 중인 상태 {#pending-status}

게재를 확인한 후 게재 상태가 **[!UICONTROL Pending]**&#x200B;임을 확인할 수 있습니다. 이 상태는 실행 프로세스가 일부 리소스의 가용성을 대기 중임을 의미합니다.

**[!UICONTROL Pending]** 상태는 먼저 게재가 예약되어 지정된 날짜까지 보류 중임을 의미할 수 있습니다. 자세한 내용은 [게재 예약 전송](configure-and-send.md#schedule-delivery-sending) 섹션을 참조하십시오.

게재를 보낼 수 없고 상태가 **[!UICONTROL Pending]**&#x200B;인 경우 다음 결과가 발생할 수 있습니다.

* **동시에 실행되는 캠페인이 너무 많음**

  동시 캠페인의 제한은 **[!UICONTROL NmsOperation_LimitConcurrency]** 옵션에 정의되어 있습니다. 기본값은 10입니다.

  필요한 경우 Managed Cloud Services 사용자는 Adobe과 협력하여 이 제한을 조정할 수 있습니다. 옵션에 대한 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options.html){target="_blank"}를 참조하세요.

* **리소스 가용성 문제**

  MTA(메시지 전송 에이전트)가 게재를 처리하기 전에 리소스를 사용할 수 있을 때까지 대기할 수 있습니다.

>[!NOTE]
>
>Campaign v8 Managed Cloud Services 사용자는 MTA 인프라를 Adobe에서 모니터링하고 관리합니다. 보류 중인 게재에 지속적인 문제가 발생하는 경우 Adobe 고객 지원 센터에 문의하십시오.

**관련 항목:**

* [이메일 전송 및 모니터링](send.md#email-monitoring)
* [게재 실패 이해](delivery-failures.md)
* [Campaign 환경 모니터링](../start/monitor.md#monitor-deliveries)

