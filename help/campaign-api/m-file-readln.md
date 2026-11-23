---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 20%
---
# 읽기

텍스트 파일의 한 줄을 읽습니다.

```text
readln ()
```

## 매개변수

없음.

## 반환 값

파일의 다음 줄이 포함된 문자열이거나, 파일의 끝에 도달하면 ⌐null입니다.

## 비고

예:

```javascript
var f = new File("c:/dummy.xml")
f.open("r", File.CODEPAGE_UTF8)
var line
while( line = f.readln() )
  logInfo(line)
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
