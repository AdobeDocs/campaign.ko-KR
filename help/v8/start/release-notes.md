---
title: Campaign v8 릴리스 정보
description: Campaign v8 최신 릴리스
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 6c24f284cc9450238640de44db4e838732936a86
workflow-type: tm+mt
source-wordcount: '2170'
ht-degree: 12%

---

# 최신 릴리스 {#latest-release}

이 페이지에는 Campaign v8(콘솔) **최신 릴리스**&#x200B;에 포함된 새로운 기능, 개선 사항 및 수정 사항이 나와 있습니다. Campaign 릴리스와 버전, 업그레이드에 대한 자세한 내용은 [이 페이지](upgrades.md)에서 알아보세요. 다른 릴리스는 이 설명서의 이전 릴리스 섹션에 나열되어 있습니다.

## 릴리스 8.8.1 {#release-8-8-1}

_2025년 7월 9일 목요일_

### 새로운 기능 {#features-8-8-1}

이전에 소규모 고객을 위해 릴리스된 다음 기능은 이제 모든 Campaign FDA 환경에서 사용할 수 있습니다.

* **새 SMS 전송 커넥터** - SMS 전송 커넥터가 현대화되고 개선되어 송수신기 모드 SMPP 연결을 활성화하고 영구 SMPP 연결을 활성화하며 더 나은 호환성을 보장합니다. 이제 모든 새 SMS 구현에 새 SMS 외부 계정을 사용할 수 있습니다. 기존 구현도 여전히 지원하지만 새롭게 확장된 최신형 커넥터로 옮기는 것을 권장합니다. [자세히 알아보기](../send/sms/sms.md)

  >[!NOTE]
  >
  >이 기능은 **Campaign FFDA 배포**&#x200B;에 사용할 수 있는 [없음](../architecture/enterprise-deployment.md)입니다.

<!-- (from ACC rn, aleady in the product, to remove?) -->

<!-- * **Enrichment in transactional messages** (to remove?) -->

<!--
* **Multilingual delivery creation** in the Web UI - You can now send multiple email deliveries in different languages in Adobe Campaign Web User Interface. The Multilingual delivery feature allows you to choose the default language of your delivery as well as the different languages in which the delivery can be sent. You can also preview these deliveries in the languages you have chosen. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html)

ACC - Multilingual deliveries - Starting Campaign Web User interface April release, you will be able to send multiple email deliveries in different languages, and access the related dynamic reports. This capability will only be available in Adobe Campaign Web User Interface at the end of April, and require a server update to Campaign v8.7.4.
-->

<!--
*  **Visual fragments** in the Web UI - You can now create, use and archive content fragments. Visual fragments are pre-defined visual blocks that you can reuse across multiple email deliveries, or in content templates. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/content/manage-reusable-content/fragments/fragments.html){target="_blank"}

(already available in console and web, to remove?) 
web - * Visual fragments - You can now archive visual content fragments. Learn more
-->

<!--
* **Delivery alerting** in the Web UI - The Delivery alerting feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html){target="_blank"}
-->

<!--
* **Landing pages improvements**  in the Web UI- The following improvements to landing pages are now available:

    * You can now reference a default subscription/unsubscription landing page when configuring a service. When designing an email, if you define a link to that landing page, users submitting the landing page form are automatically subscribed to or unsubscribed from this service. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/audiences/work-with-services/manage-services.html#create-service){target="_blank"}
    * A new option in the landing page configuration allows anonymous visitors to access the landing page. If you unselect this option, only identified users can access and submit the form. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#create-landing-page){target="_blank"}
    * A new option in the landing page configuration allows to store additional internal data when the landing page is being submitted. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#create-landing-page){target="_blank"}
    * A new option enables to use a landing page for several services, making it dynamic. When adding a link to an email, if you select a dynamic landing page, you can select any service. If you select a landing page that has a specific service associated, this service will be automatically used (you cannot select another one). [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#define-actions-on-form-submission){target="_blank"}
    * Conditional content is now supported in landing pages. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html){target="_blank"}
    * You can link a landing page to a service, and send a confirmation message when users validate it. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html#lp-message){target="_blank"}
    * You can add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#captcha){target="_blank"}

