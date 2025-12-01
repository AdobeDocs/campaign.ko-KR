---
title: queryDef를 사용하여 데이터베이스 쿼리
description: queryDef 및 NLWS 메서드를 사용하여 Campaign 데이터베이스를 쿼리하는 방법에 대해 알아봅니다
feature: API
role: Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: 0fd39d6c-9e87-4b0f-a960-2aef76c9c8eb
source-git-commit: ceab90331fab0725962a2a98f338ac3dc31a2588
workflow-type: tm+mt
source-wordcount: '1281'
ht-degree: 1%

---

# queryDef를 사용하여 데이터베이스 쿼리 {#query-database-api}

[!DNL Adobe Campaign]은(는) `queryDef` 및 `NLWS` 개체를 사용하여 데이터베이스와 상호 작용하는 강력한 JavaScript 메서드를 제공합니다. 이러한 SOAP 기반 메서드를 사용하면 JSON, XML 또는 SQL을 사용하여 데이터를 로드, 생성, 업데이트 및 쿼리할 수 있습니다.

>[!NOTE]
>
>이 설명서는 프로그래밍 방식으로 데이터베이스 쿼리를 위한 데이터 지향 API를 다룹니다. REST API의 경우 [REST API 시작](api/get-started-apis.md)을 참조하세요. 시각적 쿼리 작성에 대한 자세한 내용은 [쿼리 편집기 작업](../start/query-editor.md)을 참조하세요.

## NLWS란? {#what-is-nlws}

`NLWS`(Neolane Web Services)은 [!DNL Adobe Campaign]의 SOAP 기반 API 메서드에 액세스하는 데 사용되는 전역 JavaScript 개체입니다. 스키마는 `NLWS` 개체의 속성으로, 프로그래밍 방식으로 Campaign 엔터티와 상호 작용할 수 있습니다.

[Campaign JSAPI 설명서](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html?lang=ko){target="_blank"}에 따르면 &quot;스키마는 &#39;NLWS&#39; 전역 개체입니다.&quot; 스키마 메서드에 액세스하는 구문은 다음 패턴을 따릅니다.

```javascript
NLWS.<namespace><SchemaName>.<method>()
```

**예:**

* `NLWS.nmsRecipient` - 수신자 스키마(`nms:recipient`)에 대한 액세스 메서드
* `NLWS.nmsDelivery` - 게재 스키마(`nms:delivery`)에 대한 액세스 메서드
* `NLWS.xtkQueryDef` - 데이터베이스 쿼리를 위해 queryDef 메서드에 액세스합니다.

일반적인 API 메서드는 다음과 같습니다.

