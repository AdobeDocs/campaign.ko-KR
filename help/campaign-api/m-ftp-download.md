---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 9%
---
# 다운로드

서버에서 로컬 파일 또는 메모리로 파일을 다운로드합니다.

```text
download (URL [, append ])
```

## 매개변수

다운로드할 파일의 **URL** URL.

**추가** 기본적으로 다운로드한 파일이 로컬 디스크에 이미 있으면 받은 새 파일로 덮어씁니다. 부울이 활성화되면 Adobe Campaign은 다운로드한 콘텐츠를 기존 콘텐츠와 함께 동일한 이름으로 파일에 기록합니다.

## 반환 값

없음.

## 비고

로컬 파일에서 파일을 복구하려면 setFile 메서드를 사용하여 시작하십시오. 예:

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.download("ftp://ftp.funet.fi/pub/standards/RFC/rfc2068.txt")
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
