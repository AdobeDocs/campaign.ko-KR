---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 17%
---
# Zip 파일

> 경고:
>
> 파일 API를 통한 액세스는 Adobe Campaign의 **var**, **sftp** 및 임시 폴더로 제한됩니다.

파일과 연결된 새 Zip 개체를 만듭니다.

```text
ZipFile (filename)
```

## 매개변수

**파일 이름** 로드하거나 만들 보관 이름입니다.

## 반환 값

없음.

## 비고

예:

```javascript
var zip = new ZipFile("/tmp/archive.zip")
```

## 기능

**클래스의 메서드:** [ZipFile](c-zipfile.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
