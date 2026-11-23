---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 5%
---
# 열기

파일을 읽기 또는 쓰기 모드로 엽니다.

```text
open ( [mode ] [, codepage ])
```

## 매개변수

**모드** 파일 열기 모드. 모드는 여러 값 중 하나일 수 있습니다.

* &quot;r&quot; - 파일을 읽기 전용 모드로 엽니다. 이 모드는 기본 모드입니다.
* &quot;w&quot; - 파일을 쓰기 모드로 엽니다.
* &quot;a&quot; - 파일을 &#39;append&#39; 모드로 열고 파일에 기록된 데이터가 끝에 추가됩니다.

**codepage** 파일 인코딩입니다. 인코딩은 다음 값 중 하나일 수 있습니다.

* File.CODEPAGE\_CURRENT - 기본 코드 페이지입니다.
* File.CODEPAGE\_OEM
* File.CODEPAGE\_MAC
* File.CODEPAGE\_THREAD
* File.CODEPAGE\_LATIN1
* File.CODEPAGE\_LATIN2
* File.CODEPAGE\_ISOLATIN1
* File.CODEPAGE\_ISOLATIN2
* File.CODEPAGE\_OEMLATIN1
* File.CODEPAGE\_OEMLATIN2
* File.CODEPAGE\_UTF7
* File.CODEPAGE\_UTF8
* File.CODEPAGE\_ISOLATIN9
* File.CODEPAGE\_OEMUS
* File.CODEPAGE\_SHIFTJIS
* File.CODEPAGE\_BIG5
* File.CODEPAGE\_CHINESE
* File.CODEPAGE\_EUKOREAN
* File.CODEPAGE\_UTF16LE
* File.CODEPAGE\_UTF16BE

## 반환 값

없음.

## 비고

파일을 열 수 없으면 예외가 발생합니다.

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
