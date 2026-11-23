---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 10%
---
# 목록

지정한 디렉터리에 있는 서버의 파일 목록을 반환합니다.

```text
list (URL, pattern [, max ])
```

## 매개변수

URL로서 FTP 서버의 **URL** 주소입니다.

**pattern** 검색할 파일 목록의 파일 및 마스크입니다.

**max** 반환할 최대 파일 수입니다. 이 매개 변수가 없으면 메서드는 파일의 전체 목록을 반환합니다.

## 반환 값

지정된 경로 및 마스크에 해당하는 파일 이름이 포함된 표입니다.

## 비고

FTP 명령이 실패하고 예외가 발생하는 경우 예:

```javascript
var ftp = new FTP
var files = ftp.list("ftp://ftp.funet.fi/", "pub/standards/RFC/rfc*.txt", 10)
for(var i in files)
  logInfo(files[i])
ftp.dispose()
```

## 기능

**클래스의 메서드:** [FTP](c-ftp.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
