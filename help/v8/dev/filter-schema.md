---
title: 캠페인 스키마 필터링
description: Campaign 스키마를 필터링하는 방법 알아보기
exl-id: e8ad021c-ce2e-4a74-b9bf-a989d8879fd1
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# 스키마 필터링{#filter-schemas}

## 시스템 필터 {#system-filters}

사용 권한에 따라 특정 사용자에 대한 스키마 액세스를 필터링할 수 있습니다. 시스템 필터를 사용하여 스키마에 자세히 나와 있는 엔티티의 읽기 및 쓰기 권한을 관리할 수 있습니다 **readAccess** 및 **writeAccess** 매개 변수.

>[!NOTE]
>
>이 제한 사항은 기술 전문가가 아닌 사용자만 적용됩니다. 관련 권한이 있거나 워크플로우를 사용하는 기술 사용자는 데이터를 검색하고 업데이트할 수 있습니다.

* **readAccess**: 스키마 데이터에 대한 읽기 전용 액세스 권한을 제공합니다.

   **경고** - 연결된 모든 테이블은 동일한 제한 사항으로 설정해야 합니다. 이 구성은 성능에 영향을 줄 수 있습니다.

* **writeAccess**: 스키마 데이터에 대한 쓰기 액세스를 제공합니다.

이러한 필터는 기본 **요소** 다음 예와 같이 스키마 및 수준의 레벨을 만들어 액세스를 제한할 수 있습니다.

* 쓰기 권한 제한

   여기서는 ADMINISTRATION 권한 없이 연산자에 대해 스키마에 대한 WRITE 권한을 허용하지 않는 데 필터를 사용합니다. 즉, 관리자만 이 스키마에서 설명하는 엔터티에 대한 쓰기 권한이 있습니다.

   ```
   <sysFilter name="writeAccess">      
    <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
   </sysFilter>
   ```

* 읽기 및 쓰기 권한 제한:

   여기서는 모든 연산자에 대해 스키마에 대한 읽기 및 쓰기 권한을 모두 허용하지 않는 데 필터를 사용합니다. 전용 **내부** 계정, &quot;$(loginId)!= 0&quot;에는 이러한 권한이 있습니다.

   ```
   <sysFilter name="readAccess"> 
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   
   <sysFilter name="writeAccess">  
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   ```

   가능한 **expr** 조건을 정의하는 데 사용되는 속성 값은 TRUE 또는 FALSE입니다.

>[!NOTE]
>
>필터를 지정하지 않으면 모든 연산자는 스키마에 대한 읽기 및 쓰기 권한을 갖습니다.

## Protect 기본 제공 스키마

기본적으로 내장 스키마에는 ADMINISTRATION 권한이 있는 연산자에 대한 WRITE 권한만 있으면 액세스할 수 있습니다.

* ncm:게시
* nl:모니터링
* nms:달력
* xtk:builder
* xtk:연결
* xtk:dbInit
* xtk:entityBackupNew
* xtk:entityBackupOriginal
* xtk:entityOriginal
* xtk:form
* xtk:funcList
* xtk:fusion
* xtk:image
* xtk:javascript
* xtk:jssp
* xtk:jst
* xtk:navtree
* xtk:operatorGroup
* xtk:package
* xtk:queryDef
* xtk:resourceMenu
* xtk:rights
* xtk:스키마
* xtk:scriptContext
* xtk:specFile
* xtk:sql
* xtk:sqlSchema
* xtk:srcSchema
* xtk:문자열
* xtk:xslt

>[!CAUTION]
>
>에 대한 읽기 및 쓰기 권한 **xtk:sessionInfo** 스키마는 Adobe Campaign 인스턴스의 내부 계정에서만 액세스할 수 있습니다.

## 기본 제공 스키마의 시스템 필터 수정

기본 제공 스키마는 이전 버전과의 호환성 문제를 방지하기 위해 보호됩니다. Adobe은 최적의 보안을 위해 기본 스키마 매개 변수를 수정하지 않는 것을 권장합니다.

그러나 특정 컨텍스트에서는 기본 제공 스키마의 시스템 필터를 수정해야 할 수 있습니다. 이렇게 하려면 아래 단계를 수행하십시오.

1. 기본 제공 스키마에 대한 확장을 만들거나 기존 확장을 엽니다.
1. 하위 요소 추가 **`<sysfilter name="<filter name>" _operation="delete"/>`** 기본 요소에서 기본 제공 스키마에서 동일한 아래에 있는 필터를 무시합니다.
1. 에 자세히 설명된 대로 새 필터를 추가할 수 있습니다. [시스템 필터](#system-filters) 섹션을 참조하십시오.
