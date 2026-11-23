---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '27'
ht-degree: 37%
---
# RegisterGroup

선택한 수신자를 목록에 추가

```text
RegisterGroup ( XML groupList, XML recipientList, Boolean register )
```

## 매개변수

**groupList** 목록

**recipientList** 수신자 목록

받는 사람 **등록** 구독/구독 취소

## 반환 값

없음.

## 예제

```javascript
//List
var entity = <entityList><key value="24447964"/>
              <where>
                <condition enabledIf="" expr="@id = 24447964"/>
              </where>
            </entityList>
 
//Recipient
var choice = <choiceList><key value="18995462"/>
              <where>
                <condition enabledIf="" expr="@id = 18995462"/>
              </where>
            </choiceList>
nms.recipient.RegisterGroup(entity,choice,true)
        
```

## 기능

**스키마:** [nms:recipient](s-nms-recipient.md)

**정적:**

예