* `load(id)` - 엔터티를 해당 ID로 로드합니다. [자세히 알아보기](https://experienceleague.adobe.com/developer/campaign-api/api/f-load.html?lang=ko){target="_blank"}
* `create(data)` - 새 엔터티 만들기
* `save()` - 엔터티에 변경 내용 저장

**공식 설명서의 예:**

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
```

>[!NOTE]
>
>**대체 구문:** 이전 버전과의 호환성을 위해 일부 문서에서 소문자 네임스페이스 구문을 확인할 수도 있습니다(예: `nms.recipient.create()`, `xtk.queryDef.create()`). 두 구문이 모두 작동하지만 `NLWS`은(는) 공식 Campaign JSAPI 참조에 문서화된 표준입니다.

## 필수 구성 요소 {#prerequisites}

queryDef 및 NLWS 메서드를 사용하기 전에 다음 사항에 익숙해야 합니다.

* JavaScript
* [!DNL Adobe Campaign] 데이터 모델 및 스키마
* 스키마 요소 탐색을 위한 XPath 표현식

**Campaign 데이터 모델 이해:**

Adobe Campaign에는 클라우드 데이터베이스에서 함께 연결된 테이블로 구성된 사전 정의된 데이터 모델이 포함되어 있습니다. 기본 구조에는 다음이 포함됩니다.

* **받는 사람 테이블**(`nmsRecipient`) - 마케팅 프로필을 저장하는 기본 테이블
* **게재 테이블** (`nmsDelivery`) - 게재 작업 및 템플릿을 게재 수행을 위한 매개 변수와 함께 저장합니다.
* **로그 테이블** - 저장소 실행 로그:
   * `nmsBroadLogRcp` - 받는 사람에게 보낸 모든 메시지의 게재 로그
   * `nmsTrackingLogRcp` - 수신자 반응(열기, 클릭)에 대한 추적 로그
* **기술 테이블** - 연산자(`xtkGroup`), 세션(`xtkSessionInfo`), 워크플로우(`xtkWorkflow`)와 같은 시스템 데이터를 저장합니다.

Campaign 인터페이스의 스키마 설명에 액세스하려면 **관리 > 구성 > 데이터 스키마**&#x200B;로 이동하여 리소스를 선택하고 **설명서** 탭을 클릭하십시오.

## 엔티티 스키마 메서드 {#entity-schema-methods}

[!DNL Adobe Campaign]의 각 스키마(예: `nms:recipient`, `nms:delivery`)에는 `NLWS` 개체를 통해 액세스할 수 있는 메서드가 제공됩니다. 이러한 메서드는 데이터베이스 엔터티와 상호 작용하는 편리한 방법을 제공합니다.

### 정적 메서드 {#static-methods}

정적 SOAP 메서드는 스키마를 나타내는 개체에서 메서드를 호출하여 액세스됩니다. 예를 들어 `NLWS.xtkWorkflow.PostEvent()`은(는) 정적 메서드를 호출합니다.

### 비정적 메서드 {#non-static-methods}

비정적 SOAP 메서드를 사용하려면 먼저 해당 스키마에서 `load` 또는 `create` 메서드를 사용하여 엔터티를 검색해야 합니다. 자세한 내용은 [Campaign JSAPI 설명서](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html?lang=ko){target="_blank"}를 참조하세요.

### 엔티티 로드, 저장 및 생성 {#load-save-create}

**ID별로 엔터티를 로드하고 업데이트함:**

```javascript
// Load a delivery by @id and save
var delivery = NLWS.nmsDelivery.load("12435");
delivery.label = "New label";
delivery.save();
```

**JSON을 사용하여 받는 사람 만들기:**

```javascript
// Create via JSON, edit via JS and save
var recipient = NLWS.nmsRecipient.create({
  x: { // the key 'x' doesn't matter
    email: 'john.doe@example.com',
  }
});
recipient.folder_id = 1183;
recipient.firstName = 'John';
recipient.lastName = 'Doe';
recipient.save();
```

**XML을 사용하여 받는 사람 만들기:**

```javascript
// Create via XML and save
var recipient = NLWS.nmsRecipient.create(
  <recipient
    email="support@adobe.com"
    lastName="Adobe"
    firstName="Support"
  />
);
recipient.save();
```

## QueryDef 개요 {#querydef-overview}

`xtk:queryDef` 스키마는 데이터베이스 쿼리를 빌드하고 실행하는 메서드를 제공합니다. `NLWS.xtkQueryDef.create()`을(를) 사용하여 JSON 또는 XML 구문으로 쿼리를 작성할 수 있습니다.

**사용 가능한 작업:**

* `select` - 여러 레코드 검색
* `get` - 단일 레코드 검색(SQL `LIMIT 1`)
* `getIfExists` - 단일 레코드를 검색하고, 찾을 수 없으면 null을 반환합니다.
* `count` - 기준과 일치하는 레코드 수

[Campaign JSAPI 설명서](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html?lang=ko){target="_blank"}에서 queryDef 메서드에 대해 자세히 알아보세요.

## JSON을 사용한 쿼리 {#query-json}

`NLWS.xtkQueryDef.create()`을(를) 사용하여 JSON 구문으로 쿼리를 빌드합니다. `get` 작업은 단일 레코드(SQL `LIMIT 1`)를 검색하는 반면 `select`은(는) 여러 레코드를 검색합니다.

**단일 받는 사람 받기:**

```javascript
var email = "contact@example.com";
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "get", // "get" does a SQL "LIMIT 1"
    select: { 
      node: [{expr: "@id"}, {expr: "@email"}, {expr: "@firstName"}] 
    },
    where: { 
      condition: [
        {expr: "@email = '" + email + "'"}, // filter by email
      ],
    }
  }
});

