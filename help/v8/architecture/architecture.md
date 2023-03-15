---
title: Campaign 아키텍처 시작
description: 환경 및 배포와 관련된 기본적인 사항과캠페인 환경에서 보고하는 방법을 살펴봅니다.
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 618e45b6948070c6b791d2bcefa8296b297bf25e
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 11%

---

# Campaign 아키텍처 시작{#gs-ac-archi}

## 환경 {#environments}

Campaign은 개별 인스턴스로서 사용할 수 있게 되었으며, 이때 각 인스턴스는 전체 캠페인 환경을 나타냅니다.

두 가지 유형의 환경을 사용할 수 있습니다.

* **프로덕션 환경**: 비즈니스 전문가를 위한 애플리케이션을 호스팅합니다.

* **비프로덕션 환경**: 애플리케이션 변경 사항이 프로덕션 환경에 푸시되기 전에 다양한 성능 및 품질 테스트에 사용됩니다.

한 환경에서 다른 환경으로 패키지를 내보내고 가져올 수 있습니다.

![](../assets/do-not-localize/book.png) 의 패키지에 대해 자세히 알아보십시오 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html){target="_blank"}

## 배포 모델{#ac-deployment}

두 가지 배포 모델을 사용할 수 있습니다:

* **Campaign FDA [!DNL Snowflake] 배포**

   In it [[!DNL Snowflake] FDA 배포](fda-deployment.md), [!DNL Adobe Campaign] v8이 [!DNL Snowflake] 페더레이션 데이터 액세스 기능을 통해 데이터에 액세스하려면 다음을 수행하십시오. 에 저장된 외부 데이터 및 정보에 액세스하여 처리할 수 있습니다 [!DNL Snowflake] Adobe Campaign 데이터 구조를 변경하지 않고 데이터베이스를 만듭니다. PostgreSQL은 기본 데이터베이스이고 Snowflake은 보조 데이터베이스입니다. 데이터 모델을 확장하고 데이터를 Snowflake에 저장할 수 있습니다. 그 후에 성능이 우수한 대용량 데이터 세트에 대해 ETL, 세그멘테이션 및 보고서를 실행할 수 있습니다.

* **Campaign Enterprise(FFDA) 배포**

   의 컨텍스트에서 [엔터프라이즈(FFDA) 배포](enterprise-deployment.md), [!DNL Adobe Campaign] v8은 두 개의 데이터베이스에서 작동합니다. 지역 [!DNL Campaign] 사용자 인터페이스 실시간 메시징 및 단일 쿼리 및 API를 통한 쓰기 및 클라우드에 대한 데이터베이스 [!DNL Snowflake] 캠페인 실행, 배치 쿼리 및 워크플로우 실행을 위한 데이터베이스.

   Campaign v8 Enterprise는 **FFDA(Full Federated Data Access)** 개념을 도입했습니다. 이제 모든 데이터는 클라우드 데이터베이스에서 원격으로 사용할 수 있습니다. Campaign v8 엔터프라이즈(FFDA) 배포는 이 새로운 아키텍처를 통해 데이터 관리를 간소화하므로 클라우드 데이터베이스에 인덱스를 작성할 필요가 없습니다. 표를 만들고 데이터를 복사하기만 하면 바로 시작할 수 있습니다. 클라우드 데이터베이스 기술은 성능 수준을 보장하기 위해 특정한 유지 관리가 필요 없습니다.

## 게재 실행 분할 {#split}

>[!AVAILABILITY]
>
>이 기능은 여러 MID 인스턴스 구성을 가진 고객만 사용할 수 있습니다.

Campaign v8 패키지에 따라 게재 실행을 담당하는 특정 수의 중간 소싱 인스턴스가 제공됩니다.

기본적으로 모든 채널에 대한 외부 계정은 **[!UICONTROL Alternate]** 라우팅 모드: 한 번에 하나씩 중간 인스턴스에서 교대로 전송됨을 의미합니다.

속도와 규모 면에서 모두 향상된 성능을 보장하기 위해 중간 소싱 인스턴스에 게재를 자동으로 분할하여 수신자에게 더 빨리 전달할 수 있습니다. 마케팅 인스턴스에서 게재를 실행할 때 이 작업은 투명합니다. 게재가 전송되면 마케팅 인스턴스로 다시 전송되기 전에 모든 로그가 함께 통합됩니다.

이렇게 하려면 **[!UICONTROL Split]** 라우팅 모드는 각 채널에 대한 프로비저닝을 통해 생성됩니다.

* 배달 분할 - 이메일(splitDeliveryEmail)
* 분할 게재 - SMS(splitDeliverySMS)
* 분할 배달 - iOS(splitDeliveryIOS)
* 배달 분할 - Android(splitDeliveryAndroid)

![](assets/splitted-delivery.png)

>[!IMPORTANT]
>
>분할 라우팅 모드는 &quot;배달 분할 - 이메일&quot; 계정에 대해 기본적으로 활성화되어 있습니다. 기타 모든 채널 외부 계정의 경우, 고객 지원 센터에 연락하여 이 옵션을 활성화하십시오.
>
>기본적으로 여러 mid 간에 전달을 분할하는 임계값 크기 값은 100K입니다. 의 &quot;NmsDelivery_MultiMidSplitThreshold&quot; 옵션에서 이 값을 변경할 수 있습니다 **[!UICONTROL Administration]** / **[!UICONTROL Platform]** / **[!UICONTROL Options]** 메뉴 아래의 제품에서 사용할 수 있습니다.

