---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 3%
---
# EvaluateContent

주문에 연결된 게재 콘텐츠를 평가합니다. 이 평가는 운영자 권한을 사용하여 주문할 때 로컬 캠페인이 생성되기 전에 수행됩니다.

```text
XML result = EvaluateContent ( XML order, Number deliveryId, String contentType, Number seedMemberId )
```

## 매개변수

주문 정보가 포함된 **order** 요소입니다.

**deliveryId** 평가할 게재 ID.

**contentType** 반환할 콘텐츠 유형(전자 메일의 경우 html 또는 텍스트, 다른 채널의 경우 빈 문자열).

콘텐츠 개인화에 사용되는 **seedMemberId** 시드 주소 ID입니다.

## 반환 값

**결과** 평가된 콘텐츠.

## 기능

**스키마:** [nms:localOrder](s-nms-localorder.md)

**정적:**

예
