---
product: campaign
title: Technote - Adobe Campaign의 비동기 암호화 및 암호 해독
description: 기술 참고 사항 - Adobe Campaign의 비동기 암호화 및 암호 해독
hide: true
hidefromtoc: true
source-git-commit: 1d9d4111cde1e230220a04c8fd10a126116339ad
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---

# 기술 정보: Adobe Campaign의 비대칭 암호화 및 암호 해독 {#asymetric-encryption}

공개 키 암호화 또는 비대칭 암호는 관련 키 쌍을 사용하는 암호화 시스템의 필드입니다. 각 키 쌍은 **공개 키**&#x200B;와 해당 **개인 키**(으)로 구성됩니다.

* **공개 키**&#x200B;는 공개적으로 공유되며 데이터를 암호화하는 데 사용됩니다.

* **개인 키**&#x200B;은(는) 비밀로 유지되며 데이터 암호를 해독하는 데 사용됩니다.

이 접근 방식은 누군가 공개 키를 가지고 있더라도 개인 키 없이 메시지를 해독할 수 없도록 합니다. 기밀 유지, 인증 및 무결성과 같은 주요 보안 기능을 제공합니다.

Adobe Campaign v8.8.3부터 암호화 및 암호 해독을 위해 두 개의 새로운 Javascript 함수가 추가되고 있습니다.

* 공개 키를 사용한 암호화: `rsaPublicEncrypt(data, base64EncodedPublicKey, useOAEPpadding)`

* 개인 키를 사용한 암호 해독: `rsaPrivateDecrypt(encryptedData, base64EncodedPrivateKey, useOAEPpadding)`


예:

```Java
// Encryption with PKCS#1 v1.5 padding (default)
var encrypted = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t..." // Base64 encoded public key
);
 
// Encryption with OAEP padding
var encryptedOAEP = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t...", // Base64 encoded public key
    true
);
 
// Decryption
var decrypted = rsaPrivateDecrypt(
    encrypted,
    "LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVkt..." // Base64 encoded private key
);
```

**추가 리소스**

* [시작 [!DNL Campaign] API](https://experienceleague.adobe.com/ko/docs/campaign/campaign-v8/developer/api){target="_blank"}
* [Campaign JSAPI 설명서](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=ko){target="_blank"}
