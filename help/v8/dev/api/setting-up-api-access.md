---
title: API 액세스 설정
description: Campaign Standard API에 대한 액세스를 설정하는 방법을 알아봅니다.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 6%

---

# API 액세스 설정 {#setting-up-api-access}

Adobe Campaign Standard API 액세스는 아래 단계를 통해 설정됩니다. 이러한 각 단계는 [Adobe Developer 설명서](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)에 자세히 설명되어 있습니다.

>[!IMPORTANT]
>
>[Adobe Developer](https://developer.adobe.com/)에서 인증서를 관리하려면 조직에 대한 **시스템 관리자** 권한 또는 Admin Console의 [개발자 계정](https://helpx.adobe.com/kr/enterprise/using/manage-developers.html)이 있는지 확인하십시오.

1. **디지털 인증서가 있는지 확인**&#x200B;하거나 필요한 경우 만드십시오. 인증서와 함께 제공되는 공개 및 개인 키는 다음 단계에서 필요합니다.
1. **Adobe Developer**&#x200B;에서 [Adobe Campaign 서비스에 대한 새 통합을 만들고](https://developer.adobe.com/) 구성합니다. 그러면 자격 증명이 생성됩니다(API 키, 클라이언트 암호...).
1. **다음**&#x200B;구현 단계[에 따라 OAuth 서버 간 자격 증명을 만듭니다](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)

   >[!IMPORTANT]
   >
   >현재 JWT(JSON 웹 토큰)의 지원 종료를 준비하고 있으며, 이를 OAuth로 대체하는 과정이 진행 중입니다. 전환은 Campaign의 예정된 릴리스 내에서 점진적으로 수행됩니다. 서비스 계정(JWT) 자격 증명이 더 이상 사용되지 않는 것으로 표시되었으며, 2025년 1월 27일까지 계속 작동합니다. 따라서 2025년 1월 27일 이전에 새 OAuth 서버 간 자격 증명을 사용하려면 애플리케이션이나 통합을 마이그레이션해야 합니다. OAuth 인증이 선호됩니다. 다음 페이지에서 JWT 인증에서 OAuth 인증으로 마이그레이션할 모든 요소를 찾을 수 있습니다.
   >* [마이그레이션](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)
   >* [구현](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)
   >* [사용 중단 JWT FAQ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)

보안 서비스 간 Adobe I/O API 세션을 설정하려면 Adobe 서비스에 대한 모든 요청에서 아래 정보를 인증 헤더에 포함해야 합니다.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;조직>**: 개인 조직 ID이며, Adobe에서 각 인스턴스에 대해 하나의 조직 ID를 제공합니다.

   * &lt;조직> : 프로덕션 인스턴스,
   * &lt;ORGANIZATION-mkt-stage>: 단계 인스턴스입니다.

  조직 ID 값을 얻으려면 관리자 또는 Adobe 기술 담당자에게 문의하십시오. 라이선스 목록에서 새 통합을 만들 때 Adobe I/O에서 검색할 수도 있습니다(<a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Adobe Developer 설명서</a> 참조).

* **&lt;ACCESS_TOKEN>**: POST 요청을 통해 JSON 웹 토큰을 교환할 때 검색된 개인 액세스 토큰입니다.

* **&lt;API_KEY>**: 개인 API 키. Adobe Campaign 서비스에 대한 새 통합을 만든 후 Adobe I/O에서 제공합니다.

  ![대체 텍스트](assets/tenant.png)

## 문제 해결

AdobeIO 통합 중에 다음 오류가 나타나면

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


CNAME 매개 변수가 올바르게 생성되었는지 확인하려면 관리자 또는 Adobe 기술 담당자에게 문의하십시오.
