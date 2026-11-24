---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 27%
---
# 테스트 계산 필드

스크립트에 저장된 샘플 라인을 사용하여 계산된 필드를 테스트합니다.

```text
XML calcFieldValues = TestCalcField ( XML dataTransferStep, String calcFieldName )
```

## 매개변수

계산된 필드가 정의된 **dataTransferStep** 데이터 전송 단계

**calcFieldName** 테스트할 계산된 필드

## 반환 값

**calcFieldValues** 각 샘플 라인(calcFieldValues/line) 및 필드 이름(calcFieldValues/@name)에 대한 값 목록을 반환합니다.

## 기능

**스키마:** [xtk:dataTransfer](s-xtk-datatransfer.md)

**정적:**

예
