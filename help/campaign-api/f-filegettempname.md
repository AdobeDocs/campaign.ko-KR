---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 15%
---
# fileGetTempName

임시 파일 이름을 생성합니다.

```text
fileGetTempName ( [directory ] [, prefix ] [, extension ])
```

## 매개변수

임시 파일의 **디렉터리** 디렉터리. 비어 있는 경우 시스템에서 정의한 임시 디렉토리를 사용합니다.

**접두사** 접두사(최대 4자). 비어 있는 경우 tmp 접두사가 사용됩니다.

**확장명** 파일 확장명.

## 반환 값

파일의 전체 이름.

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
