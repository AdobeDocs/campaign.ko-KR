---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 7%
---
# SubmitNotification

시나리오에서 알림 만들기 및 제출.

```text
Number notificationId = SubmitNotification ( String scenarioName, XML target )
```

## 매개변수

템플릿의 **scenarioName** 내부 이름

시나리오의 모집단을 대체하는 **target** 게재 대상 모집단

## 반환 값

**notificationId** 알림 식별자

## 비고

경고: 이 API는 대량의 데이터를 관리하거나 실시간으로 작동하도록 빌드되지 않았습니다. 분당 최대 여러 개의 호출을 처리하도록 개발되었습니다. SubmitNotification은 게재 분석 중에 스레드를 차단합니다. 몇 초 정도 소요될 수 있습니다. target 매개 변수는 게재 대상을 지정합니다. 템플릿에 지정된 대상을 재정의합니다. 데이터베이스의 대상에 전달하려면 대상 요소는 다음 구문을 사용합니다.

```xml
<delivery>
  <targets>
    <deliveryTarget>
      <targetPart type='query' exclusion='false' ignoreDeleteStatus='false'>
        <where>
          <condition expr='[@folder-id] = 1050'/>
        </where>
      </targetPart>
    </deliveryTarget>
  </targets>
</delivery>
```

파일의 대상에 게재하려면 다음 작업을 수행하십시오.

```xml
<delivery>
  <targets>
    <deliveryFile upload='false'>
      <name>c:/tmp/myFile.csv</name>
    </deliveryFile>
  </targets>
</delivery>
```

대상을 명시적으로 정의할 수 있습니다(실제로는 타겟으로 사용되는 파일의 콘텐츠).

```xml
<delivery>
  <targets fromExternalSource='true'>
    <externalSource>MsgId|ClientId|Title|Name|FirstName|Mobile|Email|Market_segment|Product_propensity1|Product_propensity2|Product_propensity3|Product_propensity4|Support_Number|Amount|Threshold1|
                    000001234|M.|Martin|Peter|0650201020|pmartin@neolane.com|1|A1|A2|A3|A4|E12|120000|100000
    </externalSource>
  </targets>
</delivery>
```

템플릿에 정의된 대상을 &quot;\_keepTemplateTarget&quot; 속성으로 유지할 수도 있습니다.

```xml
<delivery>
  <targets _keepScenarioTarget='true'/>
</delivery>
```

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

예
