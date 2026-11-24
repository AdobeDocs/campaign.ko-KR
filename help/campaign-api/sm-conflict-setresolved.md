---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 5%
---
# SetResolved

더 이상 충돌이 없는 엔터티를 선언합니다.

```text
SetResolved ( String conflictId )
```

## 매개변수

**conflictId** 충돌 식별자.

## 반환 값

없음.

## 비고

모든 충돌이 해결되면 이 방법을 사용하여 엔티티를 원래 위치에 되돌릴 수 있습니다. 이 메서드를 호출하기 전에 충돌하는 모든 특성 및 요소를 해결해야 합니다.

## 기능

**스키마:** [xtk:conflict](s-xtk-conflict.md)

**정적:**

예
