---
title: Campaign 트랜잭션 메시지 설정
description: Campaign 트랜잭션 메시지 설정
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# 트랜잭션 메시지 설정

![](../assets/do-not-localize/speech.png)  관리 Cloud Services 사용자로, [연락처 Adobe](../start/campaign-faq.md#support) 를 사용 중인 환경에 Campaign 트랜잭션 메시지를 설치하고 구성하려면 다음을 수행하십시오.

![](../assets/do-not-localize/glass.png) 트랜잭션 메시지 기능은 [이 섹션](../send/transactional.md).

![](../assets/do-not-localize/glass.png) 의 트랜잭션 메시지 아키텍처 이해 [이 페이지](../dev/architecture.md).

## 권한 정의

Adobe Cloud에서 호스팅되는 메시지 센터 실행 인스턴스에 대한 새 사용자를 만들려면 Adobe 고객 지원 센터에 문의해야 합니다. 메시지 센터 사용자는 &#39;실시간 이벤트&#39;(nmsRtEvent) 폴더에 액세스하기 위해 전용 권한이 필요한 특정 연산자입니다.

## 스키마 확장

에서 사용하는 스키마에서 만들어진 모든 스키마 확장 **메시지 센터 기술 워크플로우** 제어 또는 실행 인스턴스에서 Adobe Campaign 트랜잭션 메시지 모듈에서 사용하는 다른 인스턴스에 복제해야 합니다.

![](../assets/do-not-localize/book.png) 의 메시지 센터 기술 워크플로우에 대해 자세히 알아보십시오 [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html#technical-workflows)

## 트랜잭션 푸시 알림 보내기

모바일 앱 채널 모듈과 결합하면 트랜잭션 메시지를 통해 모바일 장치의 알림을 통해 트랜잭션 메시지를 푸시할 수 있습니다.

![](../assets/do-not-localize/book.png) 모바일 앱 채널은에 자세히 설명되어 있습니다. [Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages).

트랜잭션 푸시 알림을 전송하려면 다음 구성을 수행해야 합니다.

1. 설치 **모바일 앱 채널** 를 제어 및 실행 인스턴스에 패키지화합니다.

   >[!CAUTION]
   >
   >새 Campaign 기본 제공 패키지를 설치하기 전에 라이선스 계약을 확인하십시오.

1. 복제 **모바일 애플리케이션** 실행 인스턴스의 서비스 및 관련 모바일 애플리케이션.

Campaign에서 트랜잭션 푸시 알림을 전송하려면 이벤트에 다음 요소가 포함되어야 합니다.

* 모바일 장치 ID: **registrationId** Android 및 **deviceToken** iOS용. 이 ID는 알림을 전송할 &quot;주소&quot;를 나타냅니다.
* 모바일 애플리케이션 또는 통합 키에 대한 링크(**uuid**)을 클릭하여 응용 프로그램과 관련된 연결 정보를 검색할 수 있습니다.
* 알림을 전송할 채널(**whospredChannel**): iOS용 41 및 Android용 42.
* 개인화를 위해 활용할 기타 데이터입니다.

다음은 이 정보를 포함하는 이벤트의 예입니다.

```
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation=”none” uuid="com.adobe.NeoMiles"/>
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
