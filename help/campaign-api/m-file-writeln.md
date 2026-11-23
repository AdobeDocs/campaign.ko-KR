---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 25%
---
# writeln

파일에 텍스트 줄을 씁니다.

```text
writeln (line)
```

## 매개변수

**줄** 쓸 텍스트 줄입니다.

## 반환 값

없음.

## 비고

예:

```javascript
var f = new File("c:/file.txt")
f.open("a")
f.writeln("line 1")
f.writeln("line 2")
f.close()
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
