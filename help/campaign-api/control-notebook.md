---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%
---
# 노트북

여러 페이지를 표시할 탭 목록입니다.

![전자 필기장 컨트롤](assets/notebook.3b531a46.png)

## 속성

**backColor - string** 배경색(btnshadow, white).

**이름 - 문자열** 컨테이너 ID.

**padding-left - integer** 컨테이너의 왼쪽에 있는 픽셀 단위 공간입니다.

**패딩 오른쪽 - 정수** 컨테이너의 오른쪽에 있는 픽셀 단위 공간입니다.

**위쪽 패딩 - 정수** 컨테이너 위의 픽셀 단위 공간입니다.

**padding-bottom - integer** 컨테이너 아래 픽셀 단위 공간입니다.

**패딩 - 정수** 컨테이너 주위의 픽셀 단위 공간입니다.

**읽기 전용 - 부울** 제어와 모든 하위 항목을 읽기 전용으로 강제 적용합니다.

**style - string** flat \| down \| up (기본값).

## 비고

각 하위 요소는 페이지를 나타냅니다. 예:

```xml
      <container colspan="2" style="down" type="notebook">
   <container label="Products">
     ...
   </container>

   <container colcount="3" xpath="link">
     ...
   </container>

   <container xpath="linkCollection">
     ...
   </container>
 </container>
```
