---
title: 기술 사용자를 Adobe Developer 콘솔로 마이그레이션
description: Adobe Developer 콘솔에서 Campaign 기술 연산자를 기술 계정으로 마이그레이션하는 방법을 알아봅니다
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 0%

---

# Campaign 기술 운영자를 Adobe Developer 콘솔로 마이그레이션 {#migrate-tech-users-to-ims}

Campaign v8.5부터 Campaign v8에 대한 인증 프로세스가 개선되고 있습니다. 기술 운영자는 [Adobe Identity Management 시스템(IMS)](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"} Campaign에 연결합니다. 기술 운영자는 API 통합을 위해 명시적으로 생성된 Campaign 사용자 프로필입니다. 이 문서에서는 Adobe Developer 콘솔에서 기술 연산자를 기술 계정으로 마이그레이션하는 데 필요한 단계에 대해 자세히 설명합니다.

## 변경 사항{#ims-changes}

Campaign 일반 사용자는 이미 IMS(Identity Management System) Adobe을 통해 Adobe ID을 사용하여 Adobe Campaign 콘솔에 연결합니다. 보안 및 인증 프로세스를 강화하기 위한 노력의 일환으로 이제 Adobe Campaign 클라이언트 애플리케이션이 IMS 기술 계정 토큰을 사용하여 Campaign API를 직접 호출합니다.

에서 새 서버 간 인증 프로세스에 대해 자세히 알아봅니다. [Adobe Developer 콘솔 설명서](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

이 변경 사항은 Campaign v8.5부터 적용되며 다음과 같습니다. **필수** campaign v8.6을 시작하는 중입니다.


## 영향을 받습니까?{#ims-impacts}

Campaign API를 사용하는 경우 아래에 자세히 설명된 대로 기술 연산자를 Adobe Developer 콘솔로 마이그레이션해야 합니다.

## 마이그레이션 방법{#ims-migration-procedure}

### 전제 조건{#ims-migration-prerequisites}

마이그레이션 프로세스를 시작하기 전에 Adobe 기술 팀이 기존 운영자 그룹과 IMS(Identity Management System) Adobe에 대한 명명된 권한을 마이그레이션할 수 있도록 Adobe 담당자에게 문의해야 합니다.

### 1단계 - Adobe Developer 콘솔에서 Campaign 프로젝트 만들기/업데이트{#ims-migration-step-1}

통합은 의 일부로 만들어집니다. **프로젝트** Adobe Developer 콘솔 내에서. 의 프로젝트에 대해 자세히 알아보기 [Adobe Developer 콘솔 설명서](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.

Campaign v8 사용자는 이미 Adobe Developer 콘솔에 프로젝트가 있어야 합니다. 그렇지 않은 경우 프로젝트를 만들어야 합니다. 프로젝트를 만드는 단계는 자세히 설명되어 있습니다 [Adobe Developer 콘솔 설명서에서](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"}.

Campaign 프로젝트에 액세스할 수 있으면 API, Adobe Campaign 및 I/O 관리 API를 포함한 서비스를 추가할 수 있습니다. 이 마이그레이션의 경우 프로젝트에서 아래 API를 추가해야 합니다. **I/O 관리 API** 및 **Adobe Campaign**.

![](assets/do-not-localize/ims-products-and-services.png)


### 2단계 - 서버 간 인증을 사용하여 프로젝트에 API 추가{#ims-migration-step-2}

Adobe Developer 콘솔에서 프로젝트가 생성되면 서버 간 인증을 사용하는 API를 추가하십시오. 에서 OAuth 서버 간 자격 증명을 설정하는 방법에 대해 알아봅니다. [Adobe Developer 콘솔 설명서](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}.

API가 성공적으로 연결되면 클라이언트 ID 및 클라이언트 암호를 포함하여 새로 생성된 자격 증명에 액세스하고 액세스 토큰을 생성할 수 있습니다.

### 3단계 - 프로젝트에 제품 프로필 추가{#ims-migration-step-3}

이제 아래에 자세히 설명된 대로 Campaign 제품 프로필을 프로젝트에 추가할 수 있습니다.

1. Adobe Campaign API를 엽니다.
1. 다음을 클릭합니다. **제품 프로필 편집** 단추

   ![](assets/do-not-localize/ims-edit-api.png)

1. 모든 관련 제품 프로필을 API(예: &#39;messagecenter&#39;)에 할당하고 변경 사항을 저장합니다.
1. 다음으로 이동 **자격 증명 세부 정보** 프로젝트의 탭을 복사한 다음 **기술 계정 이메일** 값.

### 4단계 - 클라이언트 콘솔에서 기술 연산자 업데이트 {#ims-migration-step-4}


이 단계는 (운영자의 그룹을 통하지 않고) 이 운영자에 대해 특정 폴더 권한 또는 명명된 권한이 정의된 경우에만 필요합니다.

이제 Adobe Campaign 클라이언트 콘솔에서 새로 만든 기술 연산자를 업데이트해야 합니다. 기존 기술 운영자 폴더 권한을 새 기술 운영자에게 적용해야 합니다.
이 연산자를 업데이트하려면 다음 단계를 수행합니다.

1. Campaign 클라이언트 콘솔 탐색기에서 **관리 > 액세스 관리 > 연산자**.
1. API에 사용되는 기존 기술 운영자에 액세스합니다.
1. 폴더 권한을 찾아 권한을 확인합니다.
1. 새로 만든 기술 운영자에게 동일한 권한을 적용합니다. 이 운영자의 이메일은 **기술 계정 이메일** 값이 이전에 복사되었습니다.
1. 변경 내용을 저장합니다.


>[!CAUTION]
>
>새 기술 운영자가 Campaign 클라이언트 콘솔에 추가할 API 호출을 하나 이상 수행해야 합니다.
>

<!--

>[!CAUTION]
>
>After updating the authentication type for the technical operator, all API integrations with this technical operator will stop working. You must [update your API integrations](#ims-migration-step-6). 

To update the technical operator authentication mode to IMS, follow these steps:

1. From Campaign Client Console explorer, browse to the **Administration > Access Management > Operators**.
1. Edit the existing technical operator used for APIs.
1. Replace the **Name (login)** of this technical operator by the technical account email retrieved earlier.
1. Browse to the **Edit** button on the top left beside **File**, and select **Edit the XML source**.
1. Update the authentication mode to `ims`, as follows:

    ```javascript
    <operator 
    ...
        <access authenticationType="ims" ...
        ...
        </access>
    ...
    </operator>
    ```

1. Save your changes.

You can also update the technical operator programmatically, using SQL scripts or Campaign APIs. These modes help you automate the steps which update operator's name with associated Technical account email address and/or authentication type. 

* Use the following **SQL Script** to replace operator's name with associated email:

    ```sql
    UPDATE xtkoperator
    SET sauthenticationtype = 'ims',
            sname = '{email}'
    WHERE sname = '{name}' AND itype = 0;
    ```

* Use the following `queryDef.ExecuteQuery` **Campaign API** to fetch id of an operator for given technical operator:

    ```javascript
    <?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
        <soap:Body>
            <ExecuteQuery xmlns="urn:xtk:queryDef">
                <sessiontoken>{session_token}</sessiontoken>
                <entity>
                    <queryDef schema="xtk:operator" operation="select">
                        <select>
                            <node expr="@id"/>
                        </select>
                        <where>
                            <condition expr="@name='{name}'"/>
                            <condition expr="@type=0"/>
                        </where>
                    </queryDef>
                </entity>
            </ExecuteQuery>
        </soap:Body>
    </soap:Envelope>
    ```

* Use the following `session.Write` **Campaign API** to update name with given technical account email address:

    ```javascript
    <?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
        <soap:Body>
            <Write xmlns="urn:xtk:session">
                <sessiontoken>{session_token}</sessiontoken>
                <domDoc xsi:type='ns:Element' SOAP-ENV:encodingStyle='http://xml.apache.org/xml-soap/literalxml'>
                    <operator _operation="update" id="{id}" name="{email}" xtkschema="xtk:operator">
                        <access authenticationType="ims" />
                    </operator>
                </domDoc>
            </Write>
        </soap:Body>
    </soap:Envelope>
    ```
-->

### 5단계 - 구성 유효성 검사 {#ims-migration-step-5}

연결을 시도하려면 다음에서 자세히 설명하는 단계를 수행합니다. [Adobe Developer 콘솔 자격 증명 안내서](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} 액세스 토큰을 생성하고 제공된 샘플 cURL 명령을 복사합니다.


### 6단계 - 서드파티 API 통합 업데이트 {#ims-migration-step-6}

타사 시스템과의 API 통합을 업데이트해야 합니다.

원활한 통합을 위한 샘플 코드를 포함하여 API 통합 단계에 대한 자세한 내용은 을 참조하십시오. [Adobe Developer 콘솔 인증 설명서](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.


### 7단계 - 이전 기술 연산자 제거 {#ims-migration-step-7}


기술 계정 사용자와 모든 API/사용자 정의 코드 통합 마이그레이션 후. Campaign 클라이언트 콘솔에서 이전 기술 연산자를 삭제할 수 있습니다.

### Soap 호출 샘플{#ims-migration-samples}

마이그레이션 프로세스가 달성되고 유효성이 확인되면 Soap 호출이 다음과 같이 업데이트됩니다.

* 마이그레이션 전

  ```sql
  POST /nl/jsp/soaprouter.jsp HTTP/1.1
  Host: localhost:8080
  Content-Type: application/soap+xml;
  SOAPAction: "nms:rtEvent#PushEvent"
  charset=utf-8
  
  <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
  <soapenv:Header/>
  <soapenv:Body>
      <urn:PushEvent>
          <urn:sessiontoken>SESSION_TOKEN</urn:sessiontoken>
          <urn:domEvent>
              <!--You may enter ANY elements at this point-->
              <rtEvent type="type" email="name@domain.com"/>
          </urn:domEvent>
      </urn:PushEvent>
  </soapenv:Body>
  </soapenv:Envelope>
  ```

* 마이그레이션 후

  ```sql
  POST /nl/jsp/soaprouter.jsp HTTP/1.1
  Host: localhost:8080
  Content-Type: application/soap+xml;
  SOAPAction: "nms:rtEvent#PushEvent"
  charset=utf-8
  Authorization: Bearer <IMS_Technical_Token_Token>
  
  <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
  <soapenv:Header/>
  <soapenv:Body>
      <urn:PushEvent>
          <urn:sessiontoken></urn:sessiontoken>
          <urn:domEvent>
              <!--You may enter ANY elements at this point-->
              <rtEvent type="type" email="name@domain.com"/>
          </urn:domEvent>
      </urn:PushEvent>
  </soapenv:Body>
  </soapenv:Envelope>
  ```
