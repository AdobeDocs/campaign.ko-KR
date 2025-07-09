---
title: 권장 사항 및 제한 사항
description: Campaign v8 REST API로 마이그레이션할 때의 권장 사항 및 제한 사항입니다.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
mini-toc-levels: 1
exl-id: 45acebb1-9325-4e26-8fe9-cc73f745d801
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 1%

---

# 권장 사항 및 제한 사항 {#limitations}

## 권한 및 보안 {#permissions}

### 제품 프로필 매핑

Campaign Standard에서는 할당된 제품 프로필과 관계없이 API에 대한 관리자 역할 액세스 권한이 부여되었습니다. Campaign v8에서는 Campaign Standard에서 Campaign v8 제품 프로필로의 매핑이 필요한 다양한 제품 프로필 세트를 도입했습니다.

마이그레이션을 수행하면 기존 또는 미리 만든 기술 계정에 두 개의 제품 프로필이 추가됩니다(트랜잭션 API에 액세스하기 위한 관리자 및 메시지 센터). 제품 프로필 매핑을 검토하고 관리자 제품 프로필을 기술 계정과 매핑하지 않으려는 경우 필요한 제품 프로필을 할당합니다.

### 임차인 ID

마이그레이션 후 향후 통합을 위해 이전 Campaign Standard 테넌트 ID를 대체하여 REST URL의 **Campaign v8 테넌트 ID**&#x200B;를 사용하는 것이 좋습니다.

### 키 사용

PKey 값 관리는 Campaign Standard과 Campaign v8에서 다릅니다. Campaign Standard과 함께 PKeys를 저장하는 경우 이전 API 호출에서 가져온 PKeys 또는 href를 사용하여 구현이 후속 API 호출을 동적으로 형성하는지 확인하십시오.

## 사용 가능한 API {#deprecated}

현재 아래에 나열된 REST API를 사용할 수 있습니다.

* **프로필**
* **서비스 및 구독**
* **사용자 정의 리소스**
* **워크플로**
* **트랜잭션 메시지**

>[!AVAILABILITY]
>
>지금은 **트랜잭션 메시지** REST API를 사용할 수 없습니다.
>
>아래에 나열된 REST API는 더 이상 사용되지 않으며 사용할 수 없습니다.
>* 마케팅 기록
>* 조직 단위
>* 개인 정보 보호 관리

## 필터링

* REST API 페이로드에서 필터를 사용하려면 Campaign v8에서 편집하고 페이로드에 사용할 이름을 제공해야 합니다. 이렇게 하려면 **[!UICONTROL Parameters]** 탭에서 필터의 추가 매개 변수에 액세스하고 **[!UICONTROL Filter name in REST API]** 필드에 원하는 이름을 입력합니다.

  ![](assets/api-filtering.png)


* 사용자 지정 필터를 사용하는 데 필요한 &quot;by&quot; 접두사는 더 이상 필요하지 않습니다. 필터 이름은 요청에 있는 그대로 사용해야 합니다.

  예:

  `GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/<customFilterName>?<customFilterparam>=<customFilterValue>`

## 삭제된 데이터베이스 필드

마이그레이션 도중 데이터베이스의 일부 필드가 삭제됩니다. 삭제된 필드를 사용할 때 REST API는 빈 값을 반환합니다. 앞으로 삭제된 모든 필드는 더 이상 사용되지 않으며 제거됩니다.

## 연결된 리소스가 있는 POST

다음 요청 본문 형식을 사용할 때 &quot;vehicleOwner&quot;는 &quot;nms:recipient&quot;에 대한 링크를 나타냅니다.

```
{
    "vehicleNumber": "20009",
    "vehicleName": "Model E",
    "vehicleOwner":{
        "firstName":"tester 11",
        "lastName":"Smith 11"
    }
}
```

링크 정보는 무시됩니다. 따라서 &quot;vehicleNumber&quot; 및 &quot;vehicleName&quot; 값만 포함된 &quot;cusVehicle&quot;에 새 레코드가 생성됩니다. 하지만 링크는 null로 유지되므로 &quot;vehicleOwner&quot;가 null로 설정됩니다.

Campaign v8에서 동일한 요청 본문 구조를 사용하고 &quot;차량&quot;이 프로필에 연결되어 있으면 오류가 발생합니다. 이 오류는 &quot;firstName&quot; 속성이 &quot;cusVehicle&quot;에 대해 유효한 것으로 인식되지 않기 때문에 발생합니다. 하지만 링크가 없는 속성만 구성하는 요청 본문은 문제 없이 작동합니다.

## PATCH 작업

* Campaign v8은 빈 요청 본문이 있는 PATCH을 지원하지 않습니다. 204 콘텐츠 없음 상태를 반환합니다.
* Campaign Standard은 스키마 내의 요소/특성에 대해 PATCH을 지원하지만, 위치에 대한 PATCH 작업은 Campaign v8에서 지원되지 않습니다. 위치에서 PATCH을 시도하면 &#39;zipCode&#39; 속성이 &#39;profile&#39; 리소스에 유효하지 않다는 오류 메시지와 함께 500 내부 서버 오류가 발생합니다.

## 나머지 응답

아래 섹션에는 Campaign Standard과 v8 REST 응답 간의 사소한 차이점이 나열되어 있습니다.

* 단일 GET 레코드의 경우 응답에는 응답에 href가 포함됩니다.
* 속성을 사용하여 쿼리하면 Campaign v8은 응답에 개수 및 페이지 매김 기능을 제공합니다.
* POST 작업 후 연결된 리소스의 값이 응답에서 반환됩니다.

## 오류 코드 및 메시지

