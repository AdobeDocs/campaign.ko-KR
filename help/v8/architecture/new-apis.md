---
title: 새 Campaign v8 API
description: 새 Campaign v8 API
feature: API, FFDA
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: dd822f88-b27d-4944-879c-087f68e79825
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 2%

---

# 특정 FFDA 캠페인 API{#gs-new-api}

의 컨텍스트에서 [엔터프라이즈(FFDA) 배포](enterprise-deployment.md), Campaign v8에는 Campaign 로컬 데이터베이스와 Cloud 데이터베이스 간의 데이터를 관리하기 위한 두 개의 특정 API가 포함되어 있습니다. 이를 사용하기 위한 사전 요구 사항은 스키마에서 스테이징 메커니즘을 활성화하는 것입니다. [자세히 알아보기](staging.md)

* 수집 API: **xtk.session.ingest**

   이 API는 데이터 삽입에만 사용됩니다. [자세히 알아보기](#data-insert-api)

* 데이터 업데이트/삭제 API: **xtk.session.ingestExt**

   이 API는 데이터를 업데이트하거나 삭제하는 데 사용됩니다. [자세히 알아보기](#data-update-api)

전용 기본 제공 워크플로우는 클라우드 데이터베이스의 데이터를 동기화합니다.

## 데이터 삽입{#data-insert-api}

다음 **xtk.session.ingest** API는 데이터 삽입에만 사용됩니다. 업데이트/삭제가 없습니다.

### 조정 없이 삽입{#insert-no-reconciliation}

**워크플로우에서**

다음 코드를 **Javascript 코드** 조정 없이 클라우드 데이터베이스에 데이터를 삽입하는 활동:

```
var xmlStagingSampleTable = <sampleTableStg
                                testcol1="testValue1"
                                testcol2="testValue2"
                                xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

워크플로우가 실행되면 스테이징 테이블이 예상대로 제공됩니다.

**SOAP 호출에서**

1. 인증 토큰을 가져옵니다.
1. API를 트리거합니다. 페이로드는 다음과 같습니다.

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:Ingest>
           <urn:sessiontoken>___xxxxxxx-xxxx-xxx-xxx-xxxxxxxxxxx</urn:sessiontoken>
           <urn:domDoc>
               <sampleTableStg
                   testcol1="Test Value 1 (from SOAP)"
                   testcol2="Test Value 2 (from SOAP)"
                   xtkschema="dem:sampleTableStg">
               </sampleTableStg>
           </urn:domDoc>
       </urn:Ingest>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

1. UUID가 SOAP 응답으로 다시 전송됩니다.

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
           <pstrSUuids xsi:type="xsd:string">e1e7c8b3-6f79-44da-a72d-49ed0f73db2c</pstrSUuids>
       </IngestResponse>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

따라서 스테이징 테이블은 예상대로 제공됩니다.

![](assets/no-reconciliation.png)

### 조정을 사용하여 삽입

**워크플로우에서**

다음 코드를 **Javascript 코드** 조정을 사용하여 클라우드 데이터베이스에 데이터를 삽입하는 활동:

```
var xmlStagingSampleTable = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue1"
                              testcol2="testValue2"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;         
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

워크플로우가 실행되면 스테이징 테이블이 예상대로 제공됩니다.

![](assets/with-reconciliation.png)


**SOAP 호출에서**

1. 인증 토큰을 가져옵니다.
1. API를 트리거합니다. 페이로드는 다음과 같습니다.

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
     <urn:Ingest>
        <urn:sessiontoken>___5e71f4bf-d38a-4ba8-ac15-35a958f7f138</urn:sessiontoken>
        <urn:domDoc>
           <sampleTableStg  _key="@id" id="ABDCD321"
                testcol1="Test Value 1 (from SOAP)"
                testcol2="Test Value 2 (from SOAP)"
                xtkschema="dem:sampleTableStg">
            </sampleTableStg>
        </urn:domDoc>
     </urn:Ingest>
    </soapenv:Body>
   </soapenv:Envelope>
   ```

1. 이 경우 UUID는 페이로드에서 제공되었으므로 응답으로 다시 제공되지 않습니다. 응답은 다음과 같습니다.

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
           <pstrSUuids xsi:type="xsd:string"/>
       </IngestResponse>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

따라서 스테이징 테이블은 예상대로 제공됩니다.

## 데이터 업데이트 또는 삭제{#data-update-api}

다음 **xtk.session.IngestExt** 데이터 업데이트/삭제에 대해 API가 최적화되었습니다. 삽입만 하려면 **xtk.session.ingest**. 레코드 키가 스테이징 테이블에 없는지 여부를 삽입하는 중입니다.

### 삽입/업데이트

**워크플로우에서**

다음 코드를 **Javascript 코드** 활동을 통해 클라우드 데이터베이스의 데이터를 업데이트합니다.

```
var xmlStagingRecipient = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue A (updated)"
                              testcol2="testValue B (updated)"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
xtk.session.IngestExt(xmlStagingRecipient);
```

워크플로우가 실행되면 스테이징 테이블이 예상대로 업데이트됩니다.

![](assets/updated-data.png)

**SOAP 호출에서**

1. 인증 토큰을 가져옵니다.
1. API를 트리거합니다. 페이로드는 다음과 같습니다.

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:IngestExt>
           <urn:sessiontoken>___444cd168-a1e2-4fb6-a2a8-73be9f133489</urn:sessiontoken>
           <urn:domDoc>
           <sampleTableStg  _key="@id" id="ABDCD321"
                   testcol1="Test Value E (from SOAP)"
                   testcol2="Test Value F (from SOAP)"
                   xtkschema="dem:sampleTableStg">
               </sampleTableStg>
           </urn:domDoc>
       </urn:IngestExt>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

1. SOAP 응답은 다음과 같습니다.

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestExtResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default"/>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

따라서 스테이징 테이블은 예상대로 업데이트됩니다.

## 구독 관리 {#sub-apis}

Campaign의 구독 관리는 [이 페이지](../start/subscriptions.md).

구독 및 구독 취소 데이터는 [스테이징 메커니즘](staging.md) ( Campaign 로컬 데이터베이스)를 참조하십시오. 가입자 정보는 로컬 데이터베이스의 스테이징 테이블에 임시 저장되며 동기화 워크플로우는 로컬 데이터베이스에서 클라우드 데이터베이스로 이 데이터를 전송합니다. 따라서 구독 및 구독 취소 프로세스는 다음과 같습니다 **비동기**. 옵트인 및 옵트아웃 요청은 매 시간 특정 기술 워크플로우를 통해 처리됩니다. [자세히 알아보기](replication.md#tech-wf)


**관련 항목**

* [Campaign JSAPI](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html){target="_blank"}
