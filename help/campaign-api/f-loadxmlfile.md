---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 13%
---
# loadXmlFile

> 경고:
>
> 파일 API를 통한 액세스는 Adobe Campaign의 **var**, **sftp** 및 임시 폴더로 제한됩니다.

이 함수는 더 이상 사용되지 않습니다. [DOMDocument.load()](m-domdocument-load.md)을(를) 사용하십시오. 파일을 XML 문서 객체 형태로 로드합니다.

```text
loadXmlFile (filename [, noErr ])
```

## 매개변수

**파일 이름** 로드할 파일의 전체 이름입니다.

**noErr** true인 경우 파일이 비어 있으면 오류가 발생하지 않습니다(기본값=false).

## 반환 값

XML 문서.

## 비고

이 함수는 BOM 및 XML 프롤로그 감지를 통해 파일의 코드 페이지 감지를 지원합니다.

## 기능

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