var res = query.ExecuteQuery(); 
// res is an XML object such as <recipient id="1234" email="contact@example.com" firstName="John"/>
var recipient = NLWS.nmsRecipient.load(res.$id); // conversion to a JavaScript object
recipient.email = "newemail@example.com";
recipient.save();
```

**예외를 방지하려면 `getIfExists`을(를) 사용합니다.**

레코드가 없는 경우 예외를 방지하려면 `operation: "getIfExists"` 대신 `get`을(를) 사용합니다.

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "getIfExists",
    select: { node: [{expr: "@id"}] },
    where: { 
      condition: [{expr: "@email = 'nonexistent@example.com'"}]
    }
  }
});

var res = query.ExecuteQuery();
if (res) {
  logInfo("Recipient found: " + res.$id);
} else {
  logInfo("Recipient not found");
}
```

## 여러 레코드 선택 {#select-multiple}

`select` 작업을 사용하여 여러 레코드를 검색합니다. 조건, 순서 및 제한을 추가할 수 있습니다.

**필터 및 순서 지정 쿼리 워크플로:**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "xtk:workflow", 
    operation: "select", 
    select: {
      node: [
        {expr: "@id"},
        {expr: "@label"},
        {expr: "@internalName"}
      ] 
    }, 
    where: {
      condition: [
        {expr: "[folder/@name]='nmsTechnicalWorkflow'"},
        {expr: "@production = 1"}
      ]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }
});

var res = query.ExecuteQuery();

var workflows = res.getElementsByTagName("workflow");
for each (var w in workflows) {
  logInfo(w.getAttribute("internalName"));
}
```

**XML 구문을 사용한 쿼리 게재:**

```javascript
var q = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select" lineCount="3">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
      <node expr="@created"/>
    </select>
    <where>
      <condition expr="@label NOT LIKE '%Proof%'" bool-operator="AND"/>
      <condition expr="@created &lt;= '2024-12-01'" bool-operator="AND"/>
    </where>
    <orderBy>
      <node expr="@lastModified" sortDesc="true"/>
    </orderBy>    
  </queryDef>
);

var deliveries = q.ExecuteQuery();
for each(var delivery in deliveries.delivery) {
  logInfo(delivery.@id + ": " + delivery.@label);
}
```

>[!NOTE]
>
>**결과 제한:** Campaign은 메모리 문제를 방지하기 위해 쿼리 결과를 자동으로 제한합니다.
>* 기본 제한은 컨텍스트에 따라 다릅니다(일반적으로 200~10,000개의 레코드).
>* 최대 결과 수를 명시적으로 설정하려면 `lineCount`을(를) 사용하십시오.
>* 대규모 데이터 세트(>1000개의 레코드)의 경우 queryDef 대신 워크플로우를 사용합니다. 워크플로우는 수백만 개의 행을 효율적으로 처리하도록 설계되었습니다.

[ExecuteQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-ExecuteQuery.html?lang=ko){target="_blank"} 및 [쿼리 모범 사례](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}에 대해 자세히 알아보세요.

## 워크플로우 전환 데이터 쿼리 {#workflow-transition-data}

워크플로우에서 JavaScript 활동을 사용하여 작업할 때 `vars.targetSchema` 및 `vars.tableName`을(를) 사용하여 들어오는 전환에서 데이터를 쿼리할 수 있습니다.

**워크플로우 전환에서 받는 사람 데이터를 쿼리합니다.**

```javascript
// Query data from the incoming transition
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema, // The schema from the previous activity
    operation: 'select', 
    lineCount: 999999999, // Override default 10,000 limit
    select: { 
      node: [
        {expr: '@id'},
        {expr: '@email'},
        {expr: '@firstName'},
        {expr: '@lastName'}
      ]
    },
  }
});

