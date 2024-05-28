---
title: 데이터 패키지 작업
description: 데이터 패키지 작업
feature: Data Management, Package Export/Import
role: Developer
level: Intermediate, Experienced
source-git-commit: 933c266febdc293dccdf9b7383d94d7a5dce22bc
workflow-type: tm+mt
source-wordcount: '1941'
ht-degree: 0%

---

# 데이터 패키지를 사용한 작업{#data-packages}

## 패키지 시작 {#gs-data-packages}

데이터 패키지를 사용하여 플랫폼 사용자 지정 설정 및 데이터를 내보내고 가져올 수 있습니다. 패키지에는 필터링되거나 필터링되지 않은 다양한 유형의 구성 및 구성 요소가 포함될 수 있습니다.

Campaign 데이터 패키지에서 Adobe Campaign 데이터베이스의 엔터티가 XML 파일로 표시됩니다. 패키지에서 각 엔티티는 모든 데이터로 표시됩니다.

의 원칙 **데이터 패키지** 는 데이터 구성을 내보내고 다른 Adobe Campaign 환경에 통합하는 것입니다. 에서 일관된 데이터 패키지 세트를 유지 관리하는 방법을 알아봅니다. [섹션](#data-package-best-practices).

### 패키지 유형 {#types-of-packages}

Adobe Campaign에서 사용자 패키지, 플랫폼 패키지 및 관리 패키지의 세 가지 유형의 패키지를 사용하여 작업할 수 있습니다.

* A **사용자 패키지** 내보낼 엔티티 목록을 선택할 수 있습니다. 이 유형의 패키지는 종속성을 관리하고 오류를 확인합니다.
* A **플랫폼 패키지** 스키마, JavaScript 코드 등 추가된 모든 기술 리소스(비표준)를 포함합니다.
* An **관리 패키지** 추가된 모든 템플릿 및 비즈니스 개체(비표준)(템플릿, 라이브러리 등)를 포함합니다.

>[!CAUTION]
>
>다음 **platform** 및 **admin** 패키지에는 내보낼 미리 정의된 엔티티 목록이 포함되어 있습니다. 각 엔티티는 필터링 조건에 연결되어 만들어진 패키지의 기본 리소스를 제거할 수 있습니다.

## 데이터 구조 {#data-structure}

데이터 패키지에 대한 설명은 의 문법을 준수하는 구조화된 XML 문서입니다 **xrk:navtree** 아래 예와 같은 데이터 스키마:

```xml
<package>
  <entities schema="nms:recipient">
    <recipient email="john.smith@adobe.com" lastName="Smith" firstName="John">      
      <folder _operation="none" name="nmsRootFolder"/>      
      <company _operation="none" name="Adobe"/>
    </recipient>
  </entities>
  <entities schema="sfa:company">
    <company name="Adobe">
      <location city="London" zipCode="W11 2BQ"/>
    </company>
  </entities>
</package>
```

XML 문서는 다음으로 시작하고 끝나야 합니다 `<package>` 요소를 생성하지 않습니다. 임의 `<entities>` 뒤에 오는 요소는 문서 유형별로 데이터를 배포합니다. An `<entities>` 요소는에 입력한 데이터 스키마 형식으로 패키지의 데이터를 포함합니다. **스키마** 특성. 패키지의 데이터에는 자동 생성 키( )와 같이 기본 간에 호환되지 않는 내부 키가 포함되지 않아야 합니다.**autopk** 선택 사항).

이 예에서 의 조인은 `folder` 및 `company` 링크는 대상 테이블에서 소위 &quot;높은 수준&quot; 키로 대체되었습니다.

```xml
<recipient>
  <folder _operation="none" name="nmsRootFolder"/>
  <company _operation="none" name="Adobe"/>
</recipient>
```

다음 `operation` 값이 있는 속성 `none` 조정 링크를 정의합니다.

데이터 패키지는 모든 텍스트 편집기에서 수동으로 빌드할 수 있습니다. XML 문서의 구조가 `xtk:navtree` 데이터 스키마. 클라이언트 콘솔에는 데이터 패키지 내보내기 및 가져오기 모듈이 있습니다.

## 패키지 내보내기 {#export-packages}

패키지를 다음과 같은 세 가지 방법으로 내보낼 수 있습니다.

