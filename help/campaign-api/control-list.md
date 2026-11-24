---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 1%
---
# 목록

메모리 목록입니다.

## 속성

**backColor - string** 배경색(btnshadow, white).

**border - string** 컨트롤 윤곽선 스타일(단색, 이중, 인세트, 시작, 없음)을 변경합니다.

**편집 가능 - 부울** 목록 편집 권한을 부여합니다.

**font-size - integer** 글꼴 크기를 변경합니다.

**양식 - 문자열** 편집 양식입니다.

각 줄의 **img - 문자열** 이미지.

**레이블 - 문자열** 관련 레이블입니다.

**nolabel - 부울** 레이블이 없습니다.

**알림 - 부울** 열 제목을 표시하지 않습니다.

**noToolbar - 부울** 도구 모음을 숨깁니다.

**정렬됨 - 부울** 목록 일정을 허용합니다.

**읽기 전용 - 부울** 컨트롤을 읽기 전용으로 강제 실행합니다.

**toobarAlign - 문자열** 가로 \| 세로

**toobarCaption - string** 레이블이 도구 모음에 표시됩니다.

**확대/축소 - 부울** 편집 양식을 표시합니다.

**zoomOnAdd - boolean** 줄을 추가하면 양식을 엽니다.

**xpathIndex - xpath** 선택 항목의 인덱스는 이 경로에서 지정한 위치에 저장됩니다.

**xpathSelection - xpath** XPATH 경로가 저장되어 선택한 요소에 도달할 노드입니다.

## 비고

예제 1:

```xml
      <input type="list" xpath="dataTransferStep" nolabel="true" editable="false"
       zoom="true" form="xtk:exportSource" zoomOnAdd="true" img="xtk:script.bmp">
  <input xpath="@name" colSize="15"/>
  <input xpath="@active" editable="true" colSize="15"/>
</input>
```

예제 2:

```xml
<input type="list" xpath="operator" zoom="true">
  <input xpath="@name" colSize="15"/>
  <form>
    <input xpath="@name"/>
  </form>
</input>
```
