---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 13%
---
# getOption

options 테이블에서 옵션 값을 반환합니다.

```text
getOption (name [, useCache ])
```

## 매개변수

**이름** 옵션 이름입니다.

**useCache** 옵션 값 캐시를 사용합니다(기본적으로 사용되지 않음).

## 반환 값

옵션이 있는 경우 옵션의 값. 그렇지 않으면 정의되지 않습니다. 값의 유형은 옵션 유형에 따라 다릅니다.

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
