---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 11%
---
# getUrl

URL에서 텍스트 콘텐츠를 복구합니다.

```text
getUrl (url [, timeout ])
```

## 매개변수

**url** 복구할 페이지의 주소입니다.

**시간 초과** 연결 시간 초과. 지정된 지연 내에 연결을 설정할 수 없으면 오류가 발생하고 스크립트가 중단됩니다.

## 반환 값

텍스트 페이지를 포함하는 문자열.

## 비고

반환된 문자열의 인코딩은 응답에 지정된 인코딩입니다(Content-Type). 다운로드 중에 오류가 발생하거나 반환 코드가 200(OK)이 아니면 오류가 발생하여 실행 중인 스크립트가 중단됩니다. 예:

```javascript
      var content = getUrl("http://www.google.com/index.html")
```

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
