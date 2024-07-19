---
title: 캠페인 트랜잭션 메시지 설정
description: 캠페인 트랜잭션 메시지 설정
feature: Transactional Messaging
role: Admin, Developer
level: Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 4%

---

# 트랜잭션 메시지 설정 {#mc-settings}

트랜잭션 메시지(메시지 센터)는 트리거된 메시지를 관리하기 위해 고안된 캠페인 모듈입니다. [이 섹션](../send/transactional.md)에서 트랜잭션 메시지에 대해 자세히 알아보세요.

[이 페이지](../architecture/architecture.md#transac-msg-archi)의 트랜잭션 메시지 아키텍처를 이해합니다.


>[!NOTE]
>
>관리 Cloud Service 사용자는 [Adobe에게 문의](../start/campaign-faq.md#support)하여 환경에 Campaign 트랜잭션 메시지를 설치하고 구성하세요.

## 권한 정의 {#mc-permissions}

Adobe 클라우드에서 호스팅되는 메시지 센터 실행 인스턴스에 대해 새 사용자를 만들려면 Adobe 전환 관리자에게 문의하십시오. 메시지 센터 사용자는 &#39;실시간 이벤트&#39;(nmsRtEvent) 폴더에 액세스하기 위해 전용 권한이 필요한 특정 운영자입니다.

## 스키마 확장  {#mc-schema-ext}

제어 또는 실행 인스턴스의 [메시지 센터 기술 워크플로우](#technical-workflows)에서 사용하는 스키마에 대한 모든 스키마 확장은 Adobe Campaign 트랜잭션 메시지 모듈에서 사용하는 다른 인스턴스에 복제해야 합니다.

## 트랜잭션 푸시 알림 보내기 {#mc-transactional-push}

트랜잭션 메시지를 [모바일 앱 채널 모듈](../send/push.md)과(와) 결합하면 모바일 장치에서 알림을 통해 트랜잭션 메시지를 푸시할 수 있습니다.

트랜잭션 푸시 알림을 전송하려면 다음 구성을 수행해야 합니다.

1. 컨트롤 및 실행 인스턴스에 **모바일 앱 채널** 패키지를 설치합니다.

   >[!CAUTION]
   >
   >새 Campaign 기본 제공 패키지를 설치하기 전에 라이선스 계약을 확인하십시오.

1. 실행 인스턴스에서 **모바일 응용 프로그램** 서비스 및 연결된 모바일 응용 프로그램을 복제합니다.

또한 이벤트에는 다음 요소가 포함되어야 합니다.

* 모바일 장치 ID: Android의 경우 **registrationId**, iOS의 경우 **deviceToken**. 이 ID는 알림이 전송되는 &quot;주소&quot;를 나타냅니다.
* 응용 프로그램에 대한 연결 정보를 검색할 수 있는 모바일 응용 프로그램 또는 통합 키(**uuid**)에 대한 링크입니다.
* 알림을 보낼 채널(**wishedChannel**): iOS의 경우 41, Android의 경우 42.
* 기타 모든 개인화 데이터.

다음은 트랜잭션 푸시 알림을 전송하는 이벤트 구성의 예입니다.

```xml
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation="none" uuid="com.adobe.NeoMiles"/>
                <ctx>
                    <deliveryTime>1:30 PM</deliveryTime>
                    <url>http://www.adobe.com</url>
                </ctx>
              </rtEvent>

         </urn:domEvent>
     </urn:PushEvent>           
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## 이벤트 제거 {#purge-events}

배포 마법사 설정을 조정하여 데이터베이스에 데이터를 저장하는 시간을 구성할 수 있습니다.

이벤트 삭제는 **데이터베이스 정리** 기술 워크플로우에서 자동으로 수행됩니다. 이 워크플로우는 실행 인스턴스에 수신 및 저장된 이벤트와 제어 인스턴스에 보관된 이벤트를 삭제합니다.

화살표를 적절히 사용하여 **이벤트**(실행 인스턴스) 및 **보관된 이벤트**(제어 인스턴스)에 대한 제거 설정을 변경합니다.


## 기술 워크플로우 {#technical-workflows}

트랜잭션 메시지 템플릿을 배포하기 전에 컨트롤 및 실행 인스턴스의 기술 워크플로우가 시작되었는지 확인해야 합니다.

그런 다음 **관리 > 프로덕션 > 메시지 센터** 폴더에서 이러한 워크플로에 액세스할 수 있습니다.

### 인스턴스 워크플로 제어 {#control-instance-workflows}

제어 인스턴스에서는 각 **[!UICONTROL Message Center execution instance]** 외부 계정에 대해 하나의 보관 워크플로우를 만들어야 합니다. **[!UICONTROL Create the archiving workflow]** 단추를 클릭하여 워크플로를 만들고 시작합니다.

### 실행 인스턴스 워크플로 {#execution-instance-workflows}

실행 인스턴스에서 다음 기술 워크플로우를 시작해야 합니다.

* **[!UICONTROL Processing batch events]**(내부 이름: **[!UICONTROL batchEventsProcessing]**): 이 워크플로우를 사용하면 메시지 템플릿에 연결되기 전에 대기열의 일괄 처리 이벤트를 분류할 수 있습니다.
* **[!UICONTROL Processing real time events]**(내부 이름: **[!UICONTROL rtEventsProcessing]**): 이 워크플로를 사용하면 대기열의 실시간 이벤트가 메시지 템플릿에 연결되기 전에 분류할 수 있습니다.
* **[!UICONTROL Update event status]**(내부 이름: **[!UICONTROL updateEventStatus]**): 이 워크플로를 사용하면 이벤트에 상태를 지정할 수 있습니다.

  가능한 이벤트 상태는 다음과 같습니다.

   * **[!UICONTROL Pending]**: 이벤트가 큐에 있습니다. 메시지 템플릿이 아직 할당되지 않았습니다.
   * **[!UICONTROL Pending delivery]**: 이벤트가 큐에 있고 메시지 템플릿이 할당되어 게재에 의해 처리되는 중입니다.
   * **[!UICONTROL Sent]**: 이 상태는 게재 로그에서 복사됩니다. 게재가 전송되었음을 의미합니다.
   * **[!UICONTROL Ignored by the delivery]**: 이 상태는 게재 로그에서 복사됩니다. 게재가 무시되었다는 뜻입니다.
   * **[!UICONTROL Delivery failed]**: 이 상태는 게재 로그에서 복사됩니다. 게재에 실패했다는 뜻입니다.
   * **[!UICONTROL Event not taken into account]**: 이벤트를 메시지 템플릿에 연결할 수 없습니다. 이벤트가 처리되지 않습니다.
