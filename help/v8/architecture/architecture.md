---
title: Campaign 아키텍처 시작
description: 환경 및 배포와 관련된 기본적인 사항과캠페인 환경에서 보고하는 방법을 살펴봅니다.
feature: Architecture, Deployment
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 561e4b6d2c99e98e068132c80c2bebb756b60a44
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 10%

---

# Campaign 아키텍처 시작{#gs-ac-archi}

## 환경 {#environments}

Campaign은 각 인스턴스가 전체 Campaign 환경을 나타내는 개별 인스턴스로 사용할 수 있습니다.

두 가지 유형의 환경을 사용할 수 있습니다.

* **프로덕션 환경**: 비즈니스 전문가를 위한 애플리케이션을 호스팅합니다.

* **비프로덕션 환경**: 애플리케이션 변경 사항이 프로덕션 환경에 푸시되기 전에 다양한 성능 및 품질 테스트에 사용됩니다.

한 환경에서 다른 환경으로 패키지를 내보내고 가져올 수 있습니다.

![](../assets/do-not-localize/book.png) 의 패키지에 대해 자세히 알아보기 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html){target="_blank"}

## 배포 모델{#ac-deployment}

두 가지 배포 모델을 사용할 수 있습니다:

* **Campaign FDA 배포**

  의 [FDA 배포](fda-deployment.md), [!DNL Adobe Campaign] v8에 연결할 수 있음 [!DNL Snowflake] Federated Data Access 기능을 통해 데이터에 액세스하려면에 저장된 외부 데이터 및 정보에 액세스하고 이를 처리할 수 있습니다. [!DNL Snowflake] Adobe Campaign 데이터의 구조를 변경하지 않고 데이터베이스를 구축할 수 있습니다. PostgreSQL은 기본 데이터베이스이며 Snowflake을 보조 데이터베이스로 사용하여 데이터 모델을 확장한 다음 데이터를 Snowflake에 저장할 수 있습니다. 그런 다음 ETL, 세그먼테이션 및 뛰어난 성능이 포함된 대규모 데이터 세트에 대한 보고서를 실행할 수 있습니다.

  >[!NOTE]
  >
  >이 배포 모델에서는 [!DNL Snowflake] 보조 데이터베이스는 요청 시에만 사용할 수 있습니다. 을(를) 사용하여 배포를 업데이트하려면 [!DNL Snowflake], Adobe 전환 관리자에게 문의하십시오.
  >

* **Campaign Enterprise(FFDA) 배포**

  의 맥락에서 [엔터프라이즈(FFDA) 배포](enterprise-deployment.md), [!DNL Adobe Campaign] v8은 두 개의 데이터베이스를 사용합니다. 하나는 로컬이고, 다른 하나는 [!DNL Campaign] API 및 클라우드를 통한 사용자 인터페이스 실시간 메시징 및 단일 쿼리 및 쓰기를 위한 데이터베이스 [!DNL Snowflake] 캠페인 실행, 일괄 쿼리 및 워크플로우 실행을 위한 데이터베이스.

  Campaign v8 Enterprise는 **FFDA(Full Federated Data Access)** 개념을 도입했습니다. 이제 모든 데이터는 클라우드 데이터베이스에서 원격으로 사용할 수 있습니다. Campaign v8 엔터프라이즈(FFDA) 배포는 이 새로운 아키텍처를 통해 데이터 관리를 간소화하므로 클라우드 데이터베이스에 인덱스를 작성할 필요가 없습니다. 표를 만들고 데이터를 복사하기만 하면 바로 시작할 수 있습니다. 클라우드 데이터베이스 기술은 성능 수준을 보장하기 위해 특정한 유지 관리가 필요 없습니다.

## 분할 게재 실행 {#split}

>[!AVAILABILITY]
>
>이 기능은 여러 MID 인스턴스 구성이 있는 고객만 사용할 수 있습니다.

Campaign v8 패키지에 따라 게재 실행을 담당하는 특정 수의 중간 소싱 인스턴스가 제공됩니다.

기본적으로 모든 채널의 외부 계정은 **[!UICONTROL Alternate]** 라우팅 모드: 한 번에 하나의 게재가 각 mid 인스턴스에서 교대로 전송됩니다.

속도와 규모 면에서 모두 더 나은 성능을 보장하기 위해 중간 소싱 인스턴스 간에 게재를 자동으로 분할하여 수신자에게 더 빨리 게재할 수 있습니다. 이 작업은 마케팅 인스턴스에서 게재를 실행할 때 투명합니다. 게재가 전송되면 모든 로그가 통합되어 마케팅 인스턴스로 다시 단일 게재 개체로 전송됩니다.

이렇게 하려면 를 사용하여 추가 외부 계정을 **[!UICONTROL Split]** 라우팅 모드는 각 채널에 대한 프로비저닝 시 생성됩니다.

* 분할 게재 - 이메일(splitDeliveryEmail)
* 분할 게재 - SMS(splitDeliverySMS)
* 분할 게재 - iOS(splitDeliveryIOS)
* 분할 게재 - Android(splitDeliveryAndroid)

![](assets/splitted-delivery.png)

