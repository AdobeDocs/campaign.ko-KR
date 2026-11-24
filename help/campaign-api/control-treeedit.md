---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 1%
---
# 트리 편집

다양한 카테고리로 그룹화된 다양한 값을 보고 편집하도록 제어합니다.

![TreeEdit 컨트롤](assets/treeedit.253f1374.png)

## 속성

**backColor - string** 배경색(btnshadow, white).

**border - string** 컨트롤 윤곽선 스타일(단색, 이중, 인세트, 시작, 없음)을 변경합니다.

**편집 가능 - 문자열**&#x200B;은(는) 수정 내용을 자동으로 적용합니다(기본적으로 true).

**font-size - integer** 글꼴 크기를 변경합니다.

**레이블 - 문자열** 관련 레이블입니다.

**noImage - string** 목록에 있는 요소의 이미지를 숨깁니다.

**nolabel - 부울** 연결된 레이블을 숨깁니다.

**읽기 전용 - 부울** 컨트롤을 읽기 전용으로 강제 실행합니다.

## 비고

하위 요소 속성

* visibleIf: 요소를 표시하거나 숨기는 XTK 조건입니다.
* label: 요소의 레이블입니다.
* exprLabel: 표현식 형식으로 요소의 레이블입니다.
* xpath: 요소의 XPath.
* img: 요소의 이미지입니다.

입력 하위 요소의 속성

* editable: 편집 가능한 값. 기본값은 루트 요소에서 상속됩니다.

컨테이너 하위 요소 속성

* 축소됨: true\|false 하위 요소를 표시하거나 숨깁니다.

예:

```xml
<input nolabel="true" type="treeEdit">
  <container label="Text fields">
    <input xpath="@text1"/>
    <input xpath="@text2"/>
    <input xpath="@text3"/>
    <input xpath="@text4"/>
    <input xpath="@text5"/>
  </container>
  <container label="Boolean fields">
    <input xpath="@boolean1"/>
    <input xpath="@boolean2"/>
    <input xpath="@boolean3"/>
  </container>
</input>
    
```
