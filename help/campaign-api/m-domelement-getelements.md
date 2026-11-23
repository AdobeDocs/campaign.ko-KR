---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 13%
---
# getElements

이 요소에 속한 지정된 이름의 자식 요소 목록을 반환합니다.

```text
getElements ( [tagName ])
```

## 매개변수

**tagName** 검색된 요소 이름입니다. 이 매개 변수가 생략되면 함수는 모든 하위 요소를 반환합니다.

## 반환 값

요소 목록이 포함된 표.

## 비고

이 메서드는 각 호출에 대해 새 테이블을 만듭니다. 따라서 여러 번 호출하기 보다는 테이블을 로컬 변수에 유지하는 것이 좋습니다.

## 기능

**클래스의 메서드:** [DOMElement](c-domelement.md)

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