>[!IMPORTANT]
>
>분할 라우팅 모드는 &quot;분할 게재 - 이메일&quot; 계정에 대해 기본적으로 활성화됩니다. 기타 모든 채널 외부 계정의 경우 Adobe 전환 관리자에게 문의하여 옵션을 활성화하십시오.
>
>기본적으로 여러 MID 간에 게재를 분할하는 임계값 크기 값은 100K입니다. 의 &quot;NmsDelivery_MultiMidSplitThreshold&quot; 옵션에서 이 값을 변경할 수 있습니다. **[!UICONTROL Administration]** / **[!UICONTROL Platform]** / **[!UICONTROL Options]** 메뉴 아래의 제품에서 사용할 수 있습니다.

외부 계정을 분할해서 게재를 보내기 위한 기본 계정으로 만들려면 게재 템플릿에서 라우팅 공급자를 변경해야 합니다. 이렇게 하려면 다음 단계를 수행합니다.

1. 다음 위치로 이동 **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Delivery templates]** 폴더를 만들고 원하는 게재 템플릿을 엽니다. 이 예제에서는 이메일 게재 템플릿을 편집하려고 합니다.

   ![](assets/split-default-list.png)

1. 다음을 클릭합니다. **[!UICONTROL Properties]** 버튼을 누르고 라우팅 공급자를 해당 분할 게재 외부 계정으로 변경합니다.

   ![](assets/split-default-delivery.png)

1. 변경 내용을 저장합니다. 이제 템플릿을 사용하여 보낸 모든 게재는 기본적으로 분할 라우팅 모드를 사용하게 됩니다.

<!--In addition, you can select split external accounts as the default routing provider for all future delivery templates. To do this, change the value of the **[!UICONTROL xtkoption NmsBroadcast_DefaultProvider]** option to the name of the split account.

![](assets/split-default-options.png) -->

## 메시지 센터 아키텍처{#transac-msg-archi}

트랜잭션 메시지(메시지 센터)는 트리거 메시지를 관리하기 위해 고안된 캠페인 모듈입니다.

![](../assets/do-not-localize/glass.png) 트랜잭션 메시지를 보내는 방법 알아보기 [이 섹션](../send/transactional.md).

웹 사이트에서의 고객 동작에 대한 응답으로, 이벤트는 REST API를 통해 Campaign으로 전송되고, 메시지 템플릿은 API 호출을 통해 제공된 정보 또는 데이터로 채워지고, 트랜잭션 메시지는 실시간으로 고객에게 전송됩니다. 이러한 메시지는 이메일, SMS 또는 푸시 알림을 통해 개별적으로 또는 일괄적으로 전송할 수 있습니다.

이러한 특정 아키텍처에서는 실행 셀을 제어 인스턴스와 분리하여 고가용성 및 부하 관리를 보장합니다.

* 다음 **컨트롤 인스턴스** (또는 마케팅 인스턴스)는 마케터와 IT 팀이 메시지 템플릿을 만들고 구성하고 게시하는 데 사용됩니다. 또한 이 인스턴스는 이벤트 모니터링 및 내역을 중앙 집중화합니다.

  ![](../assets/do-not-localize/glass.png) 에서 메시지 템플릿을 만들고 게시하는 방법에 대해 알아봅니다. [이 섹션](../send/transactional.md).

* 다음 **실행 인스턴스** 들어오는 이벤트(예: 암호 재설정 또는 웹 사이트의 주문)를 검색하고 개인화된 메시지를 전송합니다. 로드 밸런서를 통해 메시지를 처리하고 최대 가용성을 위해 처리할 이벤트 수를 확장하기 위한 실행 인스턴스가 두 개 이상 있을 수 있습니다.

>[!CAUTION]
>
>제어 인스턴스와 실행 인스턴스를 다른 컴퓨터에 설치해야 합니다. 동일한 Campaign 인스턴스를 공유할 수 없습니다.

![](assets/messagecenter_diagram.png)

### 인증

Adobe Campaign 사용자는 이러한 기능을 사용하기 위해 제어 인스턴스에 로그온하여 트랜잭션 메시지 템플릿을 만들고 시드 목록을 사용하여 메시지 미리 보기를 생성하며 보고서를 표시하고 실행 인스턴스를 모니터링합니다.

* 단일 실행 인스턴스 Adobe 호스팅 메시지 센터 실행 인스턴스와 상호 작용할 때 외부 시스템은 먼저 제공된 계정 로그인 및 암호를 사용하여 세션 로그온 메서드에 대한 api 호출을 수행하여 세션 토큰(기본적으로 24시간 후에 만료됨)을 검색할 수 있습니다.
그런 다음 위의 호출에 대한 응답으로 실행 인스턴스가 제공하는 sessionToken을 사용하여 외부 애플리케이션은 계정 로그인 및 암호를 각 SOAP 호출에 포함할 필요 없이 SOAP api 호출(rtEvents 또는 batchEvents)을 수행하여 통신을 전송할 수 있습니다.

* 여러 실행 인스턴스 로드 밸런서 뒤에 여러 실행 인스턴스가 있는 다중 셀 실행 아키텍처에서 외부 응용 프로그램에서 호출한 로그온 메소드가 로드 밸런서를 거칩니다. 따라서 토큰 기반 인증을 사용할 수 없습니다. 사용자/암호 기반 인증이 필요합니다.

에서 트랜잭션 메시지 이벤트에 대해 자세히 알아보기 [이 페이지](../send/event-processing.md).