var records = query.ExecuteQuery(); // Returns a DOMElement

for each(var record in records.getElements()) {
  logInfo("Processing: " + record.$id + " - " + record.$email);
  
  // Clean email address
  var cleanedEmail = record.$email.replace(/\s+/g, '').toLowerCase();
  
  // Update using parameterized query to prevent SQL injection
  sqlExec(
    "UPDATE " + vars.tableName + " SET sEmail=$(sz) WHERE iId=$(l)", 
    cleanedEmail, 
    record.$id
  );
}
```

>[!CAUTION]
>
>SQL 삽입 취약성을 방지하려면 항상 문자열의 경우 `$(sz)`을(를) 사용하고 정수의 경우 `$(l)`을(를) 사용하는 매개 변수가 있는 쿼리를 사용하십시오. 자세한 내용은 [Campaign JSAPI 설명서](https://experienceleague.adobe.com/developer/campaign-api/api/f-sqlExec.html?lang=ko){target="_blank"}를 참조하세요.

## 레코드 수 {#count-records}

`Count(@id)`을(를) 별칭과 함께 사용하여 레코드를 계산합니다.

**실행 중인 가설 수:**

```javascript
var jobCount = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:remaHypothesis" operation="get">
    <select>
      <node expr="Count(@id)" alias="@count"/>
    </select>
    <where>
      <condition expr={"@status=" + HYPOTHESIS_STATUS_RUNNING}/>
    </where>
  </queryDef>
);

var iJobCount = parseInt(jobCount.ExecuteQuery().@count);
logInfo("Running jobs: " + iJobCount);
```

**조건이 여러 개인 개수:**

```javascript
var xmlQuery = <queryDef schema="nms:trackingLogRcp" operation="select">
  <select>
    <node expr="DateOnly(@logDate)" groupBy="1"/>
    <node expr="count(@id)" alias="@count"/>
    <node expr="countDistinct([@broadLog-id])" alias="@distinctCount"/>
  </select>
  <where>
    <condition expr={"@logDate IS NOT NULL AND @logDate &lt; #" + today + "# AND [@url-id] &lt;&gt; 1"}/>
  </where>
</queryDef>;

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## 값 분포 {#distribution-values}

데이터 패턴을 분석하는 데 유용한 특정 필드에 대한 값 분포를 가져옵니다.

**국가 코드 배포:**

```javascript
/**
 * @class DistributionOfValues
 * @param {string} schema - The schema name (e.g., 'nms:recipient')
 * @param {string} field - The field to analyze (e.g., '@country')
 */
function DistributionOfValues(schema, field) {
  this.queryDef = {
    operation: 'select', 
    lineCount: 200, 
    schema: schema,
    select: {
      node: [
        {alias: '@expr', expr: field, groupBy: 'true', noSqlBind: 'true'},
        {alias: '@count', expr: 'COUNT()', label: 'Count'},
      ]
    },
    orderBy: {
      node: [{expr: 'COUNT()', sortDesc: 'true'}]
    },
  };
  
  /**
   * Execute the query and return results
   * @return {Array} XML list of results
   */
  this.get = function() {
    this.results = NLWS.xtkQueryDef.create({queryDef: this.queryDef}).ExecuteQuery();
    return this.results.getElements();
  };
}

// Usage example
var d = new DistributionOfValues('nms:recipient', '@country');

// Optional: Add additional filters
d.queryDef.where = {
  condition: [{expr: 'DateOnly(@created) = #2024-12-01#'}]
};

// Execute and display results
for each(var result in d.get()) {
  logInfo(result.$expr + ': ' + result.$count);
}
```

