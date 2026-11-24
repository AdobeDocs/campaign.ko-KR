---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '27'
ht-degree: 14%
---
# evaluateTemplate

JavaScript 템플릿을 평가합니다(&lt;%= ... %>).

```text
evaluateTemplate (template)
```

## 매개변수

**템플릿** 평가할 템플릿입니다.

## 반환 값

&lt;%와 %> 사이의 식을 대체한 후의 문자열입니다.

## 비고

예:

```javascript
      vars.filename = evaluateTemplate(activity.filename)
```

## 기능

**다음 위치에서 사용 가능:**

* 워크플로
