---
title: 캠페인 스키마 필터링
description: Campaign 스키마를 필터링하는 방법 알아보기
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: e8ad021c-ce2e-4a74-b9bf-a989d8879fd1
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 2%

---

# 스키마 필터링{#filter-schemas}

## 시스템 필터 {#system-filters}

권한에 따라 특정 사용자에 대한 스키마 액세스를 필터링할 수 있습니다. 시스템 필터를 사용하면 **readAccess** 및 **writeAccess** 매개 변수를 사용하여 스키마에 설명된 엔터티의 읽기 및 쓰기 권한을 관리할 수 있습니다.

>[!NOTE]
>
>이 제한은 기술 사용자가 아닌 사용자에게만 적용됩니다. 관련 권한이 있거나 워크플로우를 사용하는 기술 사용자는 데이터를 검색하고 업데이트할 수 있습니다.

* **readAccess**: 스키마 데이터에 대한 읽기 전용 액세스를 제공합니다.

  **경고** - 연결된 모든 테이블은 동일한 제한으로 설정해야 합니다. 이 구성은 성능에 영향을 줄 수 있습니다.

* **writeAccess**: 스키마 데이터에 대한 쓰기 액세스를 제공합니다.

이러한 필터는 스키마의 기본 **요소** 수준에서 입력되며, 다음 예제와 같이 액세스를 제한하도록 구성할 수 있습니다.

* 쓰기 권한 제한

  여기서 필터는 ADMINISTRATION 권한이 없는 연산자에 대해 스키마에 대한 WRITE 권한을 허용하지 않는 데 사용됩니다. 즉, 관리자만 이 스키마에서 설명한 엔티티에 대한 쓰기 권한을 갖습니다.

  ```
  <sysFilter name="writeAccess">      
   <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
  </sysFilter>
  ```

* 읽기 및 쓰기 권한 제한:

  여기서 필터는 모든 연산자에 대해 스키마에 대한 읽기 및 쓰기 권한을 모두 허용하지 않는 데 사용됩니다. 식 &quot;$(loginId)로 표시되는 **internal** 계정만!=0&quot;에는 이러한 권한이 있습니다.

  ```
  <sysFilter name="readAccess"> 
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  
  <sysFilter name="writeAccess">  
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  ```

  조건을 정의하는 데 사용할 수 있는 **expr** 특성 값은 TRUE 또는 FALSE입니다.

>[!NOTE]
>
>필터를 지정하지 않으면 모든 연산자는 스키마에 대한 읽기 및 쓰기 권한을 갖게 됩니다.

## Protect 기본 스키마

기본적으로 기본 제공 스키마는 관리 권한이 있는 연산자에 대한 쓰기 권한으로만 액세스할 수 있습니다.

* ncm:게시
* nl:monitoring
* nms:calendar
* xtk:builder
* xtk:connections
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
* xtk:schema
* xtk:scriptContext
* xtk:specFile
* xtk:sql
* xtk:sqlSchema
* xtk:srcSchema
* xtk:strings
* xtk:xslt

>[!CAUTION]
>
>**xtk:sessionInfo** 스키마에 대한 읽기 및 쓰기 권한은 Adobe Campaign 인스턴스의 내부 계정에서만 액세스할 수 있습니다.

## 기본 제공 스키마의 시스템 필터 수정

기본 제공 스키마는 이전 버전과의 호환성 문제를 방지하기 위해 보호됩니다. Adobe은 최적의 보안을 보장하기 위해 기본 스키마 매개 변수를 수정하지 않는 것을 권장합니다.

그러나 특정 컨텍스트에서는 기본 제공 스키마의 시스템 필터를 수정해야 할 수 있습니다. 이렇게 하려면 아래 단계를 수행합니다.

1. 기본 제공 스키마에 대한 확장을 만들거나 기존 확장을 엽니다.
1. 기본 요소의 자식 요소 **`<sysfilter name="<filter name>" _operation="delete"/>`**&#x200B;을(를) 추가하여 기본 제공 스키마의 같은 아래에 있는 필터를 무시합니다.
1. [시스템 필터](#system-filters) 섹션에 자세히 설명된 대로 새 필터를 추가할 수 있습니다.
