---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 17%
---
# SubmitFromModel

템플릿에서 작업 제출

```text
Number jobId = SubmitFromModel ( String schema, String where, String methodName, XML diff, Boolean async )
```

## 매개변수

**스키마** 작업 템플릿 스키마

**where** 템플릿 선택 식

호출할 메서드의 **methodName** 이름

템플릿에 추가할 **diff** XML 콘텐츠

**비동기** 비동기 작업 제출을 수행합니다.

## 반환 값

방금 만든 작업의 **jobId** 식별자

## 기능

**스키마:** [xtk:job](s-xtk-job.md)

**정적:**

예
