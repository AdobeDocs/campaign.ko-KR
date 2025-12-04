---
title: 추가 작업
description: 추가 작업을 수행하는 방법에 대해 자세히 알아보기
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 7db25b8d-a6f1-4151-bf37-c47e9991ae48
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 1%

---

# 추가 작업 {#additional-operations}

## 정렬 {#sorting}

정렬은 기본적으로 오름차순으로 사용할 수 있습니다. 내림차순으로 정렬하려면 **%20desc**&#x200B;을(를) **_order** 매개 변수 값에 추가하십시오.

필드를 정렬할 수 있는지 확인하려면 리소스 메타데이터에 &quot;정렬 가능한&quot; 매개 변수를 확인하십시오. 이 작업에 대한 자세한 정보는 [이 섹션](metadata-mechanism.md)을 참조하십시오.

<br/>

***샘플 요청***

* 알파벳순으로 정렬된 데이터베이스에서 이메일을 검색하기 위한 샘플 GET 요청.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  요청에 대한 응답입니다.

  ```
  {
  "content": [
      "adam@email.com",
      "allison.durance@example.com",
      "amy.dakota@mail.com",
      "andrea.johnson@mail.com",
      ...
  ]
  ...
  }
  ```

* 데이터베이스에서 이메일을 내림차순으로 검색하기 위한 샘플 GET 요청입니다.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  요청에 대한 응답입니다.

  ```
  {
  "content": [
      "tombinder@example.com",
      "tombinder@example.com",
      "timross@example.com",
      "john.smith@example.com",
      ...
  ]
  }
  ```

## 필터링 {#filtering}

### 필터 메타데이터 검색 중

필터는 각 리소스에 사용할 수 있습니다. 리소스와 연결된 필터를 식별하려면 리소스 메타데이터에 대해 GET 요청을 수행해야 합니다. 이 요청은 주어진 리소스에 대해 모든 필터가 정의된 URL을 반환합니다. 메타데이터에 대한 자세한 정보는 [이 섹션](metadata-mechanism.md)을 참조하세요.

필터의 메타데이터를 식별하고 사용 방법을 결정하려면 이전에 반환된 URL에 대해 GET 요청을 수행해야 합니다.

<br/>

***샘플 요청***

아래의 샘플 페이로드는 &quot;profile&quot; 리소스에 대한 &quot;byText&quot; 필터 메타데이터를 검색하는 방법을 보여 줍니다. 먼저 &quot;프로필&quot; 리소스 메타다에서 GET 요청을 수행합니다.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

필터가 설명된 URL을 반환합니다.

```
{
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>/filters/"
    }
  }
```

URL에서 GET 요청을 수행합니다. 프로필 리소스에 대한 필터 목록을 반환하고 각 필터에 연결된 메타데이터를 반환합니다.

```
{
"birthday": {
        "PKey": "@FL-CbDFXbnHbXcVpeCGWL46VXJLn1LqxLMPagt2vz8sCxQ52lvB15KiUaxXkxJYQw-tZXYrgUWG6K8QcB4gxVY9RKoba5bRFY3294YFshDmorRr8",
        "category": "0150_profile",
        "condition": ...,
        "data": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/birthday?type=$value&precision=$value&operator=$value&day=$value&month=$value&includeStart=$value&endDay=$value&endMonth=$value&includeEnd=$value&relativeValue=$value&nextUnitsValue=$value&previousUnitsValue=$value",
        "formType": "webPage",
        "fragmentName": "",
        "label": "Birthday",
}
```

### 필터 메타데이터 구조

각 필터에 대해 동일한 메타데이터 구조를 사용할 수 있습니다.

* **@formType** 및 **@webPage** 필드는 기술 필드입니다.
* **data** 필드에 필터 사용 방법에 대한 샘플이 제공됩니다.
* **metadata** 노드는 필터 매개 변수를 설명합니다.
* **condition** 노드는 필터의 용도를 설명합니다. 메타데이터 노드에 설명된 필터 매개 변수는 필터 조건을 만드는 데 사용됩니다. 각 필터 조건에 대해 **enabledIf**&#x200B;이(가) true이면 **expr**&#x200B;이(가) 적용됩니다.

<br/>

필터 메타데이터 구조 샘플:

```
"byText": {
        "PKey": "...",
        "category": "99_none",
        "condition": ...,
        "data": "/profileAndServices/profile/byText?text=$value",
        "formType": "none",
        "fragmentName": "",
        "label": "By name or email",
    }
```

### 필터 사용

필터링은 다음 요청으로 수행됩니다.

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/by<filterName>?<filterParam>=<filterValue>`

단일 요청에서 여러 필터를 결합할 수 있습니다.

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/<filter1name>/<filter2name>?<filter1param>=<filter1value>&<filter2param>=<filter2value>`

<br/>

***샘플 요청***

* &quot;email&quot; 유형의 &quot;service&quot; 리소스를 검색하기 위한 샘플 GET 요청.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  요청에 대한 응답입니다.

  ```
  {
      "content": [
          {
              "PKey": "<PKEY>",
              "created": "2019-09-25 23:20:35.000Z",
              "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/@I_FIiDush4OQPc0mbOVR9USoh36Tt5CsD35lATvQjdWlXrYc0lFkvle2XIwZUbD8GqTVvSp8AfWFUvjkGMe1fPe5nok",
              "label": "Marketing Newsletter",
              "lastModified": "2019-09-25 23:20:35.000Z",
              "limitedDuration": false,
              "messageType": "email",
              "mode": "newsletter",
              ...
          },
          ...
      ],
      ...
  }
  ```

