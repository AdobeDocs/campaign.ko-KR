---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 16%
---
# ExportPreview

쿼리의 첫 번째 라인에 대한 출력 파일 열 미리보기 계산

```text
[ XML resultColumns, XML resultXML, String resultSQLRequest ] = ExportPreview ( XML dataTransferStep, Number lineCount, Boolean countMode, String calcFieldName )
```

## 매개변수

계산된 필드가 정의된 **dataTransferStep** 전송 단계입니다.

**lineCount** 반환할 줄 수

**countMode** 줄 계산 모드

**calcFieldName** 관찰된 계산된 필드의 이름입니다. 비어 있는 경우 출력 파일의 전역 미리 보기입니다.

## 반환 값

**resultColumns** 내보내기 파일 열 값(line/col/val, line/col/errors)을 반환합니다.

**resultXML** 쿼리의 출력 XML 문서를 반환합니다.

**resultSQLRequest** 실행된 SQL 쿼리를 반환합니다.

## 기능

**스키마:** [xtk:dataTransfer](s-xtk-datatransfer.md)

**정적:**

예
