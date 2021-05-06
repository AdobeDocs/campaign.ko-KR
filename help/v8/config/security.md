---
solution: Campaign Classic
product: campaign
title: 캠페인 보안 모범 사례
description: Campaign 보안 모범 사례 시작하기
translation-type: tm+mt
source-git-commit: aad5f67453079211b14e371da09e9dfc757acba9
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 0%

---

# 캠페인 보안 모범 사례 {#ac-security}

Adobe은 디지털 경험의 보안을 매우 중요하게 생각합니다. 보안 방침은 내부 소프트웨어 개발 및 운영 프로세스와 툴에 깊이 통합되어 있으며 이러한 사고를 예방하고 이를 신속하게 감지하고 이에 대응할 수 있도록 Adobe의 교차 업무 팀이 엄격한 뒤에 있습니다.

또한 Adobe는 파트너, 선도적인 연구원, 보안 연구 기관 및 기타 업계 조직과 공동으로 작업함으로써 최신 위협 및 취약점을 지속적으로 파악하고 고급 보안 기술을 Adobe가 제공하는 제품 및 서비스에 정기적으로 통합합니다.

## 개인 정보

개인 정보 구성 및 강화는 보안 최적화의 핵심 요소입니다. 다음은 개인 정보에 대한 몇 가지 우수 사례입니다.

* Protect HTTP 대신 HTTPS를 사용하여 고객 개인 정보(PI) 보호
* [PI 보기 제한](../dev/restrict-pi-view.md)을 사용하여 개인 정보를 보호하고 데이터가 오용되지 않도록 합니다.
* 암호화된 암호가 제한되어 있는지 확인합니다.
* Protect은 미러 페이지, 웹 애플리케이션 등과 같은 개인 정보를 포함할 수 있는 페이지를 말합니다.

:speech_bal풍선:관리 Cloud Services 사용자는 Adobe과 함께 이러한 구성을 환경에 구현하여 사용할 수 있습니다.

## 개인화

콘텐츠에 개인화된 링크를 추가할 때 잠재적인 보안 격차를 방지하기 위해 항상 URL의 호스트 이름 부분에 개인화를 사용하지 마십시오. 다음 예는 모든 URL 특성 &lt;`a href="">` 또는 `<img src="">`에서 사용해서는 안 됩니다.

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## 데이터 제한

낮은 권한 인증 사용자에 의해 암호화된 암호에 액세스할 수 없도록 해야 합니다. 이를 위해서는 두 가지 주요 방법이 있습니다.암호 필드에만 또는 전체 엔티티에 대한 액세스를 제한합니다(빌드 >= 8770 필요).

이 제한을 통해 암호 필드를 제거할 수 있지만 인터페이스에서 모든 사용자에 대해 외부 계정에 액세스할 수 있도록 할 수 있습니다. [이 페이지](../dev/restrict-pi-view.md)에서 자세히 알아보십시오.

1. **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**&#x200B;로 이동합니다.

1. 새 **[!UICONTROL Extension of a schema]**&#x200B;을(를) 만듭니다.

1. **[!UICONTROL External Account]**(extAccount)을 선택합니다.

1. 마지막 화면에서 새 srcSchema를 편집하여 모든 암호 필드에 대한 액세스를 제한할 수 있습니다.

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

   확장된 srcSchema는 다음과 같습니다.

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
   >`$(loginId) = 0 or $(login) = 'admin'`을(를) `hasNamedRight('admin')`에 다시 배치하여 관리자 권한이 있는 모든 사용자가 이러한 암호를 볼 수 있도록 할 수 있습니다.


## 액세스 관리

액세스 관리는 보안 강화를 위한 중요한 요소입니다. 다음은 몇 가지 주요 우수 사례입니다.

* 충분한 보안 그룹 만들기
* 각 연산자에 적절한 액세스 권한이 있는지 확인합니다.
* 관리 연산자 사용을 피하고 관리 그룹에 너무 많은 연산자가 없도록 하십시오.

:arrow_upper_right:[Adobe Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management.html?lang=en#webapp-operator)에서 자세한 내용

## 코딩 지침

Adobe Campaign(워크플로우, Javascript, JSSP 등)에서 개발하는 경우 항상 다음 지침을 따르십시오.

* 스크립팅:SQL 문을 사용하지 말고 문자열 연결 대신 매개 변수가 있는 함수를 사용하십시오. 허용 목록에 사용할 SQL 함수를 추가하면 SQL 주입을 방지할 수 있습니다.

* 데이터 모델의 보안:명명된 권한을 사용하여 연산자 작업을 제한하고 시스템 필터를 추가합니다(sysFilter).

* 웹 애플리케이션에 캡처를 추가합니다.공개 랜딩 페이지와 구독 페이지에 captchas를 추가합니다.

:arrow_upper_right:[Adobe Campaign Classic 설명서](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=en#installing-campaign-classic)에서 자세한 내용
