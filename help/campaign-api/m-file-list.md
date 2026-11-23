---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 11%
---
# 목록

디렉토리의 컨텐트를 나열합니다.

```text
list ( [mask ] [, sort ] [, noCase ])
```

## 매개변수

**마스크** 검색 마스크(기본적으로\*)입니다.

결과를 정렬하려면 **sort** true를 사용합니다(기본적으로 false).

정렬 시 클래스를 무시하려면 **noCase** true입니다(기본적으로 false).

## 반환 값

지정한 경로 및 마스크와 일치하는 파일 목록( [파일](c-file.md))을 포함하는 테이블입니다.

## 비고

디렉터리 이름은 Linux에서는 /, Windows에서는 \\로 끝나야 합니다. 예:

```javascript
var dir = new File("c:\\temp\\")
var files = dir.list("*.*")
for each (var file in files)
  logInfo(file.name)
```

## 기능

**클래스의 메서드:** [파일](c-file.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
