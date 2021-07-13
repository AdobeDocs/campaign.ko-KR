---
product: Adobe Campaign
title: Campaign 보안 모범 사례
description: Campaign 보안 모범 사례 시작
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 1%

---

# Campaign 보안 모범 사례 {#ac-security}

Adobe에서 Adobe는 디지털 경험의 보안을 매우 중요하게 생각합니다. 보안 정책은 내부 소프트웨어 개발 및 운영 프로세스와 도구에 깊이 스며들어 있으며, EMC의 부서간 팀이 신속하게 사고를 예방, 감지 및 대응할 수 있도록 엄격한 조치를 취하고 있습니다.

또한 Adobe의 파트너, 선도적인 연구 업체, 보안 연구소 및 기타 업계 조직과의 공동 작업은 최신 위협 및 취약점에 대한 최신 정보를 지속적으로 제공하는 데 도움이 되며, Adobe는 정기적으로 고급 보안 기술을 제공하는 제품 및 서비스에 통합합니다.

## 개인 정보 보호

개인 정보 구성 및 경화는 보안 최적화의 주요 요소입니다. 다음은 개인 정보에 대해 따라야 할 몇 가지 모범 사례입니다.

* HTTP 대신 HTTPS를 사용하여 고객 개인 정보(PI)를 Protect
* 개인 정보를 보호하고 데이터가 오용되지 않도록 하려면 [PI 보기 제한](../dev/restrict-pi-view.md)을 사용하십시오
* 암호화된 암호가 제한되어 있는지 확인하십시오
* Protect 미러 페이지, 웹 애플리케이션 등의 개인 정보를 포함할 수 있는 페이지를 설정합니다.

?? 관리 Cloud Services 사용자인 Adobe은 사용자와 협력하여 환경에서 이러한 구성을 구현합니다.

## 개인화

컨텐츠에 개인화된 링크를 추가할 때는 잠재적인 보안 격차를 방지하기 위해 항상 URL의 호스트 이름 부분에 개인화를 사용하지 마십시오. 모든 URL 속성 &lt;`a href="">` 또는 `<img src="">`에 다음 예를 사용해서는 안 됩니다.

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## 데이터 제한

낮은 권한 인증 사용자가 암호화된 암호를 액세스할 수 없도록 해야 합니다. 이를 위해 다음과 같은 두 가지 주요 방법이 있습니다. 암호 필드에만 또는 전체 엔터티에 대한 액세스를 제한합니다.

이 제한 사항으로 암호 필드를 제거할 수 있지만, 모든 사용자의 인터페이스에서 외부 계정에 액세스할 수 있도록 유지합니다. [이 페이지](../dev/restrict-pi-view.md)에서 자세히 알아보십시오.

1. **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**&#x200B;로 이동합니다.

1. 새 **[!UICONTROL Extension of a schema]**&#x200B;을(를) 만듭니다.

1. **[!UICONTROL External Account]** (extAccount)을 선택합니다.

1. 마지막 화면에서는 새 srcSchema를 편집하여 모든 암호 필드에 대한 액세스를 제한할 수 있습니다.

   기본 요소(`<element name="extAccount" ... >`)를 다음과 같이 바꿀 수 있습니다.

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

   따라서 확장된 srcSchema는 다음과 같을 수 있습니다.

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
   >`$(loginId) = 0 or $(login) = 'admin'` 을 `hasNamedRight('admin')` 로 대체하여 관리자 권한이 있는 모든 사용자가 이러한 암호를 볼 수 있도록 할 수 있습니다.


## 액세스 관리

액세스 관리는 보안 강화의 중요한 부분입니다. 다음은 몇 가지 주요 우수 사례입니다.

* 충분한 보안 그룹 만들기
* 각 연산자에 적절한 액세스 권한이 있는지 확인합니다
* 관리 연산자를 사용하지 않도록 하고, 관리 그룹에 너무 많은 운영자가 없도록 하십시오

↗️ [Adobe Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management.html?lang=en#webapp-operator){target=&quot;_blank&quot;}에서 자세히 알아보기

## 코딩 지침

Adobe Campaign(워크플로우, Javascript, JSSP 등)에서 개발할 때에는 항상 다음 지침을 따르십시오.

* **스크립팅**: SQL 문을 사용하지 않도록 설정하고, 문자열 연결 대신 매개 변수화된 함수를 사용하고, 허용 목록에 사용할 SQL 함수를 추가하여 SQL 주입을 방지하십시오.

* **데이터 모델** 보안: 명명된 권한을 사용하여 운영자 작업을 제한하고 시스템 필터 추가(sysFilter)

* **웹 애플리케이션에서 캡처를 추가합니다**. 공개 랜딩 페이지 및 구독 페이지에 캡처를 추가합니다.

↗️ [Adobe Campaign Classic v7 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=en#installing-campaign-classic){target=&quot;_blank&quot;}에서 자세히 알아보기
