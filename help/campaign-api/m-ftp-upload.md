---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%
---
# 업로드

로컬 파일에서 FTP 서버로 파일을 다운로드합니다.

```text
upload (URL)
```

## 매개변수

**URL** 서버 URL.

## 반환 값

없음.

## 비고

URL은 &#39;ftp:&#39;으로 시작해야 합니다. 예:

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.upload("ftp://ftp.funet.fi/pub/standards/RFC")
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
