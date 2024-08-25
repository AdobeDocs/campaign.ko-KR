---
product: campaign
title: 워크플로의 JavaScript 코드 예
description: 다음 예에서는 워크플로우에서 JavaScript 코드를 사용하는 방법을 보여 줍니다
feature: Workflows
role: Developer
exl-id: 3412e3de-1c88-496e-8fda-ca9fc9b18e69
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 2%

---

# 워크플로의 JavaScript 코드 예{#javascript-in-workflows}

다음 예에서는 워크플로우에서 JavaScript 코드를 사용하는 방법을 보여 줍니다.

* [데이터베이스에 쓰기](#write-example)
* [데이터베이스 쿼리](#read-example)
* [정적 SOAP 메서드를 사용하여 워크플로우 트리거](#trigger-example)
* [비정적 SOAP 메서드를 사용하여 데이터베이스와 상호 작용합니다](#interact-example)

정적 및 비정적 SOAP 메서드에 대해 [자세히 알아보기](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html){target="_blank"}.

이 예제에서는 ECMAScript for XML (E4X) 확장 프로그램이 사용됩니다. 이 확장을 사용하면 JavaScript 호출과 XML 프리미티브를 동일한 스크립트에 결합할 수 있습니다.

이러한 예를 시도하려면 다음 단계를 수행합니다.

1. 워크플로우를 만들고 다음 활동을 워크플로우에 추가합니다.
   1. 활동 시작
   1. JavaScript 코드 활동
   1. 종료 활동

   워크플로우 빌드에 대해 [자세히 알아보기](build-a-workflow.md).

1. 활동에 JavaScript 코드를 추가합니다. [자세히 알아보기](advanced-parameters.md).
1. 워크플로를 저장합니다.
1. 예제를 테스트합니다.
   1. 워크플로우를 시작합니다. [자세히 알아보기](start-a-workflow.md).
   1. 분개를 엽니다. [자세히 알아보기](monitor-workflow-execution.md#displaying-logs).

## 예제 1: 데이터베이스에 쓰기{#write-example}

데이터베이스에 쓰려면 `xtk:session` 스키마에서 정적 `Write` 메서드를 사용할 수 있습니다.

1. XML로 쓰기 요청을 작성합니다.

1. 레코드를 작성합니다.

   1. `xtk:session` 스키마에서 `Write` 메서드를 호출합니다.

      >[!IMPORTANT]
      > Adobe Campaign v8을 사용하는 경우 Snowflake 테이블에서 `Write` 메서드에 대한 **수집** 및 **데이터 업데이트/삭제** API와 함께 스테이징 메커니즘을 사용하는 것이 좋습니다. [자세히 보기](https://experienceleague.adobe.com/docs/campaign/campaign-v8/architecture/api/new-apis.html){target="_blank"}.

   1. XML 코드를 쓰기 요청의 인수로 전달합니다.

### 1단계: 쓰기 요청 작성

레코드를 추가, 업데이트 및 삭제할 수 있습니다.

#### 레코드 삽입

`insert` 작업은 기본 작업이므로 지정할 필요가 없습니다.

이 정보를 XML 속성으로 지정합니다.

* 수정할 테이블의 스키마
* 채울 테이블 필드

예:

```javascript
var myXML = <recipient xtkschema="nms:recipient"
    firstName="Isabel"
    lastName="Garcia"
    email="isabel.garcia@mycompany.com"/>
```

#### 레코드 업데이트

`_update` 작업을 사용합니다.

이 정보를 XML 속성으로 지정합니다.

* 수정할 테이블의 스키마
* 업데이트할 테이블 필드
* 업데이트할 레코드를 식별하는 데 필요한 주요 인수

예:

```javascript
var myXML = <recipient xtkschema="nms:recipient"
    status="Client"
    email="isabel.garcia@mycompany.com"
    operation="_update"
    _key="@email"/>
```

#### 레코드 삭제

`DeleteCollection` 메서드를 사용합니다. [자세히 알아보기](https://experienceleague.adobe.com/developer/campaign-api/api/sm-session-DeleteCollection.html){target="_blank"}

다음 정보를 지정합니다.

* 수정할 테이블의 스키마
* 업데이트할 레코드를 XML 요소 형식으로 식별하는 데 필요한 `where` 절

예:

```javascript
xtk.session.DeleteCollection(
    "nms:recipient",
    <where>
        <condition expr="[@email] = 'isabel.garcia@mycompany.com'"/>
    </where>,
    false
    )
```

### 2단계: 레코드 쓰기

`xtk:session` 스키마에서 비정적 `Write` 메서드를 호출합니다.

```javascript
xtk.session.Write(myXML)
```

이 메서드에 대해서는 값이 반환되지 않습니다.

워크플로우의 JavaScript 코드 활동에 전체 코드를 추가합니다.

```javascript
var myXML = <recipient xtkschema="nms:recipient"
    firstName="Isabel"
    lastName="Garcia"
    email="isabel.garcia@mycompany.com"/>

xtk.session.Write(myXML)
```

이 비디오는 데이터베이스에 쓰는 방법을 보여 줍니다.
>[!VIDEO](https://video.tv.adobe.com/v/18472/?learn=on)

## 예제 2: 데이터베이스 쿼리{#read-example}

데이터베이스를 쿼리하려면 비정적 `xtk:queryDef` 인스턴스 메서드를 사용할 수 있습니다.

1. XML로 쿼리를 작성합니다.
1. 쿼리 개체를 만듭니다.
1. 쿼리를 실행합니다.

### 1단계: 쿼리 작성

`queryDef` 엔터티에 대한 XML 코드를 지정하십시오.

구문:

```xml
<queryDef schema="nms:recipient" operation="">
    <!-- select, where, and orderBy clauses as XML elements -->
</queryDef>
```

다음 정보를 지정합니다.

* 읽을 테이블의 스키마
* 작업
* `select` 절에 반환될 열
* `where` 절의 조건
* `orderBy` 절의 필터링 기준

다음 작업을 사용할 수 있습니다.

| 작업 | 결과 |
| --- | --- |
| `select` | 0개 이상의 요소가 컬렉션으로 반환됩니다. |
| `getIfExists` | 요소 1개가 반환됩니다. 일치 요소가 없으면 빈 요소가 반환됩니다. |
| `get` | 요소 1개가 반환됩니다. 일치 요소가 없으면 오류가 반환됩니다. |
| `count` | 일치하는 레코드 수가 `count` 특성이 있는 요소 형식으로 반환됩니다. |

`select`, `where` 및 `orderBy` 절을 XML 요소로 작성하십시오.

* `select` 절

  반환할 열을 지정합니다. 예를 들어 개인의 이름과 성을 선택하려면 다음 코드를 작성합니다.

  ```xml
  <select>
      <node expr="@firstName"/>
      <node expr="@lastName"/>
  </select>
  ```

  `nms:recipient` 스키마를 사용하면 요소가 다음 형식으로 반환됩니다.

  ```xml
  <recipient firstName="Bo" lastName="Didley"/>
  ```

* `where` 절

  조건을 지정하려면 `where` 절을 사용합니다. 예를 들어 **Training** 폴더에 있는 레코드를 선택하려면 다음 코드를 작성할 수 있습니다.

  ```xml
  <where>
      <condition expr="[folder/@label]='Training'"/>
  </where>
  ```

  여러 표현식을 결합할 때는 첫 번째 표현식에 부울 연산자를 사용하십시오. 예를 들어 Isabel Garcia라는 이름을 가진 모든 사람을 선택하려면 다음 코드를 작성할 수 있습니다.

  ```xml
  <condition boolOperator="AND" expr="@firstName='Isabel'"/>
  <condition expr="@lastName='Garcia'"/>
  ```

* `orderBy` 절

  결과 집합을 정렬하려면 `orderBy` 절을 `sortDesc` 특성이 있는 XML 요소로 지정하십시오. 예를 들어 성을 오름차순으로 정렬하려면 다음 코드를 작성할 수 있습니다.

  ```xml
  <orderBy>
      <node expr="@lastName> sortDesc="false"/>
  </orderBy>
  ```

### 2단계: 쿼리 개체 만들기

XML 코드에서 엔터티를 만들려면 `create(`*`content`*`)` 메서드를 사용합니다.

```javascript
var query = xtk.queryDef.create(
    <queryDef schema="nms:recipient" operation="select">
    …
    </queryDef>)
```

만들 엔터티의 스키마로 `create(`*`content`*`)` 메서드 접두사를 사용합니다.

*`content`* 인수는 문자열 인수이며 선택 사항입니다. 이 인수는 엔터티를 설명하는 XML 코드를 포함합니다.

### 3단계: 쿼리 실행

다음 단계를 수행하십시오.

1. `queryDef` 엔터티에서 `ExecuteQuery` 메서드 호출:

   ```javascript
   var res = query.ExecuteQuery()
   ```

1. 결과를 처리합니다.
   1. 루프 구문을 사용하여 `select` 작업의 결과를 반복합니다.
   1. `getIfExists` 작업을 사용하여 결과를 테스트합니다.
   1. `count` 작업을 사용하여 결과를 계산하십시오.

#### `select` 작업 결과

모든 일치 항목이 컬렉션으로 반환됩니다.

```xml
<recipient-collection>
    <recipient email="jane.smith@mycompany.com">
    <recipient email="john.harris@mycompany.com">
</recipient-collection>
```

결과를 반복하려면 `for each` 루프를 사용합니다.

```javascript
for each (var rcp in res:recipient)
    logInfo(rcp.@email)
```

루프에 로컬 수신자 변수가 포함되어 있습니다. 수신자 컬렉션에서 반환되는 각 수신자에 대해 수신자 이메일이 인쇄됩니다. `logInfo` 함수에 대해 [자세히 알아보기](https://experienceleague.adobe.com/developer/campaign-api/api/f-logInfo.html){target="_blank"}.

#### `getIfExists` 작업 결과

각 일치 항목이 요소로 반환됩니다.

```xml
<recipient id="52,378,079">
```

일치하는 항목이 없으면 빈 요소가 반환됩니다.

```xml
<recipient/>
```

기본 키 노드(예: `@id` 특성)를 참조할 수 있습니다.

```javascript
if (res.@id !=undefined)
    { // match was found
    …
    }
```

#### `get` 작업 결과

하나의 일치 항목이 요소로 반환됩니다.

```xml
<recipient id="52,378,079">
```

일치하는 항목이 없으면 오류가 반환됩니다.

>[!TIP]
>
>일치하는 항목이 있는 경우 `get` 작업을 사용하십시오. 그렇지 않으면 `getIfExists` 작업을 사용하십시오. 이 모범 사례를 사용하는 경우 오류가 예기치 않은 문제를 표시합니다. `get` 작업을 사용하는 경우 `try…catch` 문을 사용하지 마십시오. 문제는 워크플로우의 오류 처리 프로세스에 의해 처리됩니다.

#### `count` 작업 결과

`count` 특성이 있는 요소가 반환됩니다.

```xml
<recipient count="200">
```

결과를 사용하려면 `@count` 특성을 참조하십시오.

```javascript
if (res.@count > 0)
    { // matches were found
    …
    }
```

`select` 작업의 경우 이 코드를 워크플로우의 JavaScript 코드 활동에 추가합니다.

```javascript
var myXML =
<queryDef schema="nms:recipient" operation="select">
    <select>
        <node expr="@firstName"/>
        <node expr="@lastName"/>
    </select>
</queryDef>

var query = xtk.queryDef.create(myXML)

var res = query.ExecuteQuery()

for each (var rcp in res.recipient)
    logInfo(rcp.@firstName + " " + rcp.@lastName)
```

`select` 작업은 기본 작업이므로 지정할 필요가 없습니다.

이 비디오는 데이터베이스에서 를 읽는 방법을 보여 줍니다.
>[!VIDEO](https://video.tv.adobe.com/v/18475/?learn=on)

## 워크플로우 트리거 {#trigger-example}

예를 들어 기술 워크플로우에서 프로그래밍 방식으로 워크플로우를 트리거하거나 사용자가 웹 애플리케이션 페이지에 입력한 정보를 처리할 수 있습니다.

워크플로우 트리거는 이벤트를 사용하여 작동합니다. 이벤트에 다음 기능을 사용할 수 있습니다.

* 이벤트를 게시하려면 정적 `PostEvent` 메서드를 사용합니다. [자세히 알아보기](https://experienceleague.adobe.com/developer/campaign-api/api/sm-workflow-PostEvent.html){target="_blank"}
* 이벤트를 받으려면 **[!UICONTROL External signal]** 활동을 사용할 수 있습니다. [자세히 알아보기](external-signal.md).

다음과 같은 다양한 방법으로 워크플로우를 트리거할 수 있습니다.

* **[!UICONTROL JavaScript code]** 활동의 기본 스크립트에서 워크플로우 인라인을 트리거할 수 있습니다.
* 다른 작업이 완료되면 워크플로우를 트리거할 수 있습니다.
   * 초기 워크플로의 **[!UICONTROL End]** 활동에 초기화 스크립트를 추가합니다.
   * 대상 워크플로우의 시작 부분에 **[!UICONTROL External signal]** 활동을 추가합니다.

     초기 워크플로가 완료되면 이벤트가 게시됩니다. 나가는 전환이 활성화되고 이벤트 변수가 채워집니다. 그런 다음 대상 워크플로우에서 이벤트를 수신합니다.

     >[!TIP]
     >
     >활동에 스크립트를 추가할 때 활동 이름을 이중 하이픈(예: `-- end --`)으로 묶는 것이 좋습니다. 워크플로우 모범 사례에 대해 [자세히 알아보기](workflow-best-practices.md).

`PostEvent` 메서드 구문:

```javascript
PostEvent(
    String     //ID of the target workflow
    String     //Name of the target activity
    String     //Name of the transition to be activated in case of multiple transitions
    XML        //Event parameters, in the <variables/> element
    Boolean    //To trigger the target workflow only once, set this parameter to true.
)
```

이 예제에서는 워크플로가 완료되면 짧은 텍스트가 **wkfExampleReceiver** 워크플로의 **signal** 활동에 전달됩니다.

```javascript
var strLabel = "Adobe Campaign, Marketing that delivers"
xtk.workflow.PostEvent(
    "wkfExampleReceiver",
    "signal",
    "",
    <variables strLine={strLabel}/>,
    false)
```

마지막 매개 변수가 `false`(으)로 설정되어 있으므로 초기 워크플로가 완료될 때마다 **wkfExampleReceiver** 워크플로가 트리거됩니다.

워크플로우를 트리거할 때는 다음 원칙을 염두에 두십시오.

* `PostEvent` 명령이 비동기적으로 실행됩니다. 명령은 서버 큐에 배치됩니다. 메서드는 이벤트가 게시된 후 반환됩니다.
* 대상 워크플로우를 시작해야 합니다. 그렇지 않으면 로그 파일에 오류가 기록됩니다.
* 대상 워크플로우가 일시 중단되면 워크플로우가 다시 시작될 때까지 `PostEvent` 명령이 대기됩니다.
* 트리거된 활동에서는 작업이 진행 중일 필요가 없습니다.

이 비디오는 정적 API 메서드를 사용하는 방법을 보여 줍니다.
>[!VIDEO](https://video.tv.adobe.com/v/18481/?learn=on)

이 비디오는 워크플로우를 트리거하는 방법을 보여 줍니다.
>[!VIDEO](https://video.tv.adobe.com/v/18485/?learn=on)

## 데이터베이스와 상호 작용 {#interact-example}

다음 예에서는 이러한 작업을 수행하는 방법을 보여 줍니다.

* 비정적 SOAP 메서드를 사용하려면 스키마에서 `get` 및 `create` 메서드를 사용하십시오.
* SQL 쿼리를 수행하는 메서드 만들기
* `write` 메서드를 사용하여 레코드를 삽입, 업데이트 및 삭제합니다.

다음 단계를 수행하십시오.

1. 쿼리를 정의합니다.

   * 해당 스키마(예: `xtk:workflow` 스키마)에서 `create` 메서드를 사용하여 엔터티를 검색합니다. [자세히 알아보기](https://experienceleague.adobe.com/developer/campaign-api/api/f-create.html){target="_blank"}
   * `queryDef` 메서드를 사용하여 SQL 쿼리를 실행하십시오.

1. `ExecuteQuery` 메서드를 사용하여 쿼리를 실행합니다. [자세히 알아보기](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-ExecuteQuery.html){target="_blank"}

   `for each` 루프를 사용하여 결과를 검색합니다.

### `select` 절이 있는 `queryDef` 메서드의 구문

```xml
<queryDef schema="schema_key" operation="operation_type">
    <select>
        <node expr="expression1">
        <node sql="expression2">
    </select>
    <where> 
        <condition expr="expression1"/> 
        <condition sql="expression2"/>
    </where>
    <orderBy>
        <node expr="expression1">
        <node sql="expression2">
    </orderBy>
    <groupBy>
        <node expr="expression1">
        <node sql="expression2">
    </groupBy>
    <having>
        <condition expr="expression1"/> 
        <condition sql="expression2"/>
    </having>
</queryDef>
```

### `Create` 메서드

#### 예 1: 레코드 선택 및 저널에 쓰기

**wfExamples** 폴더에 있는 워크플로의 내부 이름이 선택됩니다. 결과는 내부 이름별로 오름차순으로 정렬되고 저널에 기록됩니다.

```javascript
var query = xtk.queryDef.create(
    <queryDef schema="xtk:workflow" operation="select">
        <select>
            <node expr="@internalName"/>
        </select>
        <where>
            <condition expr="[folder/@name]='wfExamples'"/>
        </where>
        <orderBy>
            <node expr="@internalName" sortDesc="false"/>
        </orderBy>
    </queryDef>
    )

var res = query.ExecuteQuery()
for each (var w in res.workflow)
    logInfo(w.@internalName)
```

#### 예제 2: 레코드 삭제

Chris Smith라는 이름을 가진 모든 수신자의 이름, 성, 이메일 및 ID가 선택됩니다. 결과는 이메일로 정렬되고 오름차순으로 정렬되어 저널에 기록됩니다. `delete` 작업은 선택한 레코드를 삭제하는 데 사용됩니다.

```javascript
// Build the query, create a query object and hold the object in a variable
var query = xtk.queryDef.create(
        <queryDef schema="nms:recipient" operation="select">
            <select>
                <node expr="@firstName"/>
                <node expr="@lastName"/>
                <node expr="@email"/>
                <node expr="@id"/>
            </select>
            <where>
                <condition expr="[folder/@label]='Recipients'"/>
                <condition expr="[@lastName]='Smith'"/>
                <condition expr="[@firstName]='Chris'"/>
            </where>
            <orderBy>
                <node expr="@email" sortDesc="false"/>
            </orderBy>
        </queryDef>
)

//Run the query using the ExecuteQuery method against the created object
var res = query.ExecuteQuery()

//Loop through the results, print out the person's name and email, then delete the records
for each (var rec in res.recipient)
    {
     logInfo("Delete record = Email: " + rec.@email + ', ' + rec.@firstName + ' ' + rec.@lastName)
     xtk.session.Write(<recipient xtkschema="nms:recipient" _operation="delete" id={rec.@id}/>)
    }
```

#### 예 3: 레코드 선택 및 저널에 쓰기

이 예제에서는 비정적 메서드가 사용됩니다. **1234** 폴더에 정보가 저장되고 전자 메일 도메인 이름이 &quot;adobe&quot;로 시작하는 모든 받는 사람의 전자 메일과 출생연도가 선택됩니다. 결과는 생년월일별로 내림차순으로 정렬됩니다. 수신자의 이메일이 저널에 기록됩니다.

```javascript
var query = xtk.queryDef.create(
<queryDef schema="nms:recipient" operation="select">
    <select>
        <node expr="@email"/>
        <node sql="sEmail"/>
        <node expr="Year(@birthDate)"/>
    </select>
    <where>
        <condition expr="[@folder-id] = 1234 and @domain like 'adobe%'"/>
        <condition sql="iFolderId = 1234 and sDomain like 'adobe%'"/>
    </where>
    <orderBy>
        <node expr="@birthDate" sortDesc="true"/>
    </orderBy>
</queryDef>
)

var res = query.ExecuteQuery()
for each (var w in res.recipient)
    logInfo(w.@email)
```

### `Write` 메서드

레코드를 삽입, 업데이트 및 삭제할 수 있습니다. Adobe Campaign의 모든 스키마에서 `Write` 메서드를 사용할 수 있습니다. 이 메서드는 정적이므로 개체를 만들 필요가 없습니다. 다음 작업을 사용할 수 있습니다.

* `update` 작업
* 업데이트할 레코드를 식별하는 `_key` 인수가 포함된 `insertOrUpdate` 작업

  **받는 사람** 폴더를 지정하지 않으면 일치하는 항목이 있으면 모든 하위 폴더에서 레코드가 업데이트됩니다. 그렇지 않으면 루트 **수신자** 폴더에 레코드가 만들어집니다.

* `delete` 작업

>[!IMPORTANT]
> Adobe Campaign v8을 사용하는 경우 Snowflake 테이블에서 `Write` 메서드에 대한 **수집** 및 **데이터 업데이트/삭제** API와 함께 스테이징 메커니즘을 사용하는 것이 좋습니다. [자세히 보기](https://experienceleague.adobe.com/docs/campaign/campaign-v8/architecture/api/new-apis.html){target="_blank"}.

#### 예제 1: 레코드 삽입 또는 업데이트

```javascript
xtk.session.Write(
<recipient
    xtkschema="nms:recipient"
    _operation="insertOrUpdate" _key="@email"
    lastName="Lennon"
    firstName="John"
    email="johnlennon@thebeatles.com"
/>
)
```

#### 예제 2: 레코드 삭제

이 예제에서는 정적 메서드와 비정적 메서드를 결합합니다.

```javascript
var query=xtk.queryDef.create(
<queryDef schema="nms:recipient" operation="select">
    <select>
        <node expr="@Id"/>
    </select>
    <where>
        <condition expr="[@email]='johnlennon@thebeatles.com'"/>
    </where>
</queryDef>
);

var res = query.ExecuteQuery()
for each (var w in res.recipient) {
xtk.session.Write(
    <recipient xtkschema="nms:recipient" _operation="delete" id={w.@id}/>
);
}
```

이 비디오는 비정적 API 메서드를 사용하는 방법을 보여 줍니다.
>[!VIDEO](https://video.tv.adobe.com/v/18477/?learn=on)

이 비디오는 워크플로우에서 비정적 API 메소드의 사용 예를 보여 줍니다.
>[!VIDEO](https://video.tv.adobe.com/v/18476/?learn=on)

## 관련 항목

### API 설명서

* [SOAP 호출 샘플](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html){target="_blank"}
* 방법:
   * [만들기](https://experienceleague.adobe.com/developer/campaign-api/api/f-create.html){target="_blank"}
   * [DeleteCollection](https://experienceleague.adobe.com/developer/campaign-api/api/sm-session-DeleteCollection.html){target="_blank"}
   * [ExecuteQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-ExecuteQuery.html){target="_blank"}
   * [PostEvent](https://experienceleague.adobe.com/developer/campaign-api/api/sm-workflow-PostEvent.html){target="_blank"}
   * [쓰기](https://experienceleague.adobe.com/developer/campaign-api/api/sm-session-Write.html){target="_blank"}
* [logInfo 함수](https://experienceleague.adobe.com/developer/campaign-api/api/f-logInfo.html){target="_blank"}