## 분석이 있는 쿼리 열거 {#analyze-enumerations}

`analyze` 옵션은 열거형 값에 대해 사용자에게 친숙한 이름을 반환합니다. 숫자 값 대신 Campaign은 &quot;Name&quot; 및 &quot;Label&quot; 접미사를 사용하여 문자열 값과 레이블을 반환하기도 합니다.

**열거형 분석을 사용한 쿼리 게재 매핑:**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:deliveryMapping",
    operation: "get",
    select: {
      node: [
        {expr: "@id"},
        {expr: "@name"},
        {expr: "[storage/@exclusionType]", analyze: true}  // Analyze enumeration
      ]
    },
    where: {
      condition: [{expr: "@name='mapRecipient'"}]
    }
  }
});

var mapping = query.ExecuteQuery();

// Result includes:
// - exclusionType: 2 (numeric value)
// - exclusionTypeName: "excludeRecipient" (string value)
// - exclusionTypeLabel: "Exclude recipient" (display label)
logInfo("Type: " + mapping.$exclusionType);
logInfo("Name: " + mapping.$exclusionTypeName);
logInfo("Label: " + mapping.$exclusionTypeLabel);
```

[분석 옵션](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html#the-analyze-option){target="_blank"}에 대해 자세히 알아보세요.

## 쪽 매기기 {#pagination}

`lineCount` 및 `startLine`을(를) 사용하여 큰 결과 집합의 페이지를 매깁니다.

**페이지에서 레코드 검색:**

```javascript
// Get records 3 and 4 (skip first 2)
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    lineCount: 2,     // Number of records per page
    startLine: 2,     // Starting position (0-indexed)
    select: {
      node: [
        {expr: "@id"},
        {expr: "@email"}
      ]
    },
    orderBy: {
      node: [{expr: "@id"}]  // Critical: Always use orderBy for pagination
    }
  }
});

var recipients = query.ExecuteQuery();
```

>[!CAUTION]
>
>**페이지 매김에는 orderBy:**&#x200B;이(가) 필요합니다. `orderBy` 절이 없으면 쿼리 결과가 일관된 순서로 유지되지 않습니다. 후속 호출은 다른 페이지나 중복 레코드를 반환할 수 있습니다. 페이지 매김 사용 시 항상 `orderBy`을(를) 포함하십시오.

[페이지 매김](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html#pagination){target="_blank"}에 대해 자세히 알아보세요.

## 동적 쿼리 구성 {#dynamic-queries}

프로그래밍 방식으로 조건을 추가하여 쿼리를 동적으로 빌드합니다.

**기존 쿼리에 조건 추가:**

```javascript
var xmlQuery = <queryDef schema="nms:delivery" operation="select">
  <select>
    <node expr="@id"/>
    <node expr="@label"/>
  </select>
  <where/>
</queryDef>;

// Dynamically add conditions
if (includeProofs) {
  xmlQuery.where.appendChild(
    <condition expr="@label LIKE '%Proof%'"/>
  );
}

if (startDate) {
  xmlQuery.where.appendChild(
    <condition expr={"@created >= #" + Format.toISO8601(startDate) + "#"}/>
  );
}

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

**Build select 및 where 절 in loop:**

