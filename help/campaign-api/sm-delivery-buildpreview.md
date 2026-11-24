---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 34%
---
# BuildPreview

(외부 모드에) 게재 콘텐츠 또는 출력 파일 라인의 미리보기 기능이 내장되어 있습니다.

```text
[ XML preview, XML queryResult ] = delivery.BuildPreview ( XML params ) const
```

## 매개변수

**매개 변수** 받는 사람 필터링 조건(@filter = &#39;@id = 5673&#39;), 콘텐츠 식별자(@content = &#39;html&#39;, &#39;text&#39;, &#39;sms&#39;, &#39;webContent1&#39;, &#39;outputFile&#39;...), @targetPart = 1345686...

## 반환 값

**미리 보기** 생성된 미리 보기의 매개 변수를 모두 반환합니다.

**queryResult** 미리 보기를 계산하기 위해 로드된 데이터를 반환합니다.

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

아니요

**Const:**

예

**키만:**

아니요
