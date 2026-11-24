---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 3%
---
# 아이콘 상자

여러 페이지를 선택할 수 있는 아이콘 목록입니다.

![Iconbox 컨트롤](assets/iconbox.05daa4bf.png)

## 속성

**backColor - string** 배경색(btnshadow, white).

**이름 - 문자열** 컨테이너 ID.

**padding-left - integer** 컨테이너의 왼쪽에 있는 픽셀 단위 공간입니다.

**패딩 오른쪽 - 정수** 컨테이너의 오른쪽에 있는 픽셀 단위 공간입니다.

**위쪽 패딩 - 정수** 컨테이너 위의 픽셀 단위 공간입니다.

**padding-bottom - integer** 컨테이너 아래 픽셀 단위 공간입니다.

**패딩 - 정수** 컨테이너 주위의 픽셀 단위 공간입니다.

**읽기 전용 - 부울** 제어와 모든 하위 항목을 읽기 전용으로 강제 적용합니다.

## 비고

각 컨테이너 하위 요소는 페이지를 나타냅니다. 예:

```xml
<container name="iconbox" type="iconbox">
   <container colcount="3" label="Header">
     ...
   </container>
   <container img="ncm:ctprop.bmp" label="Intro">
     ...
   </container>
   <container img="ncm:subsection.bmp" label="Event">
     ...
   </container>
   <container img="ncm:book.bmp" label="Selection">
     ...
   </container>
   <container img="nms:contacts.bmp" label="Services">
     ...
   </container>
   <container img="nms:contacts.bmp" label="Mail footer ">
     ...
   </container>
 </container>
```