```javascript
// Build select dynamically
var select = <select/>;
var fields = ["@id", "@label", "@created"];
for each(var field in fields) {
  select.appendChild(<node expr={field}/>);
}

// Build where dynamically
var where = <where/>;
var conditions = [
  "@status = 1",
  "@type = 'email'"
];
for each(var condition in conditions) {
  where.appendChild(<condition expr={condition}/>);
}

// Create complete query
var xmlQuery = <queryDef operation="select" schema="nms:delivery"/>;
xmlQuery.appendChild(select);
xmlQuery.appendChild(where);

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## 고급 queryDef 메서드 {#advanced-methods}

`ExecuteQuery()` 외에도 queryDef에서는 고급 사용 사례에 맞는 특수 메서드를 여러 개 제공합니다.

### BuildQuery - 실행하지 않고 SQL 생성 {#build-query}

`BuildQuery()`을(를) 사용하여 SQL 문을 실행하지 않고 생성합니다. 이 기능은 외부 시스템에 대한 쿼리를 디버깅, 로깅 또는 전달하는 데 유용합니다.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
    </select>
    <where>
      <condition expr="@email IS NOT NULL"/>
    </where>
  </queryDef>
);

// Get the generated SQL
var sql = query.BuildQuery();
logInfo("Generated SQL: " + sql);
// Output: "SELECT iRecipientId, sEmail FROM NmsRecipient WHERE sEmail IS NOT NULL"
```

[BuildQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQuery.html?lang=ko){target="_blank"}에 대해 자세히 알아보세요.

### BuildQueryEx - 형식 문자열로 SQL 가져오기 {#build-query-ex}

`BuildQueryEx()`은(는) SQL 쿼리와 `sqlSelect()` 함수와 호환되는 형식 문자열을 모두 반환합니다.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
      <node expr="@firstName"/>
    </select>
  </queryDef>
);

var [sql, format] = query.BuildQueryEx();
logInfo("SQL: " + sql);
logInfo("Format: " + format);

// Use with sqlSelect
var results = sqlSelect(format, sql);
```

[BuildQueryEx](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQueryEx.html?lang=ko){target="_blank"}에 대해 자세히 알아보세요.

### SelectAll - 선택할 모든 필드를 추가합니다. {#select-all}

`SelectAll()` 메서드는 스키마의 모든 필드를 SELECT 절에 자동으로 추가하므로 각 필드를 수동으로 나열할 수 없습니다.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Add all fields to the select
query.SelectAll(false);

var result = query.ExecuteQuery();
// Result contains all recipient fields
```

[모두 선택](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-SelectAll.html?lang=ko){target="_blank"}에 대해 자세히 알아보세요.

### 갱신 - 일괄 갱신 레코드 {#mass-update}

`Update()` 메서드를 사용하면 각 레코드를 개별적으로 로드하지 않고 쿼리 조건과 일치하는 레코드에 대한 대량 업데이트를 수행할 수 있습니다.

```javascript
// Mass update example: set a field value for all matching records
var updateQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "update",
    where: {
      condition: [{expr: "@country = 'US'"}]
    },
    set: {
      node: [{expr: "@blackList", value: "0"}]
    }
  }
});

// Execute mass update
updateQuery.Update();
logInfo("Mass update completed");
```

>[!CAUTION]
>
>대량 업데이트는 where 절과 일치하는 모든 레코드에 영향을 줍니다. 항상 선택 쿼리를 사용하여 where 조건을 먼저 테스트하여 영향을 받을 레코드를 확인합니다.

[업데이트](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-Update.html?lang=ko){target="_blank"}에 대해 자세히 알아보세요.

### GetInstanceFromModel - 쿼리 템플릿 인스턴스 {#get-instance-from-model}

`GetInstanceFromModel()`을(를) 사용하여 템플릿에서 만든 인스턴스에서 데이터를 검색합니다.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
    </select>
    <where>
      <condition expr="@isModel = 1"/>
    </where>
  </queryDef>
);

// Get instance data from template
var instance = query.GetInstanceFromModel("nms:delivery");
```

[GetInstanceFromModel](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-GetInstanceFromModel.html?lang=ko){target="_blank"}에 대해 자세히 알아보세요.

## 일괄 처리 작업 {#batch-operations}

여러 레코드를 일괄적으로 처리하여 성능을 향상시킵니다.

**게재 레이블 일괄 업데이트:**

```javascript
// Query all deliveries to update
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema,
    operation: 'select', 
    lineCount: 999999999,
    select: { 
      node: [{expr: '@id'}]
    },
    where: {
      condition: [{expr: "@label LIKE '%OLD%'"}]
    }
  }
});