web - * **Subscriptions with Landing pages** - You can now link a landing page to a service, and send a confirmation message when users validate it. [Learn more](../landing-pages/lp-content.md#lp-message){target="_blank"}.
Web - * **Captcha in landing pages** - You can now add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](../landing-pages/create-lp.md#captcha)
-->

<!--
* (from ACC rn, already in product, to remove?) **Rich Push Notification (GA)** - You can now send rich push notifications. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. With this version, a set of templates for rich push notifications are now available for your iOS and Android apps. [Read more](../send/rich-push-android.md). 
ACC * Rich Push Notification templates - You can now send rich push notifications via Android. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. Read more.
-->

이전에 제한된 가용성으로 릴리스된 다음 기능을 이제 **온디맨드**&#x200B;로 사용할 수 있습니다.

<!--
* **Dynamic Reporting** - You can now access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Dynamic reporting is also available for multilingual email deliveries and transactional messages. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html){target="_blank"}

ACC **Dynamic Reporting for Transactional messages** - You can now monitor your transactional messages in the Dynamic Reporting user interface. These reports provide the ability to the marketer to view the all the reporting metrics and dimensions of transactional messages, breakdown of deliveries sent through a template in real time. [Read more](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}
ACC - Dynamic Reporting - As a Campaign Standard migrated user, you can access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Read more
* **Dynamic Reporting for Multilingual** - Dynamic reporting is now available for multilingual email deliveries. For more information, refer to the [detailed documentation](../reporting/global-reports.md).
-->

* **Rest API** - 이제 Rest API를 사용하여 Adobe Campaign을 위한 통합을 만들고 Adobe Campaign과 사용하는 기술 패널을 연결하여 고유한 에코시스템을 구축할 수 있습니다. 트랜잭션 메시지 REST API는 SMS 채널에도 사용할 수 있습니다. 페이로드에 이메일과 휴대폰이 모두 있는 경우 “wishedChannel” 필드를 사용하여 채널을 지정할 수 있습니다. 제공되지 않으면 wishedChannel에서 SMS를 명시적으로 요청하지 않는 한 기본적으로 이메일이 사용됩니다. 이벤트 기반 트랜잭션 API는 이메일에도 사용할 수 있습니다. [자세히 알아보기](../dev/api/get-started-apis.md)

  >[!NOTE]
  >
  >이 기능은 **Campaign FFDA 배포**&#x200B;에 사용할 수 있는 [없음](../architecture/enterprise-deployment.md)입니다.

<!--
ACC - Rest APIs - As a Campaign Standard migrated user, you can use Rest APIs to create integrations for Adobe Campaign and build your own ecosystem by interfacing Adobe Campaign with the panel of technologies that you use. Read more
* **SMS REST API support (LA)** - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS. For more information, refer to the [detailed documentation](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target=_blank}.
ACC - SMS REST API support - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS.
ACC * **Transactional messaging REST APIs** - Event-based Transactional APIs are now available for Emails. [Read more](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}
-->

위에 나열된 기능 외에도 이 릴리스에는 Campaign 웹 사용자 인터페이스에서 사용할 수 있는 기능 집합이 포함되어 있습니다.

