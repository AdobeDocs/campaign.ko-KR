---
title: Amazon Web Services으로 Campaign 전송 인프라 마이그레이션(AWS)
description: Amazon Web Services으로 Campaign 전송 인프라 마이그레이션(AWS)
hide: true
hidefromtoc: true
exl-id: 50279a2f-0296-43f5-8967-16cc6a0c88f6
source-git-commit: 3e95a56825a143a4457ab7ee242208d7daaeb414
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 0%

---

# Campaign에서 Amazon Web Services으로 인프라 마이그레이션 전송(AWS) {#migrate-infra-to-aws}

## 변경 사항{#aws-changes}

최고 품질의 이메일 전송 서비스를 제공하기 위한 지속적인 노력의 일환으로 Campaign 이메일 전송 인프라가 Adobe 호스팅 데이터 센터에서 Amazon Web Services(AWS)로 이전됩니다.

이러한 움직임은 고가용성과 최적의 처리량을 보장하며 고객의 요구 사항에 맞게 확장할 수 있는 능력을 보장합니다.

## 영향을 받습니까?{#aws-impact}

이 변경 사항은 다음 사항에 영향을 줍니다.

* Campaign Classic v7 호스팅 및 하이브리드 고객
* Campaign Managed Services 고객
* 모든 Campaign v8 고객
* Campaign Standard 고객

## 이러한 마이그레이션은 언제 발생합니까?{#aws-timeline}

개발 및 스테이징 환경 마이그레이션은 다음 위치에서 수행됩니다. **2023년 10월**.

프로덕션 환경 마이그레이션은 다음 일자에 시작되도록 예약되었습니다. **2024년 1월**. 더 자세한 내용은 날짜가 가까워지면 제공될 것입니다.

Campaign 고객은 마이그레이션 예약된 대로 추가 알림을 받게 됩니다. 스테이지 환경의 경우 마이그레이션 최소 7일 전에 알림이 전송되고, 프로덕션 환경의 경우 마이그레이션 최소 30일 전에 알림이 전송됩니다.

## 어떤 영향이 있습니까?{#impact}

이러한 움직임은 고객에게 투명합니다.

* 각 마이그레이션 웨이브의 길이는 영향을 받는 Campaign 인스턴스의 수에 따라 달라질 수 있습니다. 마이그레이션 웨이브가 예약되면 알림에 예상 기간이 포함됩니다.

* 마이그레이션 기간 동안 Campaign 인스턴스에서 메일을 보낼 수 없습니다. 다른 캠페인 기능은 영향을 받지 않습니다.


## FAQ(자주 묻는 질문) {#aws-faq}

* **필수 업그레이드인 이유는 무엇입니까?**

  Adobe은 기존 데이터 센터를 서비스 해제할 계획이며, 이 곳에서 실행 중인 Adobe Campaign 인스턴스를 새 참조 데이터 센터인 Amazon Web Services(AWS)로 전송해야 합니다.

  Adobe Managed Services 클라우드는 현대적이고 안전하며 최적화된 환경인 Amazon Web Services(AWS)에서 호스팅됩니다. [Amazon Web Services에 대해 자세히 알아보기](https://aws.amazon.com/application-hosting/benefits/){target="_blank"}.

* **이 마이그레이션의 대상이 되는 고객은 무엇입니까?**

  모든 Campaign v8 고객과 Campaign Classic v7 하이브리드, 호스팅 및 Campaign Managed Services의 환경이 마이그레이션됩니다. Campaign Standard 고객도 영향을 받습니다.

* **예상되는 다운타임은 무엇입니까?**

  마이그레이션은 30분~60분 정도 소요될 것으로 예상되지만, 각 마이그레이션 웨이브 길이는 영향을 받는 Campaign 인스턴스의 수에 따라 달라질 수 있습니다. 마이그레이션 웨이브가 예약되면 알림에 예상 기간이 포함됩니다.

* **마이그레이션을 위해 고객이 수행해야 하는 작업이 있습니까?**

  마이그레이션은 Adobe에 의해 자동으로 실행되므로 작업이 필요하지 않습니다.

* **고객이 실행해야 하는 유효성 검사는 무엇입니까?**

  이 마이그레이션에 특정 테스트가 필요하지 않습니다. 문제가 발생하는 경우 다음으로 문의하십시오. [Adobe 고객 지원 센터](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


* **예약된 보안 업그레이드 슬롯에 대한 날짜/시간 변경을 요청할 수 있습니까?**

  이는 필수 마이그레이션이므로 기존 일정에 대한 수정 사항을 수용할 수 없습니다.

기타 문의 사항은 다음으로 문의하십시오. [Adobe 고객 지원 센터](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.
