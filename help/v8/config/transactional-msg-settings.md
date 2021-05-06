---
solution: Campaign Classic
product: campaign
title: 캠페인 트랜잭션 메시지 설정
description: 캠페인 트랜잭션 메시지 설정
feature: 개요
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: c2d066ca2f935455861c3d6747c9805c847f2e0d
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# 트랜잭션 메시지 설정

:speech_bal풍선:관리 Cloud Services 사용자는 [Adobe](../start/support.md#support)에 연락하여 사용자 환경에서 캠페인 트랜잭션 메시지를 설치하고 구성합니다.

: 전구:트랜잭션 메시지 기능은 [이 섹션](../send/transactional.md)에 자세히 설명되어 있습니다.

: 전구:[이 페이지](../dev/architecture.md)에서 트랜잭션 메시징 아키텍처를 이해합니다.

## 권한 정의

Adobe Cloud에서 호스팅되는 메시지 센터 실행 인스턴스용 새 사용자를 만들려면 Adobe 고객 지원 센터에 문의해야 합니다. 메시지 센터 사용자는 &#39;실시간 이벤트&#39;(nmsRtEvent) 폴더에 액세스하기 위한 전용 권한이 필요한 특정 연산자입니다.

## 스키마 확장

제어 또는 실행 인스턴스에서 **Message Center 기술 워크플로**&#x200B;에 사용되는 스키마에 대해 수행된 모든 스키마 확장은 Adobe Campaign 트랜잭션 메시징 모듈에서 사용하는 다른 인스턴스에 복제되어야 합니다.

:arrow_upper_right:[Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/instance-configuration/technical-workflows.html?lang=en#control-instance-workflows)의 메시지 센터 기술 워크플로우에 대한 자세한 내용

## 트랜잭션 푸시 알림 보내기

모바일 앱 채널 모듈과 결합하면 트랜잭션 메시지를 통해 모바일 장치의 알림을 통해 트랜잭션 메시지를 푸시할 수 있습니다.

:arrow_upper_right:모바일 앱 채널은 [Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages)에 자세히 설명되어 있습니다.

트랜잭션 푸시 알림을 전송하려면 다음 구성을 수행해야 합니다.

1. **모바일 앱 채널** 패키지를 제어 및 실행 인스턴스에 설치합니다.

   >[!CAUTION]
   >
   >새 Campaign 내장 패키지를 설치하기 전에 라이선스 계약을 확인하십시오.

1. 실행 인스턴스에서 **모바일 응용 프로그램** 서비스 및 관련 모바일 응용 프로그램을 복제합니다.

Campaign이 트랜잭션 푸시 알림을 전송하려면 이벤트에 다음 요소가 포함되어야 합니다.

* 모바일 장치 ID:Android용 **registrationId** 및 iOS용 **deviceToken**. 이 ID는 알림을 보낼 &quot;주소&quot;를 나타냅니다.
* 응용 프로그램과 관련된 연결 정보를 검색할 수 있는 모바일 응용 프로그램 또는 통합 키(**uuid**)에 대한 링크입니다.
* 알림을 보낼 채널(**whoseChannel**):iOS의 경우 41, Android의 경우 42
* 개인화를 위한 기타 데이터

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