외부 계정을 분할하여 게재 전송을 위한 기본 계정으로 만들려면 게재 템플릿에서 라우팅 공급자를 변경해야 합니다. 이렇게 하려면 다음 단계를 수행합니다.

1. 로 이동합니다 **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Delivery templates]** 폴더를 열고 원하는 게재 템플릿을 엽니다. 이 예제에서는 이메일 게재 템플릿을 편집하려고 합니다.

   ![](assets/split-default-list.png)

1. 을(를) 클릭합니다. **[!UICONTROL Properties]** 버튼을 클릭하고 라우팅 공급자를 해당 분할 배달 외부 계정으로 변경합니다.

   ![](assets/split-default-delivery.png)

1. 변경 내용을 저장합니다. 템플릿을 사용하여 전송된 모든 게재는 이제 기본적으로 분할 라우팅 모드를 사용합니다.

<!--In addition, you can select split external accounts as the default routing provider for all future delivery templates. To do this, change the value of the **[!UICONTROL xtkoption NmsBroadcast_DefaultProvider]** option to the name of the split account.

![](assets/split-default-options.png) -->

## 메시지 센터 아키텍처{#transac-msg-archi}

트랜잭션 메시지(메시지 센터)는 트리거 메시지를 관리하기 위해 고안된 캠페인 모듈입니다.

![](../assets/do-not-localize/glass.png) 에서 트랜잭션 메시지를 보내는 방법 알아보기 [이 섹션](../send/transactional.md).

웹 사이트에서 고객이 수행한 작업에 대한 응답으로, 이벤트는 REST API를 통해 Campaign으로 전송되고, 메시지 템플릿에는 API 호출을 통해 제공된 정보 또는 데이터가 채워지고, 트랜잭션 메시지는 실시간으로 고객에게 전송됩니다. 이러한 메시지는 개별적으로 또는 이메일, SMS 또는 푸시 알림을 통해 일괄적으로 전송할 수 있습니다.

이 특정 아키텍처에서는 실행 셀이 제어 인스턴스와 분리되어 고가용성과 로드 관리를 보장합니다.

* 다음 **컨트롤 인스턴스** (또는 마케팅 인스턴스)는 마케터와 IT 팀이 메시지 템플릿을 만들고, 구성하고, 게시하는 데 사용됩니다. 또한 이 인스턴스는 이벤트 모니터링 및 기록을 중앙 집중화합니다.

   ![](../assets/do-not-localize/glass.png) 에서 메시지 템플릿을 만들고 게시하는 방법을 알아봅니다. [이 섹션](../send/transactional.md).

* 다음 **실행 인스턴스** 들어오는 이벤트(예: 암호 재설정 또는 웹 사이트의 주문)를 검색하고 개인화된 메시지를 보냅니다. 로드 밸런서를 통해 메시지를 처리하고 최대 가용성을 위해 진행할 이벤트 수의 크기를 조정하는 실행 인스턴스가 두 개 이상 있을 수 있습니다.

>[!CAUTION]
>
>제어 인스턴스와 실행 인스턴스는 다른 컴퓨터에 설치해야 합니다. 동일한 Campaign 인스턴스를 공유할 수 없습니다.

![](assets/messagecenter_diagram.png)

### 인증

이러한 기능을 사용하려면 Adobe Campaign 사용자가 제어 인스턴스에 로그인하여 트랜잭션 메시지 템플릿을 만들고, 시드 목록을 사용하여 메시지 미리 보기를 생성하고, 보고서를 표시하고 실행 인스턴스를 모니터링합니다.

* 단일 실행 인스턴스 호스팅된 Adobe의 메시지 센터 실행 인스턴스와 상호 작용할 때 외부 시스템은 제공된 계정 로그인 및 암호를 사용하여 세션 로그온 메서드에 api를 호출하여 세션 토큰(기본적으로 24시간 후에 만료)을 먼저 검색할 수 있습니다.
그런 다음 위의 호출에 대한 응답으로 실행 인스턴스에서 제공하는 sessionToken 을 사용하면 외부 애플리케이션이 각 SOAP 호출에 계정 로그인 및 암호를 포함하지 않고 통신을 보내기 위해 SOAP api 호출(rtEvents 또는 batchEvents)을 수행할 수 있습니다.

* 다중 실행 인스턴스 로드 밸런서 뒤에 여러 실행 인스턴스가 있는 다중 셀 실행 아키텍처에서 외부 응용 프로그램에서 호출하는 로그온 방법은 로드 밸런서를 통해 수행됩니다. 따라서 토큰 기반 인증을 사용할 수 없습니다. 사용자/암호 기반 인증이 필요합니다.

![](../assets/do-not-localize/book.png) 에서 트랜잭션 메시지 이벤트에 대해 자세히 알아보십시오 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html#about-transactional-messaging-datamodel){target="_blank"}
