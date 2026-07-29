---
title: API를 사용하여 프로필 만들기
description: API를 사용하여 프로필을 만드는 방법에 대해 자세히 알아보십시오.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
TQID: https://experienceleague.adobe.com/ufHL-Vr8NjFpJVES61uhuTl8Xh3DqUsKmwyDkvm7J-g
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 112
ht-degree: 0%

---

# API를 사용하여 프로필 만들기 {#creating-profiles-api}

프로필 리소스에서 **POST** 요청을 사용하여 프로필을 만듭니다.

>[!CAUTION]
>
><b>orgUnit</b>을(를) 생성된 프로필에 연결하려면 이 필드로 프로필 리소스를 확장하고 확장을 게시한 후 <b>ProfileAndServicesExt</b> 끝점에서 POST 요청을 수행해야 합니다.
>
>프로필의 리소스 확장에 대한 자세한 내용은 <a href="https://helpx.adobe.com/kr/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Campaign 설명서</a>를 참조하세요.

<br/>

***샘플 요청***

이메일 &quot;john.doe@mail.com&quot;을 사용하여 프로필을 만들기 위한 샘플 POST 요청.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

&quot;john.doe@mail.com&quot; 이메일 주소를 사용하여 새로 만든 프로필을 반환합니다.

```
{
    "PKey": "<PKEY>",
    "firstName": "John",
    "lastName":"Doe",
    "birthDate": "1980-10-24",
    "email": "john.doe@mail.com",
    ...
}
```