아래 섹션에는 Campaign Standard과 Campaign v8 오류 코드 및 메시지의 차이점이 나와 있습니다.

| 시나리오 | Campaign Standard | Campaign v8 |
|  ---  |  ---  |  ---  |
| 요청 본문에 잘못된 PKey 사용 | 500 - &#39;O5iRp40EGA&#39; 특성을 알 수 없습니다(&#39;Profiles (nms:recipient)&#39; 스키마 정의 참조). XTK-170036 표현식 &#39;@id = @O5iRp40EGA&#39;을(를) 구문 분석할 수 없습니다. | 404 - PKey를 해독할 수 없습니다. (PKey=@jksad) |
| URI에 잘못된 PKey 사용 | 500 - &#39;O5iRp40EGA&#39; 특성을 알 수 없습니다(&#39;Profiles (nms:recipient)&#39; 스키마 정의 참조). XTK-170036 표현식 &#39;@id = @O5iRp40EGA&#39;을(를) 구문 분석할 수 없습니다. | 404 - PKey를 해독할 수 없습니다. (PKey=@jksad) 지원되지 않는 끝점입니다. (endpoint=rest/profileAndServices/profile/@jksad) |
| URI 및 요청 본문에서 두 개의 서로 다른 원시 Pkey 사용 | 500 - RST-360011 오류가 발생했습니다. 관리자에게 문의하십시오. RST-360012 리소스 &#39;서비스&#39;에서 일관성이 없는 작업 - 키 &#39;SVC3&#39;을(를) &#39;SVC4&#39;로 업데이트할 수 없습니다. | 500 - 오류가 발생했습니다. 관리자에게 문의하십시오. |
| URI에서 PKey를 사용하고 요청 본문에서 다른 원시 PKey 사용 | 500 - 동일한 키 &quot;SVC4&quot;의 &quot;서비스&quot;가 이미 있습니다. PGS-220000 PostgreSQL 오류: 오류: 중복 키 값이 고유 제약 조건 &quot;nmsservice_name&quot;을 위반합니다. DETAIL: 키(sname)=(SVC4)가 이미 있습니다. | 500 - 오류가 발생했습니다. 관리자에게 문의하십시오. |
| URI에 존재하지 않는 원시 ID 사용 | 404 - RST-360011 오류가 발생했습니다. 관리자에게 문의하십시오. &#39;adobe_nl:0&#39; 키(스키마가 &#39;service&#39;이고 이름이 &#39;adobe_nl&#39;인 문서)에서 경로가 &#39;Service&#39;인 문서를 찾을 수 없음 | 404 - &#39;adobe_nl&#39; 키(스키마가 &#39;service&#39;이고 이름이 &#39;adobe_nl&#39;인 문서)에서 &#39;Service&#39; 경로가 있는 문서를 찾을 수 없음 |
| 요청 본문에 존재하지 않는 원시 ID 사용 | 404 - RST-360011 오류가 발생했습니다. 관리자에게 문의하십시오. 경로가 &#39;Service&#39;인 문서를 &#39;adobe_nl&#39; 키(스키마가 &#39;service&#39;이고 이름이 &#39;adobe_nl&#39;인 문서)에서 찾을 수 없습니다. | 404 - &#39;adobe_nl&#39; 키(스키마가 &#39;service&#39;이고 이름이 &#39;adobe_nl&#39;인 문서)에서 &#39;Service&#39; 경로가 있는 문서를 찾을 수 없음 |
| - | 500 - RST-360011 오류가 발생했습니다. 관리자에게 문의하십시오. | 500 - 오류가 발생했습니다. 관리자에게 문의하십시오. |
| 잘못된 성별(또는 기타) 열거형 값이 있는 프로필/서비스 삽입 | 500 - RST-360011 오류가 발생했습니다. 관리자에게 문의하십시오. &#39;invalid&#39; 값은 &#39;@gender&#39; 필드의 &#39;nms:recipient:gender&#39; 열거에 사용할 수 없습니다. | 500 - 오류가 발생했습니다. 관리자에게 문의하십시오. |

## 프로필 - 시간대

Campaign Standard을 사용하면 시간대가 **profileAndServices/profile** REST API 호출의 JSON 응답의 일부로 표시됩니다.

Campaign v8에서 시간대는 **profileAndServicesExt/profile** REST API 호출의 일부로만 표시됩니다. 확장 스키마에 추가되고 있으므로 **profileAndServices/profile** REST API 호출의 일부가 아닙니다.

## 워크플로우 - 외부 신호 트리거

Campaign Standard Workflow GET API는 워크플로 인스턴스 변수 및 해당 데이터 유형(부울, 문자열 등)과 같은 매개 변수 이름을 반환합니다. POST API 호출을 통해 신호를 트리거할 때 적절한 포맷의 JSON 요청 본문을 만드는 데 사용됩니다.

Campaign v8은 광고 워크플로 인스턴스 변수를 지원하지 않지만 개발자는 해당 변수를 알고 있어야 합니다. 따라서, 마이그레이션 후 GET API 응답에서 매개 변수 정보를 사용하지 않고 POST 요청 본문의 매개 변수 정보를 구성해야 합니다.

<!--## Transactional messages

* With Campaign Standard, a POST request returns empty fields for elements and attributes in the request body. With Campaign v8, the response returns values that match the ones in the request body instead.

* When publishing an event configuration, the API preview panel displays the REST URL alongside the request body syntax.

    Since Campaign v8 does not support event configuration fields definition (event creation is just adding a value to eventType enumeration), there is no API preview panel when adding an event type. The REST URL is displayed  in the transactional message user interface once an event transactional message is published.-->
