---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 6%
---
# CreateRequestByName

네임스페이스 내부 이름을 사용하여 새 개인 정보 보호 요청을 만듦

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending Number regulation )
```

## 매개변수

**namespaceName** 네임스페이스 내부 이름

**reconciliationValue** 조정 값

**type** 조정 값

데이터를 삭제하기 전에 **confirmDeletePending** 요청 확인

다음 값이 있는 **regulation** 규정 유형:

```xml
           
               <value label="GDPR" name="gdpr" value="1"/>
            <value label="CCPA" name="ccpa" value="2"/>
            <value label="PDPA" name="pdpa" value="3"/>
            <value label="LGPD" name="lgpd" value="4"/>
           
           
```

## 반환 값

새로 만든 요청의 **id** ID

## 기능

**스키마:** [nms:privacyRequest](s-nms-privacyrequest.md)

**정적:**

예
