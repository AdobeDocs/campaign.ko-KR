---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 29%
---
# generateRegisterHookScript

“appSubscriptionRcp”의 “등록” 이벤트 중에 호출할 확장 스크립트를 생성합니다.

```text
String JSScriptStr = generateRegisterHookScript ( XML additionalXmlNodes )
```

## 매개변수

추가 매개 변수와 대상 매핑 필드 간의 연결이 포함된 **additionalXmlNodes** XML 노드입니다.

## 반환 값

대상 매핑의 필드에 추가 매개 변수를 연결할 수 있는 **JSScriptStr** JS 스크립트입니다.

## 기능

**스키마:** [nms:mobileApp](s-nms-mobileapp.md)

**정적:**

예
