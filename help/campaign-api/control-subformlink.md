---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%
---
# 하위 양식 링크

하위 양식을 여는 링크입니다.

![SubFormLink 컨트롤](assets/urlbutton.d1cf6f42.png)

## 속성

**backColor - string** 배경색(btnshadow, white).

**border - string** 컨트롤 윤곽선 스타일(단색, 이중, 인세트, 시작, 없음)을 변경합니다.

**discardReadOnly - string** &quot;읽기 전용&quot; 속성을 하위 양식으로 전파하지 않습니다.

**font-size - integer** 글꼴 크기를 변경합니다.

**img - 문자열** 연결된 이미지입니다.

**레이블 - 문자열** 단추 레이블.

**nolabel - string** 컨트롤을 레이블 열에 맞출 수 있습니다.

**prebuildSubForm - string** 컨트롤을 만들 때 하위 양식을 초기화합니다. 이 옵션은 기본적으로 활성화되어 있지만 초기 표시를 가속화하도록 비활성화할 수 있습니다.

## 비고

예:

```xml
      <input type="subformlink" label="Advanced parameters...">
  <form label=" Advanced parameters">
    <input xpath="@stopIfTooManyRejects"/>
    <input xpath="@traceMode"/>
  </form>
</input>
```
