---
title: API 문제 해결
description: Campaign Standard API와 관련된 일반적인 문제에 대해 자세히 알아보기
role: Data Engineer
level: Experienced
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---

# API 문제 해결 {#troubleshooting}

* **Adobe.io 콘솔로 이동하면 다음 오류가 발생합니다. &quot;Adobe I/O 콘솔은 엔터프라이즈 계정의 일부 구성원만 사용할 수 있습니다. 액세스 권한이 있다고 생각되면 시스템 관리자에게 문의하십시오.&quot;**

관리자는 조직의 API 키만 만들 수 있습니다. 이 메시지가 표시되고 API 키를 만들려고 하며 조직의 관리자 중 한 명에게 물어보려는 경우.

* **Adobe.io에 대한 요청을 수행하면 {&quot;error_code&quot;:&quot;403023&quot;,&quot;message&quot;:&quot;프로필이 유효하지 않습니다&quot;}**

즉, 특정 Campaign 제품의 IMS 프로비저닝에 문제가 있습니다. IMS 팀에서 이를 해결해야 합니다.

자세한 내용을 보려면 토큰으로 IMS API를 호출하여 IMS 프로필의 모양을 확인할 수 있습니다. 요청을 라우팅하려면 organization_id가 Adobe.io에 대해 URL에 입력한 것과 동일한 prodCtx가 있어야 합니다.
누락된 경우 IMS 프로비저닝을 수정해야 합니다.

```
-X GET https://mc.adobe.io/{ORGANIZATION}/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

다음 오류를 반환합니다.

```
{"error_code":"403023","message":"Profile is not valid"}
```

이 요청을 사용하여 IMS 프로필을 확인합니다.

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

응답에서 ORGANIZATION_ID 값은 첫 번째 GET 요청에서 동일해야 합니다.

```
{
  "countryCode": "FR",
  "mrktPermEmail": null,
  "projectedProductContext": [
    {
    "prodCtx": {
      "statusCode": "ACTIVE",
      "ident": "ZQ9FRQK7BF09YXAESFY9DDQP1G",
      "modDts": 1448307260000,
      "organization_id": "actest",
      "owningEntity": "6096892F54B5819E0A4C98A2@AdobeOrg",
      "serviceCode": "dma_tartan",
      "label": "Adobe Marketing Cloud",
      "serviceLevel": "standard",
      "createDts": 1421181343000,
      "deal_id": " "
      }
    }
  ]
}
```

* **Adobe.io에 대한 요청을 하면 {&quot;code&quot;:500, &quot;message&quot;:&quot;죄송합니다. 문제가 발생했습니다. URI를 확인하고 다시 시도하십시오.&quot;}**

Adobe.io에서 잘못된 URI를 선언합니다. 요청하는 URI가 유효하지 않을 가능성이 높습니다. Adobe.io에서 Campaign 서비스를 선택하면 가능한 organization_ids 목록이 있는 선택기가 표시됩니다. 선택한 항목이 URL에 입력한 내용인지 확인해야 합니다.

* **Adobe.io에 대한 요청을 수행하면 {&quot;error_code&quot;:&quot;401013&quot;,&quot;message&quot;:&quot;Oauth 토큰이 유효하지 않습니다&quot;}**

토큰이 잘못되었거나(토큰 생성에 사용한 부적절한 IMS 호출) 토큰이 만료되었습니다.

* **만든 후 내 프로필이 표시되지 않음**

인스턴스 구성에 따라 만들어진 프로필을 **orgUnit**&#x200B;에 연결해야 합니다. 생성 시 이 필드를 추가하는 방법을 이해하려면 [이 섹션](creating-profiles-api.md)을 참조하세요.

<!-- * (error duplicate key : quand tu crées un profile qui existe déjà , il faut faire un patch pour updater le profile plutôt qu'un POST)

With Curl
List all profiles

Create a profile

Update the mobilePhone attribute of a profile

API Calls on Service

GET the list of services

-->

<!--

How to find and use a filter?
Error codes:

* PAtch sur Age = message d'erreur :
500
Cannot update the 'age' property that is read-only
'age' property is not valid for the 'profile' resource.
-->

<!--
How to filter a list of subscribed profiles with available profile filters ? by date (by les filtres dispo sur la ressource) ?

Pattern classique :

recupérer la liste des subscriptions filtrées d'un profile
1) get sur profile
2) recup PKey
3) get sur PKey
4) get sur href des subscriptions

Comment savoir quel filtre appliquer ?

1) get sur metadata de profile
2) retourne description de la collection subscription
3) get sur la valeur du champ resTarget
4) get sur le href dans filters
5) retourne les filtres applicables sur l'url des data.

-->
