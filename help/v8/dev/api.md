---
title: Campaign API 시작
description: Campaign API 시작
feature: API
role: Developer
level: Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 14%

---

# [!DNL Campaign] API 시작 {#gs-ac-api}

[!DNL Adobe Campaign]에는 사용할 수 있는 Javascript 함수 집합이 포함되어 있습니다.

* 스크립트에서 - [!DNL Adobe Campaign] 워크플로에서
* API를 통해 - 외부 시스템에서

JavaScript API를 사용하여 Campaign 클라우드 데이터베이스에 쓰거나 데이터베이스에서 읽을 수 있습니다.

* 게재, 워크플로우, 구독 등 각 오브젝트에 대해 작업을 수행할 수 있는 비즈니스별 API입니다. 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html?lang=ko){target="_blank"}를 참조하세요.
* 데이터 모델 데이터 쿼리를 위한 일반 데이터 액세스 API입니다. 자세한 내용은 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html?lang=ko){target="_blank"}를 참조하세요.

[엔터프라이즈(FFDA) 배포](../architecture/enterprise-deployment.md)에서 Campaign은 두 개의 데이터베이스를 사용합니다. 하나는 사용자 인터페이스 실시간 메시지 보내기와 API를 통한 단일 쿼리 및 쓰기를 위한 로컬 데이터베이스이고, 다른 하나는 캠페인 실행, 보고, 데이터 수집, 쿼리 일괄 처리 및 워크플로우 실행을 위한 클라우드 데이터베이스입니다.

>[!NOTE]
>
>* Campaign v8에서 REST API를 사용할 수 있습니다. [자세히 알아보기](../dev/api/get-started-apis.md).

>[!CAUTION]
>
>* Campaign v8.5.1부터 Campaign v8에 대한 인증 프로세스가 변경되었습니다. 기술 운영자는 Adobe IMS(Identity Management System)를 사용하여 Campaign에 연결해야 합니다. [이 기술 노트](../../technotes/upgrades/ims-migration.md)에서 기존 기술 계정을 마이그레이션하는 방법을 알아봅니다.
>
>* [!DNL Adobe Campaign] v8에는 API 계층의 처리량(TPS)이 제한됩니다. 제한을 위반하면 표준 HTTP 오류(429)가 발생합니다. Managed Cloud Services 사용자는 Adobe에 문의하여 각 API에 대한 제한을 조정할 수 있습니다.
> 

## 필수 구성 요소 {#ac-api-prerequisites}

[!DNL Adobe Campaign] API를 사용하기 전에 다음 항목을 숙지해야 합니다.

* JavaScript
* SOAP 프로토콜
* [!DNL Adobe Campaign] 데이터 모델

API를 사용하고 [!DNL Adobe Campaign]과(와) 상호 작용하려면 데이터 모델도 잘 알고 있어야 합니다.

>[!NOTE]
>데이터 모델에 대한 전체 설명을 생성할 수 있습니다. [이 페이지](datamodel.md)에서 자세히 알아보십시오.


**관련 항목**

* [데이터 모델 모범 사례](datamodel-best-practices.md)
