---
solution: Campaign
product: Adobe Campaign
title: 기본 수신자 테이블 변경
description: 사용자 지정 수신자 테이블을 사용하는 방법 알아보기
feature: 개요
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# 사용자 지정 수신자 테이블 사용{#gs-ac-custom-recipient}

Adobe Campaign에는 내장 프로필 테이블이 포함되어 있습니다.**nmsRecipient**. 이 표에는 미리 정의된 필드 및 표가 많이 있으며 쉽게 확장할 수 있습니다. [이 페이지](datamodel.md#ootb-profiles)에서 이 표에 대해 자세히 알아보십시오.

내장 표 확장 기능은 뛰어난 유연성을 제공하지만 사용하지 않는 일부 필드나 링크를 제거할 수는 없습니다. 따라서 데이터 모델이 Campaign 기본 제공 받는 사람 테이블 구조와 크게 다르거나 프로필이 많은 경우 사용자 지정 수신자 테이블을 사용하는 것이 좋습니다.  다만, 이 방법을 구현할 때에는 특정한 예방책이 필요하다.

이 기능을 통해 Adobe Campaign은 외부 데이터베이스의 데이터를 처리할 수 있습니다.이 데이터는 배달용 프로필 세트로 사용됩니다. 이 프로세스를 구현하려면 다음과 같은 제한 사항이 포함됩니다.

* Campaign Cloud 데이터베이스에 대한 업데이트 스트림 없음:이 테이블의 데이터는 해당 테이블을 호스팅하는 데이터베이스 엔진을 통해 직접 업데이트할 수 있습니다.
* 기존 데이터베이스에서 작동하는 프로세스는 안정되어야 합니다.
* 비표준 구조와 함께 프로필 데이터베이스 사용:단일 인스턴스를 사용하여 다양한 구조의 다양한 테이블에 저장된 프로파일에 전달할 수 있습니다.

이 섹션에서는 Adobe Campaign의 기존 테이블을 매핑하기 위한 주요 포인트와 테이블을 기반으로 납품을 실행하는 데 적용할 구성 설정에 대해 설명합니다. 또한 최종 사용자를 위한 쿼리 인터페이스를 디자인하는 방법도 설명합니다.

>[!CAUTION]
>
>Adobe Campaign 맞춤화는 전문가 사용자에게만 제공됩니다. 입력 양식과 스키마 디자인에 대한 전문 지식이 필요합니다.

