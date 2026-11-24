---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 1%
---
# 다이어그램 편집

이 컨트롤은 워크플로우나 설문 조사 같은 다이어그램을 편집하는 데 사용됩니다.

![DiagramEdit 컨트롤](assets/diagramedit.d750db7e.png)

## 속성

**backColor - string** 배경색(btnshadow, white).

**border - string** 컨트롤 윤곽선 스타일(단색, 이중, 인세트, 시작, 없음)을 변경합니다.

**레이블 - 문자열** 관련 레이블입니다.

**nolabel - 부울** 레이블을 도움말 버블로 표시합니다.

**읽기 전용 - 부울** 컨트롤을 읽기 전용으로 강제 실행합니다.

## 비고

도구 모음을 개인화할 수 있습니다. 이 컨트롤의 각 하위 요소는 도구 모음의 추가 단추와 일치합니다.

```xml
<input type="diagramEdit" xpath=".">
  <input type="separator"/>
  <input img="xtk:properties.png" label="Properties" resetForm="true" prebuildSubForm="true">
    <form name="properties" label="Properties">
      <input xpath="/tmp/@test"/>
    </form>
  </input>
  <input type="separator"/>
  <input img="nms:prepare.png" label="Publish" checkModify="true">
    <form name="properties" label="Properties">
      <input xpath="/tmp/@test"/>
    </form>
  </input>
</input>
```

도구 모음의 단추에 대한 자세한 내용은 SubFormButton 컨트롤 설명서를 참조하십시오.
