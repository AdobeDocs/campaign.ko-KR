---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 38%
---
# LoadExpandedContents

종속성이 포함된 전처리의 구성 요소 목록을 로드합니다(개인화 블록, 옵션, 추가 스크립트 오브젝트 등).

```text
XML material = delivery.LoadExpandedContents ( String ids ) const
```

## 매개변수

**ids** 쉼표로 구분된 구성 요소 식별자 목록(예: &#39;option\|NmsServer\_URL\|text,includeView\|UnsubscriptionLink\|html&#39;).

## 반환 값

**material** 내용을 &#39;material&#39; 요소로 반환합니다.

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

아니요

**Const:**

예

**키만:**

아니요
