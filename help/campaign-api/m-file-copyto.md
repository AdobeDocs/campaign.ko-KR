---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 22%
---
# 복사 위치

파일을 복사합니다.

```text
copyTo (fileName)
```

## 매개변수

**fileName** 대상 파일 또는 폴더의 이름입니다(전체 경로여야 함).

## 반환 값

없음.

## 비고

예:

```javascript
var f = new File("c:/file.txt")
f.copyTo("c:/file2.txt")

var f2 = new File("c:/file.txt")
f2.copyTo("c:/dir/")
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