* 사용 **[!UICONTROL Package Export]** 단일 패키지의 개체 집합을 내보내는 도우미. [자세히 알아보기](#export-a-set-of-objects-in-a-package)
* 를 내보내려면 **단일 오브젝트**, 마우스 오른쪽 버튼으로 클릭하고 를 선택합니다. **[!UICONTROL Actions > Export in a package]**.
* 사용 **패키지 정의** 나중에 패키지에서 내보낼 개체를 추가하는 패키지 구조를 만듭니다. [자세히 알아보기](#manage-package-definitions)

패키지를 내보내고 나면 해당 패키지와 추가된 모든 엔티티를 다른 Campaign 인스턴스로 가져올 수 있습니다.

### 패키지의 개체 집합 내보내기 {#export-a-set-of-objects-in-a-package}

데이터 패키지의 개체 집합을 내보내려면 다음 단계를 수행합니다.

1. 를 통해 패키지 내보내기 도우미로 이동 **[!UICONTROL Tools > Advanced > Export package...]** 탐색기의 메뉴입니다.
1. 다음 항목 선택 [패키지 유형](#types-of-packages).

   ![](assets/package_type.png)

1. 다음을 클릭합니다. **추가** 패키지로 내보낼 엔티티를 선택하는 버튼입니다.

   >[!CAUTION]
   >
   >를 내보내는 경우 **[!UICONTROL Offer category]**, **[!UICONTROL Offer environment]**, **[!UICONTROL Program]** 또는 **[!UICONTROL Plan]** 폴더를 입력하세요. 폴더를 선택하지 마십시오. **xtk:folder** 데이터가 손실될 수 있습니다. 폴더에 해당하는 엔티티를 선택합니다. **nms:offer범주** 오퍼 범주의 경우 **nms:offer환경** 오퍼 환경의 경우 **nms:program** 프로그램 및 **nms:plan** 계획용입니다.

   종속성 메커니즘은 엔티티 내보내기 시퀀스를 제어합니다. 자세한 내용은 다음을 참조하십시오. [종속성 관리](#managing-dependencies).

1. 클릭 **[!UICONTROL Next]** 추출할 문서 유형에 필터 쿼리를 정의합니다. 데이터 추출을 위해 필터링 절을 구성해야 합니다.

   >[!NOTE]
   >
   >쿼리 편집기는에 표시됩니다. [이 섹션](../../automation/workflow/query.md).

1. 클릭 **[!UICONTROL Next]** 내보낸 데이터의 정렬 순서를 선택합니다.

1. 추출할 데이터를 미리 보고 구성을 확인합니다.

1. 패키지 내보내기 도우미의 마지막 페이지를 사용하여 내보내기를 시작할 수 있습니다. 데이터는 다음에 표시된 파일에 저장됩니다 **[!UICONTROL File]** 필드.

### 종속성 관리 {#manage-dependencies}

내보내기 프로세스는 내보낸 다양한 요소 간의 링크를 추적합니다. 이 메커니즘은 다음 두 가지 규칙으로 정의됩니다.

* 이 있는 링크에 연결된 오브젝트 `own` 또는 `owncopy` 형식 무결성은 내보낸 개체와 동일한 패키지로 내보내집니다.
* 이 있는 링크에 연결된 오브젝트 `neutral` 또는 `define` 형식 무결성(정의된 링크)은 별도로 내보내야 합니다.

>[!NOTE]
>
>스키마 요소에 연결된 무결성 유형은에 정의되어 있습니다. [이 페이지](database-links.md).

#### 캠페인 내보내기 {#export-a-campaign}

아래는 캠페인을 내보내는 방법의 예입니다. 내보낼 마케팅 캠페인에는 다음이 포함됩니다.
* a `MyTask`작업
* a `campaignWorkflow` 다음 폴더의 워크플로: **[!UICONTROL Administration > Production > Technical workflows > Campaign processes > MyWorkflow]**.

일치하는 스키마가 와 링크로 연결되므로 작업 및 워크플로는 캠페인과 동일한 패키지로 내보내집니다. `own` 유형 무결성.

패키지 콘텐츠는 다음과 같습니다.

```xml
<?xml version='1.0'?>
<package author="Administrator (admin)" buildNumber="7974" buildVersion="7.1" img=""
label="" name="" namespace="" vendor="">
 <desc></desc>
 <version buildDate="2013-01-09 10:30:18.954Z"/>
 <entities schema="nms:operation">
  <operation duration="432000" end="2013-01-14" internalName="OP1" label="MyCampaign"
  modelName="opEmpty" start="2013-01-09">
   <controlGroup>
    <where filteringSchema=""/>
   </controlGroup>
   <seedList>
    <where filteringSchema="nms:seedMember"></where>
    <seedMember internalName="SDM1"></seedMember>
   </seedList>
   <parameter useAsset="1" useBudget="1" useControlGroup="1" useDeliveryOutline="1"
   useDocument="1" useFCPValidation="0" useSeedMember="1" useTask="1"
   useValidation="1" useWorkflow="1"></parameter>
   <fcpSeed>
    <where filteringSchema="nms:seedMember"></where>
   </fcpSeed>
   <owner _operation="none" name="admin" type="0"/>
   <program _operation="none" name="nmsOperations"/>
   <task end="2013-01-17 10:07:51.000Z" label="MyTask" name="TSK2" start="2013-01-16 10:07:51.000Z"
   status="1">
    <owner _operation="none" name="admin" type="0"/>
    <operation _operation="none" internalName="OP1"/>
    <folder _operation="none" name="nmsTask"/>
   </task>
   <workflow internalName="WKF12" label="CampaignWorkflow" modelName="newOpEmpty"
   order="8982" scenario-cs="Notification of the workflow supervisor (notifySupervisor)"
   schema="nms:recipient">
    <scenario internalName="notifySupervisor"/>
    <desc></desc>
    <folder _operation="none" name="Folder4"/>
    <operation _operation="none" internalName="OP1"/>
   </workflow>
  </operation>
 </entities>
</package>   
```

패키지 유형에 대한 제휴는 를 사용하는 스키마에서 정의됩니다. `@pkgAdmin and @pkgPlatform` 특성. 이러한 속성은 모두 패키지 제휴 조건을 정의하는 XTK 식을 받습니다.

```xml
<element name="offerEnv" img="nms:offerEnv.png" 
template="xtk:folder" pkgAdmin="@id != 0">
```

마지막으로 `@pkgStatus` 속성을 사용하면 이러한 요소 또는 속성에 대한 내보내기 규칙을 정의할 수 있습니다. 속성 값에 따라 요소 또는 속성은 내보낸 패키지에서 찾을 수 있습니다. 이 속성에 대해 가능한 세 가지 값은 다음과 같습니다.

* `never`: 필드/링크를 내보내지 않습니다.
* `always`: 이 필드에 대해 강제 내보내기
* `preCreate`: 연결된 엔티티 만들기 승인

>[!NOTE]
>
>다음 `preCreate` 값은 링크 유형 이벤트에 대해서만 허용됩니다. 내보낸 패키지에 아직 로드되지 않은 엔티티를 생성하거나 가리킬 수 있습니다.

## 패키지 정의 관리 {#manage-package-definitions}

패키지 정의를 사용하면 나중에 단일 패키지로 내보낼 엔티티를 추가하는 패키지 구조를 만들 수 있습니다. 그러면 이 패키지와 추가된 모든 엔티티를 다른 Campaign 인스턴스로 가져올 수 있습니다.

### 패키지 정의 만들기 {#create-a-package-definition}

패키지 정의는 다음에서 액세스할 수 있습니다. **[!UICONTROL Administration > Configuration > Package management > Package definitions]** 메뉴 아래의 제품에서 사용할 수 있습니다.

패키지 정의를 만들려면 **[!UICONTROL New]** 단추를 누른 다음 패키지 정의 일반 정보를 입력합니다.

![](assets/packagedefinition_create.png)

그런 다음 패키지 정의에 엔티티를 추가하고 XML 파일 패키지로 내보낼 수 있습니다.

**관련 항목:**

* [패키지 정의에 엔티티 추가](#add-entities-to-a-package-definition)
* [패키지 정의 생성 구성](#configure-package-definitions-generation)
* [패키지 정의에서 패키지 내보내기](#export-packages-from-a-package-definition)

### 패키지 정의에 엔티티 추가 {#add-entities-to-a-package-definition}

다음에서 **[!UICONTROL Content]** 탭을 클릭하고 **[!UICONTROL Add]** 단추를 클릭하여 패키지로 내보낼 엔티티를 선택합니다. 엔티티 선택 모범 사례는에 나와 있습니다. [이 섹션](#export-a-set-of-objects-in-a-package).

![](assets/packagedefinition_addentities.png)

엔티티는 인스턴스의 해당 위치에서 패키지 정의에 직접 추가할 수 있습니다. 이렇게 하려면 아래 단계를 수행합니다.

1. 원하는 엔티티를 마우스 오른쪽 버튼으로 클릭한 다음 를 선택합니다 **[!UICONTROL Actions > Export in a package]**.

1. 선택 **[!UICONTROL Add to a package definition]**&#x200B;를 클릭한 후 엔티티를 추가할 패키지 정의를 선택합니다.

1. 엔티티가 패키지 정의에 추가되면 패키지와 함께 내보내집니다( 참조) [이 섹션](#export-packages-from-a-package-definition)).

### 패키지 정의 생성 구성 {#configure-package-definitions-generation}

패키지 정의에서 패키지 생성을 구성할 수 있습니다. **[!UICONTROL Content]** 탭. 이렇게 하려면 **[!UICONTROL Generation parameters]** 링크를 클릭합니다.

![](assets/packagedefinition_generationparameters.png)

* 사용 **[!UICONTROL Include the definition]** 현재 패키지 정의에 사용되는 정의를 포함하는 옵션입니다.
* 사용 **[!UICONTROL Include an installation script]** 패키지 가져오기 시 실행할 javascript 스크립트를 추가하는 옵션. 선택한 경우 **[!UICONTROL Script]** 패키지 정의 화면에 탭이 추가됩니다.
* 사용 **[!UICONTROL Include default values]** 모든 엔티티 속성의 값을 패키지에 추가하는 옵션.

  긴 내보내기를 방지하기 위해 이 옵션은 기본적으로 선택되어 있지 않습니다. 즉, 기본적으로 기본값이 있는 엔티티 속성(&#39;empty string&#39;, &#39;0&#39; 및 &#39;false&#39;(스키마에 달리 정의되지 않은 경우)은 패키지에 추가되지 않으므로 내보내지지 않습니다.

  >[!CAUTION]
  >
  >패키지를 가져오는 인스턴스에 패키지의 엔티티와 동일한 엔티티(예: 동일한 외부 ID를 가진 엔티티)가 포함된 경우 해당 속성이 업데이트되지 않습니다. 이 문제는 이전 인스턴스의 속성이 패키지에 포함되지 않았으므로 기본값이 있는 경우에 발생할 수 있습니다. 이 경우 **[!UICONTROL Include default values]** 이전 인스턴스의 모든 속성을 패키지와 함께 내보내면 옵션이 버전 병합을 방지합니다.

### 패키지 정의에서 패키지 내보내기 {#export-packages-from-a-package-definition}

패키지 정의에서 패키지를 내보내려면 아래 단계를 수행합니다.

1. 내보낼 패키지 정의를 선택하고 **[!UICONTROL Actions]** 단추 및 선택 **[!UICONTROL Export the package]**.
1. 내보낸 파일의 이름과 위치를 확인합니다.
1. 다음을 클릭합니다. **[!UICONTROL Start]** 단추를 클릭하여 내보내기를 시작합니다.

## 패키지 가져오기 {#import-packages}

패키지 가져오기 도우미는 메인 메뉴를 통해 액세스할 수 있습니다 **[!UICONTROL Tools > Advanced > Import package]** 클라이언트 콘솔의

### 파일에서 패키지 설치 {#install-a-package-from-a-file}

기존 데이터 패키지를 가져오려면 다음 단계를 수행합니다.

1. 메인 메뉴를 통해 가져오기 도우미에 액세스 **[!UICONTROL Tools > Advanced > Import package]** 클라이언트 콘솔의
1. XML 파일을 선택하고 **[!UICONTROL Open]**.

가져올 패키지의 콘텐츠가 편집기의 중간 섹션에 표시됩니다.

클릭 **[!UICONTROL Next]** 및 **[!UICONTROL Start]** 가져오기를 시작합니다.

### 기본 제공 패키지 설치 {#install-a-standard-package}

기본 제공 패키지(예: 표준 패키지)는 Adobe Campaign이 구성될 때 설치됩니다. 사용 권한, 배포 모델 및 제공 제품에 따라 새로운 표준 패키지를 가져올 수 있습니다.

설치할 수 있는 패키지를 확인하려면 사용권 계약을 참조하십시오.

## 데이터 패키지 모범 사례 {#data-package-best-practices}

이 섹션에서는 프로젝트 기간 동안 일관된 방식으로 데이터 패키지를 구성하는 방법에 대해 설명합니다.


### 버전

항상 플랫폼의 동일한 버전 내에서 가져와야 합니다. 빌드가 동일한 두 인스턴스 간에 패키지를 배포하는지 확인해야 합니다. 가져오기를 강제로 수행하지 않고 항상 먼저 플랫폼을 업데이트합니다(빌드가 다른 경우).

>[!IMPORTANT]
>
>Adobe은 다른 버전 간 가져오기를 지원하지 않습니다.

스키마와 데이터베이스 구조에 주의하십시오. 스키마를 사용하여 패키지를 가져온 다음에는 스키마가 생성되어야 합니다.

### 패키지 유형 {#package-types}

먼저 다양한 유형의 패키지를 정의합니다. 다음 네 가지 유형만 사용됩니다.

**엔티티**

* 스키마, 양식, 폴더, 게재 템플릿 등과 같은 Adobe Campaign의 모든 &quot;xtk&quot; 및 &quot;nms&quot; 특정 요소
* 엔티티를 &quot;admin&quot; 및 &quot;platform&quot; 요소로 고려할 수 있습니다.
* Campaign 인스턴스에 업로드할 때 패키지에 둘 이상의 엔티티를 포함해서는 안 됩니다.

새 인스턴스에 구성을 배포해야 하는 경우 모든 엔티티 패키지를 가져올 수 있습니다.

**기능**

이 유형의 패키지:
* 클라이언트 요구 사항/사양에 대한 답변입니다.
* 하나 이상의 기능을 포함합니다.
* 다른 패키지 없이 기능을 실행할 수 있도록 모든 종속성을 포함해야 합니다.

**캠페인**

이 패키지는 필수가 아닙니다. 캠페인이 기능으로 보여질 수 있더라도 모든 캠페인에 대한 특정 유형을 만드는 것이 유용한 경우가 있습니다.

**업데이트**

구성하고 나면 기능을 다른 환경으로 내보낼 수 있습니다. 예를 들어 패키지를 개발 환경에서 테스트 환경으로 내보낼 수 있습니다. 이 검사에서는 결함이 드러납니다. 먼저 개발 환경에서 수정해야 합니다. 그런 다음 패치를 테스트 플랫폼에 적용해야 합니다.

첫 번째 해결 방법은 전체 기능을 다시 내보내는 것입니다. 그러나 위험(원치 않는 요소 업데이트)을 방지하려면 수정만 포함된 패키지를 갖는 것이 안전합니다.

따라서 기능의 엔티티 유형이 하나만 포함된 &quot;업데이트&quot; 패키지를 만드는 것이 좋습니다.

업데이트는 수정일 뿐만 아니라 엔티티/기능/캠페인 패키지의 새 요소도 될 수 있습니다. 전체 패키지를 배포하지 않도록 업데이트 패키지를 내보낼 수 있습니다.

### 이름 지정 규칙 {#data-package-naming}

이제 유형이 정의되었으므로 명명 규칙을 지정해야 합니다. Adobe Campaign에서는 패키지 사양에 대한 하위 폴더를 만들 수 없습니다. 즉, 숫자는 조직화된 상태를 유지하는 데 가장 적합한 솔루션입니다. 번호는 패키지 이름에 접두사로 사용됩니다.

예를 들어 다음 규칙을 사용할 수 있습니다.

* 엔티티: 1부터 99까지
* 기능: 부터 100 - 199
* 캠페인: 200부터 299까지
* 업데이트: 5000에서 5999로

#### 엔티티 패키지 순서 {#entity-packages-order}

가져오기를 지원하기 위해 엔티티 패키지는 가져와야 하는 대로 주문해야 합니다.

예제:

* 001 - 스키마
* 002 - 양식
* 003 - 이미지
* 등

>[!NOTE]
>
>Forms은 가져와야 합니다. **이후** 스키마 업데이트.


#### 패키지 설명서 {#package-documentation}

패키지를 업데이트할 때 항상 설명 필드에 설명을 추가하여 수정 사항 및 이유를 자세히 설명해야 합니다(예: &quot;새 스키마 추가&quot; 또는 &quot;오류 수정&quot;).

또한 업데이트 날짜를 입력하는 것이 좋습니다.

>[!IMPORTANT]
>
>설명 필드는 2.000자까지만 포함할 수 있습니다.

