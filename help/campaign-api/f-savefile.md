---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 11%
---
# saveFile

> 경고:
>
> 파일 API를 통한 액세스는 Adobe Campaign의 **var**, **sftp** 및 임시 폴더로 제한됩니다.

문자열을 파일에 저장합니다.

```text
saveFile (text, filename [, codePage ])
```

## 매개변수

**text** 저장할 텍스트 문자열입니다.

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

문자 인코딩을 지정하지 않으면 서버 기본값이 사용됩니다.

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
