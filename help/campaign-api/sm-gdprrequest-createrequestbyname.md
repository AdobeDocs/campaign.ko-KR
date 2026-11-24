---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 29%
---
# CreateRequestByName

네임스페이스 내부 이름을 사용하여 새 GDPR 요청을 만듦

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending )
```

## 매개변수

**namespaceName** 네임스페이스 내부 이름

**reconciliationValue** 조정 값

**type** 조정 값

데이터를 삭제하기 전에 **confirmDeletePending** 요청 확인

## 반환 값

새로 만든 요청의 **id** ID

## 기능

**스키마:** [nms:gdprRequest](s-nms-gdprrequest.md)

**정적:**

예
