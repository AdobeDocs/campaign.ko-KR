---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 13%
---
# 로드

> 경고:
>
> 파일 API를 통한 액세스는 Adobe Campaign의 **var**, **sftp** 및 임시 폴더로 제한됩니다.

XML 파일에서 새 문서를 만듭니다.

```text
load (filename [, allowEmpty ])
```

## 매개변수

**파일 이름** 로드할 파일의 이름입니다.

**allowEmpty** true인 경우 파일이 비어 있으면 예외가 발생하지 않습니다(기본값=false).

## 반환 값

없음.

## 비고

파일을 로드할 수 없거나 파일 내용이 올바른 XML 문서가 아닌 경우 예외가 발생합니다. 이 함수는 DOMDocument 클래스에 적용됩니다. 예:

```javascript
var doc = DOMDocument.load("data/test.xml")
```

## 기능

**클래스의 메서드:** [DOMDocument](c-domdocument.md)

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
