---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 5%
---
# getAsModel

```text
XML parentOut = getAsModel ( String refIdName, Number refIdValue, XML selection, XML parentIn )
```

## 매개변수

연결할 엔터티의 식별자(예: &#39;delivery-id&#39;)가 포함된 **refIdName** 특성

연결할 엔터티의 **refIdValue** 식별자(&#39;refIdName&#39;의 값)

선택한 템플릿 식별자를 포함하는 **선택** 요소

기존 시드 주소를 포함하는 **parentIn** 요소

## 반환 값

**parentOut** 새 템플릿이 추가된 요소를 반환합니다.

## 기능

**스키마:** [nms:seedMember](s-nms-seedmember.md)

**정적:**

예
