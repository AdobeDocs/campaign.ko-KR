---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 14%
---
# loadString

이 명령은 더 이상 사용되지 않습니다. ⌐[loadFile()](f-loadfile.md)을(를) 사용하십시오. 텍스트 파일의 내용을 반환합니다.

```text
loadString (filename [, codePage ])
```

## 매개변수

**파일 이름** 로드할 파일의 전체 이름입니다.

**codePage** 이 선택적 매개 변수를 사용하면 문자 인코딩을 지정할 수 있습니다. 예:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## 반환 값

텍스트 파일의 내용에 해당하는 문자열입니다.

## 비고

문자 인코딩을 지정하지 않으면 서버 기본값이 사용됩니다.

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
