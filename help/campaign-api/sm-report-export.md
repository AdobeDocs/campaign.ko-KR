---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 13%
---
# 내보내기

보고서 생성 및 내보내기

```text
Export ( String reportName, XML context, String exportFormat, String fileName, Boolean isAdHoc )
```

## 매개변수

보고서의 **reportName** 내부 이름

**컨텍스트** 실행 컨텍스트입니다.

**exportFormat** 가능한 값: XLS, OOXML\_SS, ODF\_SS, PDF

XLS는 Excel 94-2003 문서를 생성합니다.\
 OOXML\_SS는 Excel 2007 문서를 생성합니다.\
 ODF\_SS가 열린 문서를 생성합니다.

**fileName** 출력 파일 이름

**isAdHoc** 내보내기가 임시 보고서와 관련되는지 여부를 지정합니다.

## 반환 값

없음.

## 기능

**스키마:** [xtk:report](s-xtk-report.md)

**정적:**

예
