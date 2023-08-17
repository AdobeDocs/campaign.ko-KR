---
title: Campaign 보안 모범 사례
description: Campaign 보안 모범 사례 시작
feature: Privacy, PI
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 1%

---

# Campaign 보안 모범 사례 {#ac-security}

Adobe 시 디지털 환경의 보안을 매우 중요하게 생각합니다. 보안 관행은 내부 소프트웨어 개발 및 운영 프로세스 및 도구에 깊이 배어있으며, 여러 분야의 다양한 팀이 협력하여 사건을 신속하게 예방, 감지 및 대응합니다.

또한 파트너, 주요 연구원, 보안 연구 기관 및 기타 산업 조직과의 공동 작업을 통해 최신 위협 및 취약점을 최신 상태로 유지할 수 있으며, 고급 보안 기술을 제공하는 제품 및 서비스에 정기적으로 통합합니다.

## 개인 정보 보호

개인 정보 보호 구성 및 강화는 보안 최적화의 핵심 요소입니다. 다음은 개인 정보와 관련하여 따라야 할 몇 가지 모범 사례입니다.

* HTTP 대신 HTTPS를 사용하여 고객 개인 정보(PI) Protect
* 사용 [PI 보기 제한](../dev/restrict-pi-view.md) 개인 정보 보호 및 데이터 오용 방지
* 암호화된 암호가 제한되어 있는지 확인하십시오.
* Protect 미러 페이지, 웹 애플리케이션 등과 같은 개인 정보가 포함될 수 있는 페이지입니다.

![](../assets/do-not-localize/speech.png)  관리 Cloud Service 사용자는 Adobe과 함께 환경에 이러한 구성을 구현합니다.


## 액세스 관리

액세스 관리는 보안 강화의 중요한 부분입니다. 다음은 몇 가지 주요 모범 사례입니다.

* 충분한 보안 그룹 만들기
* 각 운영자에게 적절한 액세스 권한이 있는지 확인합니다

의 권한에 대해 자세히 알아보기 [이 섹션](../start/gs-permissions.md)

## 코딩 지침

Adobe Campaign(워크플로우, Javascript, JSSP 등)에서 개발할 때는 항상 다음 지침을 따르십시오.

* **스크립팅**: SQL 문을 방지하고 문자열 연결 대신 매개 변수가 있는 함수를 사용하십시오. 사용할 SQL 함수를 허용 목록에 추가하여 SQL 삽입을 방지하십시오.

* **데이터 모델 보호**: 명명된 권한을 사용하여 연산자 작업을 제한하고 시스템 필터(sysFilter)를 추가합니다.

* **웹 애플리케이션에서 captcha 추가**: 공개 랜딩 페이지 및 구독 페이지에 captcha를 추가합니다.

![](../assets/do-not-localize/book.png) 다음에서 자세히 알아보기 [Adobe Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}


## 개인화

콘텐츠에 개인화된 링크를 추가할 때 잠재적인 보안 차이를 방지하기 위해 항상 URL의 호스트 이름 부분에 개인화를 두지 마십시오. 다음 예제는 모든 URL 특성 &lt;`a href="">` 또는 `<img src="">`:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## 데이터 제한

권한이 낮은 인증된 사용자가 암호화된 암호에 액세스할 수 없도록 해야 합니다. 이를 위해 두 가지 기본 방법이 있습니다. 암호 필드에만 또는 전체 엔터티에 대한 액세스를 제한합니다.

이 제한 사항을 사용하면 암호 필드를 제거할 수 있지만 모든 사용자의 인터페이스에서 외부 계정에 액세스할 수 있는 상태를 유지합니다. [이 페이지](../dev/restrict-pi-view.md)에서 자세히 알아보십시오.

1. 들어가기 **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**.

1. 새로 만들기 **[!UICONTROL Extension of a schema]**.

1. 선택 **[!UICONTROL External Account]** (extAccount).

1. 마지막 화면에서는 새 srcSchema를 편집하여 모든 암호 필드에 대한 액세스를 제한할 수 있습니다.

   주 요소(`<element name="extAccount" ... >`) 기준:

   ```
   <element name="extAccount">
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
       <element name="s3Account">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
       </element>
       <element name="wapPush">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
       <element name="mms">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
   </element>
   ```

   이렇게 확장된 srcSchema는 다음과 같이 표시됩니다.

   ```
   <...>
       <element name="extAccount">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
           <element name="s3Account">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
           </element>
           <element name="wapPush">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
           <element name="mms">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
       </element>
   <...> 
   ```

   >[!NOTE]
   >
   >다음을 바꿀 수 있습니다. `$(loginId) = 0 or $(login) = 'admin'` 작성자: `hasNamedRight('admin')` 관리자 권한이 있는 모든 사용자가 이러한 암호를 볼 수 있도록 합니다.


## 액세스 관리

액세스 관리는 보안 강화의 중요한 부분입니다. 다음은 몇 가지 주요 모범 사례입니다.

* 충분한 보안 그룹 만들기
* 각 운영자에게 적절한 액세스 권한이 있는지 확인합니다

의 권한에 대해 자세히 알아보기 [이 섹션에서](../start/gs-permissions.md).

## 코딩 지침

Adobe Campaign(워크플로우, Javascript, JSSP 등)에서 개발할 때는 항상 다음 지침을 따르십시오.

* **스크립팅**: SQL 문을 방지하고 문자열 연결 대신 매개 변수가 있는 함수를 사용하십시오. 사용할 SQL 함수를 허용 목록에 추가하여 SQL 삽입을 방지하십시오.

* **데이터 모델 보호**: 명명된 권한을 사용하여 연산자 작업을 제한하고 시스템 필터(sysFilter)를 추가합니다.

* **웹 애플리케이션에서 captcha 추가**: 공개 랜딩 페이지 및 구독 페이지에 captcha를 추가합니다.

![](../assets/do-not-localize/book.png) 다음에서 자세히 알아보기 [Adobe Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}
