---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 1%
---
# 하위 양식 단추

하위 양식을 여는 단추입니다.

![SubFormButton 컨트롤](assets/button.f0aea09a.png)

## 속성

**backColor - string** 배경색(btnshadow, white).

**border - string** 컨트롤 윤곽선 스타일(단색, 이중, 인세트, 시작, 없음)을 변경합니다.

**discardReadOnly - string** &quot;읽기 전용&quot; 속성을 하위 양식으로 전파하지 않습니다.

**font-size - integer** 글꼴 크기를 변경합니다.

**img - 문자열** 연결된 이미지입니다.

단추의 **레이블 - 문자열** 레이블입니다.

**nolabel - string** 레이블 열에서 컨트롤을 정렬할 수 있습니다.

**prebuildSubForm - string** 컨트롤을 만들 때 하위 양식을 초기화합니다. 이 옵션은 기본적으로 활성화되어 있지만 초기 표시를 가속화하도록 비활성화할 수 있습니다.

**필수 - 부울** 필드는 필수입니다.

## 비고

예:

```xml
      <input type="subformbutton" label="Advanced parameters...">
  <form label=" Advanced parameters">
    <input xpath="@stopIfTooManyRejects"/>
    <input xpath="@traceMode"/>
  </form>
</input>
```