* [다국어 게재 만들기](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html#multilingual-delivery){target="_blank"}
* [게재 경고](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html){target="_blank"}
* [랜딩 페이지 개선 사항](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/get-started-lp.html){target="_blank"}
* [동적 보고](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"}(주문형 전용)
* [중앙 브랜딩](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html){target="_blank"}(주문형 전용)

Campaign 웹 UI [릴리스 노트](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html){target="_blank"}를 참조하세요.

### 일반 개선 사항 {#improvements-8-8-1}

* Microsoft Fabric 은 이제 Adobe Campaign FDA(Federated Data Access)를 통해 외부 데이터베이스로 지원됩니다. [자세히 알아보기](../config/external-accounts.md#transfer-data-external-accounts)
* 이제 Campaign v8에서 푸시 알림용 Android 15 및 iOS 18을 지원합니다. [자세히 알아보기](../start/compatibility-matrix.md#MobileSDK)
* 이제 Secure Virtual Private Network 터널링을 위한 온프레미스 데이터베이스 외에 클라우드 데이터베이스가 지원됩니다. [자세히 알아보기](../config/enhanced-security.md#vpn-databases)
* SMS 2.0 커넥터의 &quot;들어오는 트래픽&quot; 섹션에 &quot;공급자 ID&quot; 필드 집합이 새로 추가되었습니다. [자세히 알아보기](../send/sms/smpp-external-account.md#incoming-traffic)
* &quot;mailto&quot; 목록 구독 취소 메서드를 통해 구독 취소된 수신자는 더 이상 격리로 전송되지 않습니다. 게재와 연계된 서비스를 구독하거나 게재에 대해 정의된 서비스가 없는 경우 차단 목록 취소(프로필의 &quot;더 이상 연락 안 함&quot; 섹션)로 전송됩니다. [자세히 알아보기](../send/quarantines.md)
* 받은 편지함 렌더링 보고서의 개선된 버전을 이제 Adobe Campaign 클라이언트 콘솔에서 사용할 수 있습니다. [자세히 알아보기](../send/inbox-rendering.md)

### 해결 사항 {#fixes-8-8-1}

* SMS 2.0에서 유효 기간이 잘못되어 자동 답글이 수신되지 않던 문제를 해결했습니다. 이렇게 하면 마이그레이션 후 적절한 메시지 게재가 보장됩니다. (NEO-88088)
* `inSms` 테이블의 특정 필드가 올바르게 업데이트되지 않아 SMS 기능에 대한 정확한 데이터 삽입을 보장하는 SMS 2.0의 문제를 해결했습니다. (NEO-87906)

<!--
* NOOOO Addressed delivery preparation failures for IndiGo Aviation after upgrading to v7.4.2. This fix resolves personalization and deduplication-related errors, enabling smooth delivery workflows. (NEO-87693)
* NOOOO Corrected Redshift database function definitions in version 8.6.4, ensuring proper execution of functions like `AddDays`, `AddHours`, `AddMinutes`, and `AddSeconds`. (NEO-87305)
-->

* 클라이언트 콘솔에 자동 설치 메커니즘을 제공하여 사용자 개입 없이 대량 업그레이드를 용이하게 했습니다. 이렇게 하면 수동 설치의 문제가 해결됩니다. (NEO-69772)
* SQL 쿼리에서 누락되거나 잘못된 열 참조로 인한 데이터베이스 정리 워크플로우 오류를 해결했습니다. 이렇게 하면 로그 및 방문자 데이터를 적절히 지울 수 있습니다. (NEO-86813)
* 게재 로그에서 이벤트 날짜가 누락되는 문제를 해결했습니다. 이 수정 사항은 예약된 트리거 및 워크플로에 중요한 정확한 이벤트 날짜 채우기를 보장합니다. (NEO-86708)
* SMS 2.0에서 SMS 게재 로그 삽입 문제를 해결하여 `nmsBroadLogMid` 표에 제대로 로깅하도록 했습니다. (NEO-86556)
* DM 템플릿의 외부 게재 모드 관련 파일 추출 문제를 해결하여 호환성과 기능을 보장합니다. (NEO-86520)
* 여러 MID 인스턴스 간 분할 라우팅과 관련된 게재 처리 문제를 해결하여 정확한 게재 상태 업데이트 및 처리량을 보장합니다. (NEO-86500)
* Campaign Standard에서 Campaign v8로 마이그레이션 후 동적 보고서에서 누락된 추적 데이터를 수정하여 게재 추적 로그에 대한 정확한 보고를 보장합니다. (NEO-86419)
* 워크플로우가 두 번 실행되어 중복 키 위반이 발생하는 워크플로우 트리거 문제가 해결되었습니다. 이 수정 사항은 적절한 이벤트 처리 및 실행을 보장합니다. (NEO-86154)
* 배포 후 Redshift OOTB SQL 함수에 대한 호환성 문제를 해결하여 워크플로우에서 `GetDate()`과(와) 같은 함수를 올바르게 실행할 수 있도록 했습니다. (NEO-85834)
* URL이 첨부될 때 이미지가 사라지는 이메일 빌드의 렌더링 문제가 해결되었습니다. 이 수정 사항으로 받은 편지함 미리보기에 이미지가 제대로 표시됩니다. (NEO-85716)
* WebUI에서 둥근 닫는 따옴표의 렌더링을 수정하여 이메일 게재에서 문자가 정확하게 표시되도록 했습니다. (NEO-85687)
* 미러 페이지 내의 언어 변형 간에 적절하게 탐색할 수 있는 미러 페이지 링크 기능이 수정되었습니다. (NEO-85625)
* 웹 앱 날짜 선택기에서 날짜 형식 문제를 해결하여 일본어 날짜 형식(`yyyy-mm-dd`)과의 호환성을 보장합니다. (NEO-85234)
* 중간 소싱의 대체 라우팅 설정과 관련된 후 처리 워크플로 문제를 해결하여 적절한 워크플로 실행을 보장합니다. (NEO-85111)
* 예약된 시간에 따라 게재 부분이 올바른 순서로 처리되도록 웨이브를 사용할 때 Android 게재 처리량이 개선되었습니다. (NEO-84324)
* `to_varchar` 함수에서 null 처리 오류로 인해 게재 준비 오류가 발생하여 원활한 캠페인 실행이 보장되었습니다. (NEO-84108)
* 오래된 `libcurl` 및 `libssh2` 버전으로 인해 발생한 SFTP 연결 문제가 해결되어 Azure 호스팅 SFTP 서버와의 호환성을 보장합니다. (NEO-84038)
* 키 쌍 인증 오류와 관련된 Snowflake FDA 커넥터 문제가 해결되어 데이터베이스 연결이 정상적으로 이루어졌습니다. (NEO-84024)
* 푸시 게재에서 압력 규칙을 적절히 적용할 수 있도록 유형화 규칙 기능 문제를 해결했습니다. (NEO-84010)
* 업그레이드 후 일치하지 않는 날짜 및 타임스탬프 비교로 인해 발생한 BigQuery 쿼리 오류를 해결하여 필터링 조건과의 호환성을 보장합니다. (NEO-83826)
* 개인화 오류로 인해 일시 중지된 게재를 다시 시작할 때 게재 활동이 실패하는 문제를 해결했습니다. 이 수정 사항은 더 원활한 게재 워크플로우를 보장하며 일시 중지된 활동과 관련된 오류를 방지합니다. (NEO-83809)
* &quot;대상 레코드 로드 쿼리&quot; 옵션을 사용할 때 FFDA의 문제를 해결했습니다. &quot;order by&quot; 및 &quot;where&quot; 절에 대한 지원이 추가되었습니다. (NEO-83793)
* broadLogRcp 테이블의 null을 허용하지 않는 열에 null 값이 기록되어 발생하는 반복되는 게재 오류를 해결했습니다. 이 수정 사항은 게재 안정성을 개선하고 라이브 캠페인 중 오류를 방지합니다. (NEO-83729)
* 게재를 준비하는 동안 시드 주소가 중복되어 메시지 수가 일치하지 않는 문제를 해결했습니다. 이 수정 사항은 정확한 타겟팅을 보장하며 중복 오류를 방지합니다. (NEO-83703)
* 유효 기간이 지난 후 프로덕션 게재가 전송되어 법적 문제가 발생할 수 있는 중요한 문제를 해결했습니다. 이제 게재는 정의된 유효 기간을 엄격히 준수합니다. (NEO-83350)
* 대용량 데이터 볼륨을 Teradata 테이블로 로드하는 동안 발생한 공간 문제를 해결했습니다. 이 수정 사항은 데이터 처리를 최적화하고 프로덕션 환경의 간헐적인 오류를 해결합니다. (NEO-83252)
* RT 이벤트 처리가 지연되는 SendMetricsToNewRelic 오류와 관련된 기술 워크플로우 오류를 해결했습니다. 이 수정 사항으로 인해 워크플로우 실행이 더 원활해지고 이벤트 백로그가 방지됩니다. (NEO-83143)
* FFDA 상호 작용 인스턴스에서 ID에서 UUID로의 전환 문제로 인해 데이터베이스 정리 워크플로우 오류가 발생하는 문제를 해결했습니다. 이 업데이트는 적절한 정리 작업을 보장하고 시스템 로드를 줄입니다. (NEO-83138)
* 시드 멤버 내부 이름 길이에 대한 제한으로 인해 발생한 게재 실패를 해결했습니다. 이 수정 사항으로 게재 개인화에 영향을 주지 않고 더 긴 내부 이름을 사용할 수 있습니다. (NEO-83044)
* 무작위 오류로 인해 게재가 개인화 보류 중 상태로 넘어가는 문제를 해결했습니다. 이 업데이트를 통해 더 원활한 개인화 프로세스와 안정적인 게재 실행이 보장됩니다. (NEO-82781)
* API 오류 및 느림으로 인해 콘솔에서 오퍼 제안을 검토할 수 없는 문제를 해결했습니다. 이 수정 사항은 UI 응답성을 개선하고 적절한 오퍼 기능을 보장합니다. (NEO-82742)
* 사용자 지정 게재 개체를 사용할 때 Adobe Campaign 콘솔에서 발생하는 간헐적인 충돌을 해결했습니다. 이 수정 사항은 사용자 정의 워크플로우로 작업할 때 안정성과 안정성을 보장합니다. (NEO-82675)
* v7에서 v8로 마이그레이션한 후 보고된 느린 처리 및 워크플로우 오류를 해결했습니다. 이 업데이트는 캠페인 워크플로우를 최적화하고 적시에 실행되도록 합니다. (NEO-82665)

<!--
* Resolved an issue where sysfilters were generating incorrect SQL queries after upgrading to v8.6.3. This fix ensures proper query generation and restores sysfilter functionality. (NEO-82591)
-->

* MTA 하위 프로세스가 중단되어 푸시 및 WhatsApp 전송이 차단되는 중요한 문제를 해결했습니다. 이 업데이트는 더 원활한 통신 워크플로우를 보장하고 게재 병목 현상을 방지합니다. (NEO-82351)
* Teradata 업데이트 중에 GCP 테이블의 문자열 필드에서 오류가 발생하는 데이터 마이그레이션 문제를 해결했습니다. 이 수정 사항은 해결 방법이 필요하지 않으며 워크플로 효율성을 향상시킵니다. (NEO-82260)
* FFDA 인스턴스의 기본 데이터베이스를 설명하기 위해 데이터베이스 정리 논리를 업데이트했습니다. 따라서 존재하지 않는 테이블을 삭제하려는 불필요한 시도를 방지할 수 있습니다. 이 수정 사항은 정리 작업을 최적화합니다. (NEO-81879)
* 열거형 필드와 함께 하위 워크플로우를 사용하여 발생한 콘솔 충돌이 해결되었습니다. 이 수정 사항은 보강된 워크플로우로 작업할 때 안정성을 보장합니다. (NEO-81864)
* 게재 복제 후 대상 매핑의 하위 선호도 필드가 잘못 수정되어 워크플로우 오류가 발생하는 문제를 해결했습니다. 이 업데이트는 일관된 하위 선호도 값을 보장합니다. (NEO-81809)
* Adobe Campaign Classic v8의 파일 전송 활동에서 와일드카드 문자에 대한 지원을 추가하여 사용자가 워크플로우에서 동적 이름(예: `abc_*`)을 가진 파일을 업로드할 수 있습니다. (NEO-81758)
* Adobe Campaign Classic v8용 iOS 푸시 알림에서 `content-available` 플래그를 활성화하는 옵션이 도입되었습니다. 이 향상된 기능을 통해 모바일 앱은 받은 편지함에 알림을 저장할 수 있으며 백그라운드 업데이트를 지원하므로 APNS 제한으로 인해 발생하는 게재 삭제 문제를 해결할 수 있습니다. (NEO-81721)

<!--
* Updated the Campaign 7.4.1 release upgrade process to require manual installation of dependencies. Documentation has been provided to guide users on installing required libraries such as `epel-release`, `java-11-openjdk-headless`, and others. (NEO-81433)
-->

* Adobe Campaign Classic v8에서 BigQuery 연결에 대한 시간 초과 구성 옵션을 추가했습니다. 이 향상된 기능을 통해 사용자는 쿼리의 시간 제한 기간을 조정하여 기본 시간 제한 때문에 발생하는 쿼리 실패 문제를 해결할 수 있습니다. (NEO-81222)
* v8 마이그레이션 후 분할 및 대체 라우팅 외부 계정을 통해 전송된 게재에 대해 미러 페이지 URL이 실패하는 간헐적인 문제를 해결했습니다. 기본 게재 부분이 이제 `mirrorPageInfo`에 올바르게 복사되었습니다. (NEO-81105)

<!--
* Resolved an authentication failure issue with inMail caused by token expiration. Restarting the `nlserver` process now resolves the error. (NEO-80683)
-->

* 프로덕션 인스턴스의 올바른 URL(`https://experience.adobe.com`)을 가리키도록 클라이언트 콘솔의 &quot;새 웹 UI 액세스&quot; 단추를 수정했습니다. 이렇게 하면 프로덕션 환경에서 잘못된 URL이 발생하는 문제가 해결됩니다. (NEO-80673)
* 정렬 및 크기(세그먼트 비율로)를 모두 사용하여 SQL 오류가 발생하는 분할 활동의 문제를 해결했습니다. 이제 기능이 올바르게 작동합니다. (NEO-80432)
* `CCurlAzureBlobStorage::UploadStream`을(를) 사용하여 워크플로우의 충돌 문제를 해결했습니다. 이제 Azure Blob 저장 공간을 업로드하는 동안 워크플로우가 세그멘테이션 오류 없이 실행됩니다. (NEO-79598)
* 프로덕션 환경의 클라이언트 콘솔에서 미러 페이지를 볼 수 없던 문제를 해결했습니다. 이제 미러 페이지 링크가 이메일 보기와 콘솔 보기 모두에서 올바르게 작동합니다. (NEO-78946)
* 메시지 배달이 성공했지만 일부 로그가 &quot;배달 취소됨&quot;으로 잘못 표시되던 배달 로그 문제를 해결했습니다. 연락 날짜 및 이벤트 날짜 불일치와 관련된 근본 원인이 해결되었습니다. (NEO-78933)
* 보안을 개선하기 위해 `com.google.code.gson:gson` 라이브러리를 업데이트했습니다. (NEO-78299)
* 워크플로 오류를 일으킨 FDA 연결 로그(`nmsconnectionlogs`)의 중복 키 제약 조건 오류를 해결했습니다. 중복 ID를 방지하기 위해 삽입 논리가 조정되었습니다. (NEO-78050)
* 격리된 이메일 주소가 주소 테이블에서 모바일로 잘못 플래그가 지정되어 게재 분석 오류가 발생하는 문제가 해결되었습니다. 게재 개체 간 조정 논리가 수정되었습니다. (NEO-76986)
* Oracle 데이터베이스에서 컨트롤 그룹을 사용할 때 발생하는 게재 준비 오류를 해결했습니다. Oracle 데이터베이스와의 호환성을 보장하기 위해 SQL 쿼리 생성이 수정되었습니다. (NEO-76947)
* 새 달 전환 중 동시 폴더 생성으로 인한 게재 실패를 해결했습니다. 중복 키 위반을 방지하기 위해 게재 폴더 만들기 논리를 조정했습니다. (NEO-76824)
* Teradata 외부 계정의 일관성 없는 시간대 변환 문제를 해결했습니다. 이제 표시된 타임스탬프가 구성된 시간대 설정과 올바르게 정렬됩니다. (NEO-76716)
* 대규모 데이터 세트를 효율적으로 처리할 수 있도록 데이터베이스 정리 워크플로우가 개선되었습니다. 삭제 성능을 최적화하기 위해 행 ID 및 바인드 변수를 사용하는 새로운 접근 방식이 구현되었습니다. (NEO-76439)
* &quot;기타&quot; 채널을 사용한 외부 게재에서 출력 파일이 생성되지 않던 문제를 해결했습니다. 이제 게재 속성에 생성된 파일의 파일 경로가 올바르게 포함됩니다. (NEO-75962)
* 대규모 데이터 업데이트로 인해 `ffdaReplicateStagingData` 워크플로우에서 발생하는 오류를 수정했습니다. 워크플로우 오류를 방지하기 위해 시간 제한 설정 및 테이블 크기 관리를 최적화했습니다. (NEO-75643)
* DM 출력 파일을 미리 보기하면 대시보드가 비어 있는 문제가 해결되었습니다. 이제 파일 미리보기 후에 대시보드가 올바르게 표시됩니다. (NEO-75359)
* 클릭 수 및 열기 수를 포함하는 푸시 알림에 대한 추적 지표가 개선되었습니다. 이제 `@recipientClick`, `@personClick` 및 `@totalRecipientClick` 등의 지표가 모바일 알림 클릭을 고려합니다. (NEO-75240)
* 외부 취소 보류 상태인 게재 정리 워크플로우의 오류를 수정했습니다. 데이터베이스 레코드 검색 논리가 수정되었습니다. (NEO-74833)
* `nlserver` 출력 시간이 잘못된 러시아(UTC+3:00 모스크바)의 시간대 불일치 문제를 해결했습니다. 시간 동기화 로직이 업데이트되었습니다. (NEO-74754)
* MSSQL 데이터베이스에 대한 잘못된 SQL 구문으로 인해 `defaultMidSourcingDlvStat` 워크플로우에서 오류가 발생했습니다. 호환성을 위해 쿼리 생성 논리가 조정되었습니다. (NEO-74156)
* 웹 프로세스의 여러 충돌을 해결했습니다. (NEO-73174)
* 조건에 아포스트로피가 있을 때 BigQuery 쿼리가 실패하는 문제를 수정했습니다. 쿼리 처리 로직이 특수 문자를 올바르게 해석하도록 업데이트되었습니다. (NEO-72547)
* 제외 필터가 있는 유형화 규칙이 올바르게 작동하지 않던 문제를 해결했습니다. 게재 준비를 위한 SQL 쿼리 생성이 수정되었습니다. (NEO-72292)
* 바운스 관리를 위한 이벤트 날짜 및 연락처 날짜의 불일치를 해결했습니다. 시간대 처리 논리가 개선되었습니다. (NEO-72277)
* DM 게재에서 잘못 변환된 UTF-8 문자 처리를 개선했습니다. 이제 게재 실패를 방지하기 위해 숨겨진 문자가 올바르게 처리됩니다. (NEO-72148)
* 필터로 인해 저장 문제가 발생한 인바운드 SMS 활동의 오류를 수정했습니다. 이제 워크플로우가 오류를 생성하지 않고 올바르게 저장됩니다. (NEO-70427)
* 오퍼 공간의 그룹화된 자격 조건에 대한 SQL 쿼리 생성을 수정했습니다. 적절한 필터링을 위해 SQL 조건에 괄호가 없습니다. (NEO-70425)

<!--
* Updated the public documentation link in the `ffdaUnicity` workflow email template to point to the correct page for key management in v8. (NEO-67996)
-->

* HTTP 콘텐츠 또는 전송 인코딩 문제로 인해 BigQuery 데이터 로드 워크플로우에서 발생하는 간헐적인 오류를 수정했습니다. 연결 처리 논리가 개선되었습니다. (NEO-66989)

