---
solution: Campaign Classic
product: campaign
title: 캠페인 스키마 확장
description: 캠페인 스키마를 확장하는 방법 알아보기
translation-type: tm+mt
source-git-commit: 8e90eb762a6e08077270d4f5852bfc37ac783122
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 1%

---

# 스키마 확장{#extend-schemas}

기술 사용자는 다음과 같은 구현 요구에 맞게 캠페인 데이터 모델을 사용자 정의할 수 있습니다.기존 스키마에 요소를 추가하거나 스키마의 요소를 수정하거나 요소를 삭제합니다.

캠페인 데이터 모델을 사용자 정의하는 주요 단계는 다음과 같습니다.

1. 확장 스키마 만들기
1. 캠페인 데이터베이스 업데이트
1. 입력 양식 적용

>[!CAUTION]
>내장 스키마는 직접 수정해서는 안 됩니다. 내장된 스키마를 조정해야 하는 경우 스키마를 확장해야 합니다.

: 전구:Campaign 내장 테이블 및 그 상호 작용에 대한 자세한 내용은 [이 페이지](datamodel.md)를 참조하십시오.

스키마를 확장하려면 아래 절차를 따르십시오.

1. 탐색기에서 **[!UICONTROL Administration > Configuration > Data schemas]** 폴더로 이동합니다.
1. **새로 만들기** 단추를 클릭하고 **[!UICONTROL Extend the data in a table using an extension schema]**&#x200B;를 선택합니다.

   ![](assets/extend-schema-option.png)

1. 확장 및 선택할 내장 스키마를 식별합니다.

   ![](assets/extend-schema-select.png)

   규칙에 따라 확장 스키마의 이름을 내장 스키마와 동일하게 지정하고 사용자 정의 네임스페이스를 사용합니다.

   ![](assets/extend-schema-validate.png)

1. 스키마 편집기에서 컨텍스트 메뉴를 사용하여 필요한 요소를 추가하고 저장합니다.

   ![](assets/extend-schema-edit.png)

   아래 예에서 MembershipYear 속성을 추가하고 성 이름에 대해 길이 제한을 설정하고(이 제한은 기본 이름을 덮어씁니다) 기본 스키마에서 생년월일을 제거합니다.

   ![](assets/extend-schema-sample.png)

   ```
   <srcSchema created="YY-MM-DD" desc="Recipient table" extendedSchema="nms:recipient"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient" lastModified="YY-MM-DD"
           mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:srcSchema">
    <element desc="Recipient table" img="nms:recipient.png" label="Recipients" labelSingular="Recipient"
          name="recipient">
   <attribute label="Member since" name="MembershipYear" type="long"/>
   <attribute length="50" name="lastName"/>
   <attribute _operation="delete" name="birthDate"/>
   </element>
   </srcSchema>
   ```
1. **[!UICONTROL Structure]** 탭에서 스키마 구조 업데이트를 확인하려면 Campaign의 연결을 끊거나 다시 연결하십시오.

   ![](assets/extend-schema-structure.png)

1. 데이터베이스 구조를 업데이트하여 변경 사항을 적용합니다. [자세히 알아보기](update-database-structure.md)

1. 변경 사항이 데이터베이스에 구현되면 수신자 입력 양식을 조정하여 변경 사항을 표시할 수 있습니다. [자세히 알아보기](forms.md)
