---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 12%
---
# 열기

기존 아카이브를 로드합니다.

```text
open ()
```

## 매개변수

없음.

## 반환 값

없음.

## 비고

기존 아카이브의 경우 먼저 ⌐[fileCount](p-zipfile-filecount.md) 메서드를 호출하여 파일 수를 복구하거나 [getEntry()](m-zipfile-getentry.md)을(를) 호출하여 파일을 추출해야 합니다. 파일이 없거나 파일이 올바른 보관 파일이 아닌 경우 메서드가 예외를 발생시킵니다.

## 기능

**클래스의 메서드:** [ZipFile](c-zipfile.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
