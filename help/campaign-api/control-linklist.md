---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%
---
# 링크 목록

컬렉션 편집을 위한 컨트롤입니다.

![LinkList 컨트롤](assets/linklist.8b71bb0e.png)

## 속성

**addButton - 부울** 추가 단추를 표시합니다. 이 옵션은 hideEditButtons 옵션이 활성화된 경우에만 유효합니다.

**backColor - string** 배경색(btnshadow, white).

**border - string** 컨트롤 윤곽선 스타일(단색, 이중, 인세트, 시작, 없음)을 변경합니다.

**dblClickAction - string** 두 번 클릭할 폼의 이름입니다.

**delButton - 부울** 삭제 단추를 표시합니다. 이 옵션은 hideEditButtons 단추가 활성화되어 있을 경우에만 유효합니다.

**enumImage - string** 각 줄의 이미지를 표시하는 데 사용되는 시스템 열거형의 이름입니다.

**font-size - integer** 글꼴 크기를 변경합니다.

링크 편집을 위한 **양식 - 문자열** 양식입니다.

**hideEditButtons - boolean** 추가, 삭제 및 편집 단추를 숨깁니다.

**img - 문자열** 이미지.

**레이블 - 문자열** 관련 레이블입니다.

**nolabel - 부울** 컨트롤 앞에 레이블이 없습니다.

**noToolbar - 부울** 도구 모음을 숨깁니다.

**orderBy - element** 목록 일정을 예약합니다.

**읽기 전용 - 부울** 컨트롤을 읽기 전용으로 강제 실행합니다.

**sysFilter - 요소** 목록 필터링.

**toobarAlign - 문자열** 가로 \| 세로

**toobarCaption - string** 레이블이 도구 모음에 표시됩니다.

목록의 **xpath-link - string** 링크(그룹의 예제 참조).

**xpathIndex - string** 선택 인덱스는 이 경로에서 지정한 위치에 저장됩니다.

**xpathLinkEdit - string** 편집할 링크(그룹의 예제 참조).

**확대/축소 - 부울** 링크 편집을 허용합니다.

## 비고

예:

```xml
      <input type="linkList" xpath="operator" enumImage="@type" nolabel="true">
  <input xpath="@name" label="Name" colSize="30"/>
  <input xpath="@login"/>
  <sysFilter>
    <condition expr="@type=1"/>
  </sysFilter>
</input>

<input type="linkList" xpath="operator" enumImage="@type" nolabel="true">
  <input xpath="@name" label="Name" colSize="30"/>
  <input xpath="@login"/>
  <form label="Add operators">
  <input xpath="." type="linkListChoice" xpath-link="recipient" img="nms:group.bmp">
  <input xpath="@lastName"/>
  <input xpath="@firstName"/>
  </input>
  </form>
</input>

<input type="linklist" xpath="rcpGrpRel" zoom="true" label="Recipients" form="nms:recipient"
       xpath-link="rcpGroup"
       xpathLinkEdit="recipient">
  <input xpath="recipient/@lastName"/>
  <input xpath="recipient/@firstName"/>
  <input xpath="recipient/@email"/>
  <input xpath="recipient/@phone"/>
</input>
```
