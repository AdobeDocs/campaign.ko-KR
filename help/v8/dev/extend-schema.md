---
product: Adobe Campaign
title: Campaign 스키마 확장
description: Campaign 스키마를 확장하는 방법을 알아보십시오
source-git-commit: b11b42220dae7d0a878ba102523ee2825d6fb2e2
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# 스키마 확장{#extend-schemas}

기술 사용자는 구현의 요구 사항에 맞게 Campaign 데이터 모델을 사용자 지정할 수 있습니다.기존 스키마에 요소 추가, 스키마에서 요소 수정 또는 요소 삭제

Campaign 데이터 모델을 사용자 지정하는 주요 단계는 다음과 같습니다.

1. 확장 스키마 만들기
1. Campaign 데이터베이스 업데이트
1. 입력 양식 조정

>[!CAUTION]
>기본 제공 스키마를 직접 수정해서는 안 됩니다. 기본 제공 스키마를 조정해야 하는 경우, 확장을 확장해야 합니다.

[!DNL :bulb:] Campaign 기본 제공 테이블 및 상호 작용에 대한 자세한 내용은  [이 페이지](datamodel.md)를 참조하십시오. [이 페이지에서 새 스키마를 생성할 때 권장 사항을 참조하십시오](create-schema.md).

스키마를 확장하려면 아래 단계를 따르십시오.

1. 탐색기에서 **[!UICONTROL Administration > Configuration > Data schemas]** 폴더로 이동합니다.
1. **새로 만들기** 단추를 클릭하고 **[!UICONTROL Extend the data in a table using an extension schema]**&#x200B;를 선택합니다.

   ![](assets/extend-schema-option.png)

1. 확장할 기본 제공 스키마를 식별하고 선택합니다.

   ![](assets/extend-schema-select.png)

   규칙에 따라 확장 스키마의 이름을 기본 제공 스키마와 동일하게 지정하고 사용자 지정 네임스페이스를 사용합니다.  일부 네임스페이스는 내부용입니다. [자세히 알아보기](schemas.md#reserved-namespaces)

   ![](assets/extend-schema-validate.png)

1. 스키마 편집기에서 상황별 메뉴를 사용하여 필요한 요소를 추가하고 저장합니다.

   ![](assets/extend-schema-edit.png)

   아래 예에서는 **MembershipYear** 속성을 추가하고, 성 이름에 대한 길이 제한을 지정하고(이 제한은 기본 이름을 덮어씁니다) 기본 스키마에서 생년월일을 제거합니다.

   ![](assets/extend-schema-sample.png)

   ```
   <srcSchema created="YYYY-MM-DD" desc="Recipient table" extendedSchema="nms:recipient"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient" lastModified="YYYY-MM-DD"
           mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:srcSchema">
    <element desc="Recipient table" img="nms:recipient.png" label="Recipients" labelSingular="Recipient" name="recipient">
       <attribute label="Member since" name="MembershipYear" type="long"/>
       <attribute length="50" name="lastName"/>
       <attribute _operation="delete" name="birthDate"/>
   </element>
   </srcSchema>
   ```

1. Campaign에 연결을 끊고 다시 연결하여 **[!UICONTROL Structure]** 탭에서 스키마 구조 업데이트를 확인합니다.

   ![](assets/extend-schema-structure.png)

1. 데이터베이스 구조를 업데이트하여 변경 사항을 적용합니다. [자세히 알아보기](update-database-structure.md)

1. 변경 사항이 데이터베이스에 구현되면 수신자 입력 양식을 조정하여 변경 사항을 표시할 수 있습니다. [자세히 알아보기](forms.md)
