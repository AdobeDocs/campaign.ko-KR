---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 1%
---
# LinkListChoice

하나 이상의 엔티티 선택.

## 속성

**backColor - string** 배경색(btnshadow, white).

**border - string** 컨트롤 윤곽선 스타일(단색, 이중, 인세트, 시작, 없음)을 변경합니다.

**dblClickAction - string** 두 번 클릭할 폼의 이름입니다.

**font-size - integer** 글꼴 크기를 변경합니다.

**레이블 - 문자열** 관련 레이블입니다.

**multiSelection - 부울** 여러 선택을 허용합니다.

**nolabel - 부울** 연결된 레이블을 숨깁니다.

**읽기 전용 - 부울** 컨트롤을 읽기 전용으로 강제 실행합니다.

**serialize - boolean** 사용자 구성에서 마지막 선택을 저장합니다.wu

목록의 **xpath-link - string** 링크입니다.

## 비고

예:

```xml
      <input xpath="." type="linkListChoice" xpath-link="operator">
  <input xpath="[/]"  label="Operator or named right "/>
  <input xpath="@type"/>
  <input xpath="comment"/>
  <sysFilter>
    <condition expr="@type <> 1"/>
  </sysFilter>
  <orderBy>
    <node expr="@type"/>
  </orderBy>
</input>
```
