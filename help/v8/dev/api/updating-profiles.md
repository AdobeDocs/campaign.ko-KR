---
title: 프로필 업데이트
description: API를 사용하여 프로필을 업데이트하는 방법에 대해 자세히 알아보기
role: Data Engineer
level: Experienced
exl-id: fa3796ee-a00c-4d70-bf3d-e8d2099f1116
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%

---

# API를 사용하여 프로필 업데이트{#updating-profiles-api}

프로필 업데이트는 **PATCH** 요청으로 수행됩니다.

`https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

1. 첫 번째 단계는 **프로필을 검색**&#x200B;하는 것입니다.

1. 두 번째 요청에서는 페이로드에 완료된 정보가 있는 프로필에 대해 **PATCH 요청**&#x200B;을 수행합니다.

1. PATCH 요청이 프로필을 업데이트했는지 확인하기 위해 최종 GET 요청을 수행할 수 있습니다.

<br/>

***샘플 요청***

프로필 검색을 위한 샘플 GET 요청.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>\
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
            "firstName": "Amy",
            "lastName":"Dakota",
            "birthDate": "1980-10-24",
            ...
        }
    ]
}
```

PATCH에서 &quot;phone&quot; 속성을 업데이트하도록 요청합니다.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-d '{"phone":"3301020304"}'
```

업데이트된 프로필을 검색하기 위해 PKEY 및 URL을 반환합니다.

```
{
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs"
}
```
