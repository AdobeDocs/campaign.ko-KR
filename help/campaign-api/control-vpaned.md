---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 1%
---
# VPned

여러 컨테이너를 가로로 정렬합니다.

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

각 하위 요소는 컨테이너여야 합니다. 각 하위 컨테이너는 width-percent 속성 덕분에 사용하려는 총 너비의 백분율을 지정할 수 있습니다. 예:

```xml
<container type="vpaned">
  <container label="Group 1" width-percent="25"/>
    <input .../>
  </container>
  <container label="Group 2" width-percent="75"/>
    <input .../>
  </container>
</container>
```