var records = query.ExecuteQuery();

// Process each record
for each(var record in records.getElements()) {
  var delivery = NLWS.nmsDelivery.load(record.$id);
  var oldLabel = delivery.label.toString();
  var newLabel = oldLabel.replace(/OLD/g, 'NEW');
  
  logInfo("Updating: " + oldLabel + " => " + newLabel);
  
  delivery.label = newLabel;
  delivery.save();
}

logInfo("Updated " + records.getElements().length + " deliveries");
```

## 원시 SQL 실행 {#raw-sql}

복잡한 작업의 경우 원시 SQL을 직접 실행할 수 있습니다.

**매개 변수가 있는 SQL 실행:**

```javascript
var dbEngine = instance.engine;

// Using parameterized query (recommended)
dbEngine.exec(
  "UPDATE NmsUserAgentStats SET iVisitorsOfTheDay=$(l) WHERE tsDate=$(dt)", 
  visitorCount,
  Format.parseDateTimeInter(dateString)
);
```

**sqlSelect를 사용한 쿼리:**

```javascript
// Execute SELECT query and parse results
var xml = sqlSelect(
  "collection,@id,@email", 
  "SELECT iId as id, sEmail as email FROM " + vars.tableName + " WHERE iStatus = 1"
);

logInfo(xml.toXMLString()); // "<select><collection id="1" email="..."/></select>"

for each(var record in xml.collection) {
  logInfo('ID: ' + record.@id + ', Email: ' + record.@email);
  
  // Load full object if needed
  if (vars.targetSchema == "nms:recipient") {
    var recipient = NLWS.nmsRecipient.load(record.@id);
    recipient.lastName = recipient.lastName.toUpperCase();
    recipient.save();
  }
}
```

>[!CAUTION]
>
>원시 SQL 사용 시:
>
>* 항상 사용자 입력을 확인하고 기밀 유지
>* `$(sz)`, `$(l)`, `$(dt)` 등으로 매개 변수가 있는 쿼리를 사용합니다.
>* [FFDA 배포](../architecture/enterprise-deployment.md)의 로컬 데이터베이스와 클라우드 데이터베이스 간의 차이점에 유의하십시오

## 모범 사례 {#best-practices}

queryDef 및 NLWS 메서드를 사용하여 작업하는 경우:

* **대규모 데이터 세트에 대한 워크플로우 사용** - QueryDef은 대량 데이터 처리를 위해 디자인되지 않았습니다. 레코드가 1,000개가 넘는 데이터 세트의 경우 수백만 개의 행을 효율적으로 처리할 수 있는 워크플로우를 사용합니다. 자세한 내용은 [Campaign SDK 설명서](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}를 참조하세요
* **매개 변수가 있는 쿼리 사용** - SQL 삽입을 방지하려면 항상 `$(sz)`과(와) 함께 바인딩된 매개 변수(`$(l)`, `sqlExec`)를 사용하십시오.
* **명시적 제한을 설정** - `lineCount`을(를) 사용하여 결과 크기를 제어하십시오. Campaign의 기본 제한은 컨텍스트에 따라 다릅니다(200~10,000개의 레코드)
* **페이지 매김이 있는 orderBy 사용** - `orderBy` 및 `startLine`을(를) 사용할 때 항상 `lineCount` 절을 포함하여 페이지 매김을 일관되게 유지하세요.
* **getIfExists 사용** - 예외가 발생하지 않도록 레코드가 없는 경우 `operation: "getIfExists"`을(를) 사용합니다.
* **열거형에 대해 분석 사용** - 사용자에게 친숙한 열거형 이름 및 레이블을 가져올 노드를 선택하려면 `analyze: true`을(를) 추가하십시오.
* **쿼리 최적화** - 결과 집합을 제한하려면 적절한 `where` 조건을 추가하십시오.
* **일괄 처리** - 메모리 문제와 시간 제한을 방지하기 위해 여러 레코드를 일괄적으로 처리합니다.
* **FFDA 인식** - [엔터프라이즈(FFDA) 배포](../architecture/enterprise-deployment.md)에서는 [!DNL Campaign]이(가) 두 개의 데이터베이스에서 작동한다는 것을 알아보세요.



## 실용적인 사용 사례 {#use-cases}

### 디버그 및 로그 쿼리 {#debug-queries}

실행 전에 생성된 SQL을 검사하려면 `BuildQuery()`을(를) 사용합니다.

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@blackList = 0"}] }
  }
});

// Log the SQL for debugging
var sql = query.BuildQuery();
logInfo("About to execute: " + sql);

// Now execute
var results = query.ExecuteQuery();
```