* 에 &quot;Doe&quot;가 포함된 &quot;profile&quot; 리소스를 검색하기 위한 샘플 GET 요청
이메일 또는 성 필드(byText 필터는 이메일 및 성 필드를 모두 검색합니다).

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Doe \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  요청에 대한 응답입니다.

  ```
  {
      "content": [
          {
              "PKey": "<PKEY>",
              "firstName": "John",
              "lastName":"Doe",
              "birthDate": "1980-10-24",
              ...
          }
          ...
      ],
      ...
  }
  ```

* 유형이 &quot;email&quot;이고 레이블이 &quot;sport&quot;인 서비스 리소스를 검색하기 위한 샘플 GET 요청입니다.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/byText?channel=email&text=sport \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  요청에 대한 응답입니다.

  ```
  {
      "content": [
          {
              "PKey": "<PKEY>",
              "created": "2019-09-26 09:36:01.014Z",
              "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
              "label": "sport",
              "lastModified": "2019-09-26 09:36:01.014Z",
              "limitedDuration": false,
              "messageType": "email",
              "mode": "newsletter",
              "name": "SVC13",
              ...
          }
      ],
      ...
  }
  ```

### 사용자 정의 필터

사용자 지정 필터를 사용하려면 Adobe Campaign Standard 인터페이스에서 필터를 만들고 사용자 지정해야 합니다. 그러면 사용자 지정 필터의 비헤이비어는 기본 제공 필터와 동일합니다.

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

자세한 내용은 Campaign Standard 설명서를 참조하십시오.

* [필터 정의를 구성하는 중](https://helpx.adobe.com/kr/campaign/standard/developing/using/configuring-filter-definition.html).
* [사용 사례: 복합 식별 키를 사용하여 리소스를 호출합니다](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/adding-or-extending-a-resource/uc-calling-resource-id-key.html?lang=ko).

<br/>

***샘플 요청***

트랜잭션 금액이 100$ 이상인 &quot;프로필&quot; 리소스를 검색하기 위한 샘플 GET 요청. Adobe Campaign Standard 인터페이스에서 &quot;byAmount&quot; 필터를 처음 정의하고 &quot;Transaction&quot; 사용자 지정 테이블에 연결했습니다.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byAmount?amount_parameter=100 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!--
Response to the request.

```

{
    "content": [
        {
            "PKey": "<PKEY>",
            "builtIn": false,
            "created": "2019-09-26 09:36:01.014Z",
            "desc": "",
            "end": "",
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
            ...
        }
    ],
}

```

-->

<!-- exemple à vérifier de bout en bout-->

<!--+category = query editor
privacy ?
displayFOrmat ?
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
-->





<!--
 if link ou collection.* resName +
* resTarget tout ca, ca va ensemble : le système de lien, resTarget va donner la ressource targetée par le lien. type
resType = type technique (long..) resType = link alors unbound='false' ou 'true'
If type = enumeration alors champ "values" rajouté et les valeurs sont dans values
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
ail faut que la valeur poster soit conforme ,elle doit valider la dataPolicy . La dataPolicy peut soit controler la valeur (email invalide), soit transformé (cas du smartCase par exemple)
type dans les metadata = type de haut-niveau (nombre, text)
-->

## 카운팅 {#counting}

Adobe Campaign REST API는 요청의 레코드 수를 카운트할 수 있습니다. 이렇게 하려면 **count** 노드에서 반환된 URL을 사용합니다.

<br/>

***샘플 요청***

&quot;sms&quot;와 동일한 **messageType** 값이 있는 모든 서비스를 계산하려면 **byChannel** 필터로 GET 요청을 수행하십시오.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=sms \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

필터에 해당하는 서비스를 반환합니다.

```
{
    "content": [
        {
            ...
            "messageType": "sms",
            "mode": "newsletter",
            "name": "SVC6",
            ...
        },
        ...
    ],
    "count": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/_count?channel=sms&_lineStart=@iKTZ2q3IiSEDqZ5Nw1vdoGnQCqF-8DAUJRaVwR9obqqTxhMy"
    },
    "serverSidePagination": true
}
```

**count** 노드의 URL에서 GET 요청을 수행하여 결과 수를 검색합니다.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/_count?channel=sms&_lineStart=@iKTZ2q3IiSEDqZ5Nw1vdoGnQCqF-8DAUJRaVwR9obqqTxhMy \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

레코드 수를 반환합니다.

```
{
    "count": 26
}
```

## 쪽 매기기 {#pagination}

기본적으로 25개의 리소스가 목록에 로드됩니다.

**_lineCount** 매개 변수를 사용하면 응답에 나열된 리소스 수를 제한할 수 있습니다.  그런 다음 **next** 노드를 사용하여 다음 결과를 표시할 수 있습니다.

>[!NOTE]
>
>페이지 매김 요청을 수행하려면 항상 **next** 노드에서 반환된 URL 값을 사용하십시오.
>
>**_lineStart** 요청은 계산되며 항상 **next** 노드에 반환된 URL 내에서 사용해야 합니다.

<br/>

***샘플 요청***

프로필 리소스의 레코드 1개를 표시하는 샘플 GET 요청.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

페이지 매김을 수행할 **next** 노드를 사용한 요청에 대한 응답입니다.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "John",
            "lastName":"Doe",
            "birthDate": "1980-10-24",
            ...
        }
    ],
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
        lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
    }
    ...
}
```

기본적으로 **next** 노드는 많은 양의 데이터가 있는 테이블과 상호 작용할 때 사용할 수 없습니다. 페이지 매김을 수행하려면 호출 URL에 **_forcePagination=true** 매개 변수를 추가해야 합니다.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>테이블 크기가 큰 것으로 간주되는 레코드 수는 Campaign Standard **XtkBigTableThreshold** 옵션에 정의되어 있습니다. 기본값은 100,000 레코드입니다.
