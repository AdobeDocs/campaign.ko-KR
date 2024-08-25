---
product: campaign
title: 기술 워크플로 모니터링
description: 기술 워크플로 모니터링
feature: Workflows
role: Admin
exl-id: 8524d916-8af7-4641-b047-9c348f1017fd
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 5%

---

# 기술 워크플로 모니터링 {#monitoring-technical-workflows}

기술 워크플로우는 모니터링해야 하며 실패할 경우 작업을 수행해야 합니다.

## 인스턴스 모니터링 대시보드 {#instance-monitoring-dashboard}

**[!UICONTROL Monitoring]** 탭을 통해 인스턴스 모니터링 대시보드에 액세스할 수 있습니다.

![](assets/monitoring_technical_workflows1.png)

시스템 표시기 및 코어 파일에서 빨간색으로 강조 표시된 표시기가 없는지 확인합니다. 이 경우 일부 고객은 다음과 같은 작업을 수행할 수 있습니다.

* 필요한 프로세스가 항상 실행 중인지 확인합니다.
* 너무 오래된 프로세스가 없는지 확인합니다.
* 다른 프로세스의 로그 파일에 경고 및 반복 오류가 포함되어 있지 않은지 확인하십시오.

## 기술 워크플로 {#technical-workflows}

기술 워크플로우는 **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]**&#x200B;에서 사용할 수 있습니다.

기술 워크플로우에 따라 아래 설명된 단계에 따라 모든 것이 예상대로 작동하는지 확인하십시오.

각 기술 워크플로우가 수행해야 하는 작업을 더 잘 이해하려면 이 [섹션](technical-workflows.md)을 참조하세요.

**[!UICONTROL Database Cleanup workflow ('cleanup')]**&#x200B;의 경우:

저널을 확인하여 경과 시간이 시간에 따라 비교적 일정하고 다른 워크플로우에 영향을 주지 않는지 확인하십시오.

**[!UICONTROL Tracking workflow ('tracking')]**&#x200B;의 경우:

추적 워크플로우가 예약된 대로(기본적으로 매 시간) 실행되고 저널이 반복적인 오류를 강조 표시하지 않는지 확인합니다. 자세한 정보는 이 [섹션](delivery.md)을 참조하십시오.

**[!UICONTROL Deliverability update ('deliverabilityUpdate')]**&#x200B;의 경우:

1. **[!UICONTROL Deliverability update]** 워크플로우가 매일 실행되고 성공적으로 완료되는지 확인하십시오.
1. 저널에서 규칙이 정기적으로 업데이트되고 있는지 확인합니다.

**[!UICONTROL Campaign process ('operationMgt', 'deliveryMgt', ...)]**&#x200B;의 경우:

1. **[!UICONTROL Campaign process]** 폴더 아래에 있는 모든 워크플로를 살펴봅니다. 자세한 정보는 이 [페이지](technical-workflows.md)를 참조하십시오.
1. 워크플로우가 예약대로 실행되는지 그리고 저널이 반복적인 오류를 강조 표시하지 않는지 확인하십시오.

## 워크플로우 감독 {#workflow-supervision}

**[!UICONTROL Workflow supervisors]** 그룹에는 실패를 알려야 하고 적시에 조치를 취할 수 있는 운영자가 포함되어야 합니다.

![](assets/monitoring_technical_workflows3.png)

문제가 발생하면 경고를 생성하고 올바른 그룹으로 보내야 합니다.

각 운영자에게 올바른 이메일 주소가 있는지 확인하십시오.

일별 데이터 가져오기와 같이 플랫폼이 작동하도록 하기 위해 실행해야 하는 모든 워크플로우는 &quot;프로덕션&quot;(확인란)으로 선언되고 굵게 표시되어야 합니다.

## 워크플로우 유지 관리 목록 {#workflow-maintenance-list}

모든 사용자 지정 기술 워크플로우는 다음을 포함하는 워크시트에 문서화해야 합니다.

* 워크플로우 이름 및 위치입니다.
* 목적.
* 예약 및 종속성.
* 모니터링 담당 운영자.
* 오류 발생 시 수행할 작업에 대한 지침

![](assets/monitoring_technical_workflows4.png)

## 모니터링 계획 및 자동화 {#planning-and-automation-of-monitoring}

워크플로우 모니터링을 계획하면 효율성이 향상됩니다. 일부 작업은 매일 수행되지만 다른 작업은 매주 또는 매월 수행할 수 있습니다.

되풀이에 의해 이름이 지정되고 실행 예약에 의해 정렬된 폴더에 워크플로우를 설정하면 모니터링 효율성이 향상됩니다.

모니터링 자동화를 통해 리소스 오버헤드가 줄어들고 작업이 적절한 빈도로 예약됩니다.

특정 작업이 실패하거나 중요한 테이블이 너무 커질 때마다 이메일을 보내는 모니터링 워크플로우를 빌드할 수 있습니다.

기능 영역 또는 시스템 전체에서 모든 워크플로우를 모니터링할 수 있는 보기를 만들 수 있습니다.

또한 Adobe Campaign 작업 또는 보고서 기능을 사용하여 필요할 때 언제든지 최신 문서를 작성할 수 있습니다.
