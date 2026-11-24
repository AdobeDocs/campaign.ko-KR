---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 24%
---
# 이름 바꾸기

파일 이름을 바꿉니다.

```text
renameTo (fileName)
```

## 매개변수

**fileName** 새 파일 이름(전체 경로여야 함)입니다.

## 반환 값

없음.

## 비고

예:

```javascript
var f = new File("c:/file.txt")
f.renameTo("c:/file2.txt")

var f2 = new File("c:/file.txt")
f2.renameTo("c:/dir/")
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
