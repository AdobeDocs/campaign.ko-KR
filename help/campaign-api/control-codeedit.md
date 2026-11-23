---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 3%
---
# 코드 편집

소스 코드 편집을 위한 컨트롤입니다.

![CodeEdit 컨트롤](assets/codeedit.8a744c8b.png)

## 속성

**backColor - string** 배경색(btnshadow, white).

**border - string** 컨트롤 윤곽선 스타일(단색, 이중, 인세트, 시작, 없음)을 변경합니다.

**contentType - string** 원본 코드의 언어로, 구문 색칠 및 언어에 연결된 기타 옵션에 사용됩니다. 지원되는 언어:

* 기본
* xml
* dtd
* xsl
* html
* txt
* JavaScript
* sql

nlclient.exe와 동일한 디렉토리에 있는 editor.cfg 파일을 편집하여 다른 언어를 추가할 수도 있습니다.

**font-size - integer** 글꼴 크기를 변경합니다.

**레이블 - 문자열** 관련 레이블입니다.

**nolabel - 부울** 연결된 레이블을 숨깁니다.

**읽기 전용 - 부울** 컨트롤을 읽기 전용으로 강제 실행합니다.

**도구 모음 - 부울** 도구 모음을 표시하거나 숨깁니다.

**toolbarAlign - string** 도구 모음의 위치: 가로 또는 세로

## 비고

예:

```xml
<input xpath="code" nolabel="true" type="CodeEdit"
       contentType="JavaScript" toolbar="true" toolbarAlign="horizontal"/>
```
