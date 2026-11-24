---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 11%
---
# loadLibrary

JavaScript 라이브러리를 로드합니다.

```text
loadLibrary (filename [, boolean ])
```

## 매개변수

**파일 이름** 로드할 JavaScript 라이브러리의 이름입니다.

**부울** 로드 캐시를 활성화하거나 비활성화합니다. 기본값은 true입니다.

> 참고: 매개 변수가 false로 설정되면 loadLibrary 호출 전에 logon() 함수를 사용하여 연산자로 인증해야 합니다.

## 반환 값

없음.

## 비고

캐시는 기본적으로 활성화되어 있습니다. 캐시를 사용하지 않으면 각 호출에 대해 데이터베이스가 쿼리됩니다. 이 쿼리를 사용하면 최신 버전의 라이브러리를 로드할 수 있습니다. 예: loadLibrary(&#39;xtk:shared/nl.js&#39;)

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
