---
title: Campaign 이메일 전송 인프라 업그레이드
description: Campaign 이메일 전송 인프라 업그레이드
hide: true
hidefromtoc: true
exl-id: f01e38ad-490e-4389-af5e-87beef533eb0
source-git-commit: 784c74aaff23dbf1f35c6e8153f90610048e1c07
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 1%

---

# Campaign 이메일 전송 인프라 업그레이드 {#migrate-infra-to-aws}

## 어떤 기능이 업그레이드됩니까?{#aws-changes}

최고의 사용자 경험을 제공하기 위한 지속적인 노력의 일환으로 이메일 게재 서비스를 업그레이드하고 있습니다.

## 영향을 받습니까?{#aws-impact}

이 변경 사항은 다음 사항에 영향을 줍니다.

* Adobe Campaign Classic Managed Services 고객
* Adobe Campaign Managed Cloud Services 고객
* Adobe Campaign Standard 온디맨드 고객

## 이 업그레이드는 언제 수행됩니까?{#aws-timeline}

개발 및 스테이징 환경 업그레이드가 **2023년 10월**&#x200B;에 시작되었습니다.

프로덕션 환경 업그레이드는 **2024년 1월**&#x200B;에 시작되었습니다.

## 기대 사항{#impact}

* 각 업그레이드 웨이브의 길이는 영향을 받는 Campaign 인스턴스의 수에 따라 달라집니다. 프로덕션 업그레이드 웨이브가 예약되면 알림에 예상 기간이 포함됩니다.

* 스테이징 및 프로덕션 환경 모두에서 Campaign 인스턴스는 업그레이드 기간 동안 메일을 보낼 수 없습니다. 다른 Campaign 기능은 영향을 받지 않습니다.

## 자주 묻는 질문 {#aws-faq}

* **이 업그레이드가 필수입니까?**

  예. Campaign 고객은 이메일 전송 기능을 사용하려면 이메일 전송 인프라를 사용해야 합니다.

* **이 업그레이드의 대상이 되는 고객은 무엇입니까?**

  위에서 참조한 모든 Campaign 고객의 환경이 업그레이드됩니다.

* **예상되는 가동 중지 시간은 무엇입니까?**

  각 업그레이드 웨이브의 길이는 영향을 받는 Campaign 인스턴스의 수에 따라 달라질 수 있습니다. 프로덕션 업그레이드 웨이브가 예약되면 알림에 예상 기간이 포함됩니다.

* **업그레이드를 위해 고객이 수행해야 하는 작업이 있습니까?**

  별도의 작업이 필요하지 않습니다. Adobe에서 자동으로 실행되는 업그레이드 프로세스를 관리합니다.

* **고객에게 필요한 테스트는 무엇입니까?**

  이 업그레이드 이벤트와 관련하여 고객이 어떤 테스트도 예상치 않습니다. 문제가 발생하는 경우 [Adobe 고객 지원 센터](https://experienceleague.adobe.com/ko?support-solution=Campaign#support){target="_blank"}에 문의하십시오.


* **예약된 보안 업그레이드 슬롯에 대한 날짜/시간 변경을 요청할 수 있습니까?**

  아니요. 기존 일정에 대해 요청된 수정 사항을 수용할 수 없습니다. 다른 고객에 대해 할당된 업그레이드 이벤트가 중단될 수 있기 때문입니다.

기타 문의 사항은 [Adobe 고객 지원 센터](https://experienceleague.adobe.com/ko?support-solution=Campaign#support){target="_blank"}에 문의하십시오.
