---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 25%
---
# sha1

MemoryBuffer 콘텐츠의 SHA-1 서명을 계산합니다.

```text
sha1 ()
```

## 매개변수

없음.

## 반환 값

SHA-1 서명의 16진수 표현인 문자 문자열입니다.

## 비고

예:

```javascript
var memBuf = new MemoryBuffer();
memBuf.fromString("Hello world", "utf-8");
logInfo(memBuf.sha1()); // Writes down  => 7b502c3a1f48c8609ae212cdfb639dee39673f5e
```

## 기능

**클래스의 메서드:** [MemoryBuffer](c-memorybuffer.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 게재 메시지
* 유형화 규칙
* 가져오기
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
