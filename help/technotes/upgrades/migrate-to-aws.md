---
title: Amazon Web Services으로 Campaign 전송 인프라 마이그레이션(AWS)
description: Amazon Web Services으로 Campaign 전송 인프라 마이그레이션(AWS)
hide: true
hidefromtoc: true
source-git-commit: d0935df57d8a25fa023dd93e7923c2728d889577
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 5%

---


# Campaign에서 Amazon Web Services으로 인프라 마이그레이션 전송(AWS) {#migrate-infra-to-aws}

## 변경 사항{#aws-changes}

최고 품질의 이메일 전송 서비스를 제공하기 위한 지속적인 노력의 일환으로 Campaign 이메일 전송 인프라가 Adobe 호스팅 데이터 센터에서 Amazon Web Services(AWS)로 이전됩니다.

이러한 움직임은 고가용성과 최적의 처리량을 보장하며 고객의 요구 사항에 맞게 확장할 수 있는 능력을 보장합니다.

## 영향을 받습니까?{#aws-impact}

v8 고객, v7 호스팅, 하이브리드 또는 Managed Services Campaign 고객은 영향을 받습니다.

## 이러한 마이그레이션은 언제 발생합니까?{#aws-timeline}

개발 및 스테이징 환경 마이그레이션은 다음 위치에서 수행됩니다. **2023년 10월**.

프로덕션 환경 마이그레이션은 다음 일자에 시작되도록 예약되었습니다. **2024년 1월**. 더 자세한 내용은 날짜가 가까워지면 제공될 것입니다.

Campaign 고객은 마이그레이션 예약된 대로 추가 알림을 받게 됩니다. 마이그레이션 최소 7일 전에 알림이 전송됩니다.

## 어떤 영향이 있습니까?{#aws-impact}

이러한 움직임은 고객에게 투명합니다.

* 전송 IP 및 캠페인 빌드 버전은 이동 전과 동일하게 유지됩니다.

* 마이그레이션 기간 동안 Campaign 인스턴스에서 메일을 보낼 수 없습니다. 다른 캠페인 기능은 영향을 받지 않습니다.

* 유지 관리 기간 전에 배달 대기 중인 모든 메일은 다시 전송해야 합니다.

>[!NOTE]
>
>이 마이그레이션에 대한 질문이 있으면 Adobe 담당자에게 문의하거나 [Adobe 고객 지원 센터](https://helpx.adobe.com/kr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).
>