### SelectAll을 사용하여 레코드 복제 {#duplicate-record}

레코드를 복제할 때 `SelectAll()`을(를) 사용하여 모든 필드를 복사합니다.

```javascript
// Query the original record
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="get">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Select all fields for duplication
query.SelectAll(true); // true indicates duplication mode

var original = query.ExecuteQuery();

// Create a new delivery from the original
var newDelivery = NLWS.nmsDelivery.create(original);
newDelivery.label = original.@label + " (Copy)";
newDelivery.save();
```

### 대량 업데이트 전 유효성 검사 {#validate-mass-update}

대량 업데이트를 수행하기 전에 항상 영향을 받는 레코드를 미리 봅니다.

```javascript
// Step 1: Preview what will be updated
var previewQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@country = 'US' AND @blackList = 1"}] }
  }
});

var preview = previewQuery.ExecuteQuery();
var count = preview.getElementsByTagName("recipient").length;
logInfo("About to update " + count + " recipients");

// Step 2: If count looks correct, proceed with mass update
if (count > 0 && count < 10000) {
  sqlExec("UPDATE NmsRecipient SET iBlackList = 0 WHERE sCountryCode = 'US' AND iBlackList = 1");
  logInfo("Mass update completed for " + count + " recipients");
} else {
  logWarning("Update cancelled: count is " + count);
}
```

## 쿼리 정의 구문 참조 {#querydef-reference}

`queryDef` 개체의 전체 구조:

```javascript
{
  queryDef: {
    schema: 'nms:recipient',           // Required: target schema
    operation: 'select',                // select|get|getIfExists|count
    lineCount: 100,                    // Maximum records to return
    startLine: 0,                      // Offset for pagination
    select: {
      node: [
        {
          expr: '@id',                 // XPath expression
          alias: '@myAlias',           // Optional alias
          label: 'ID',                 // Optional label
          groupBy: 'true',             // Group by this field
          noSqlBind: 'true'            // No SQL binding on constants
        }
      ]
    },
    where: {
      condition: [
        {
          expr: '@email IS NOT NULL',  // Condition expression
          boolOperator: 'AND',         // AND|OR
          setOperator: 'EXISTS',       // EXISTS|NOT EXISTS|IN|NOT IN
          enabledIf: '',               // Enabling condition
          ignore: false,               // Ignore this condition
          sql: '',                     // Native SQL expression
          'filter-name': ''            // Predefined filter name
        }
      ]
    },
    orderBy: {
      node: [
        {
          expr: '@lastModified',       // Field to sort by
          sortDesc: 'true'             // true for DESC, false for ASC
        }
      ]
    },
    groupBy: {
      node: [
        {expr: '@country'}             // Group by field
      ]
    }
  }
}
```

## 관련 항목 {#related-topics}

* [Campaign API 시작](api.md)
* [Campaign JavaScript SDK - 쿼리 API](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}
* [queryDef API 참조](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html?lang=ko){target="_blank"}
* [Campaign JSAPI 설명서](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=ko){target="_blank"}
* [스키마 작업](schemas.md)
* [쿼리 편집기 작업](../start/query-editor.md)

