---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 8%
---
# saveXmlString

이 명령은 더 이상 사용되지 않습니다. [saveXmlFile()](f-savexmlfile.md)을(를) 사용하십시오. XML 문서에 해당하는 문자열을 파일에 저장합니다.

```text
saveXmlString (text, filename [, codePage ])
```

## 매개변수

**text** 저장할 문자열 형식의 XML 문서입니다.

**파일 이름** 저장할 파일의 전체 이름입니다.

**codePage** 이 선택적 매개 변수를 사용하면 문자 인코딩을 지정할 수 있습니다. 예:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## 반환 값

없음.

## 비고

이 함수는 필요한 경우 파일에 XML 프롤로그를 삽입하고 문서 코딩을 지정합니다. 문자 인코딩을 지정하지 않으면 서버 기본값이 사용됩니다.

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
