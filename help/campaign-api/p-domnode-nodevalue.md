---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 15%
---
# nodeValue

노드 값. 값은 노드 유형에 따라 다릅니다.

```text
nodeValue
```

## 비고

이 속성은 읽기 및 쓰기 권한으로 액세스할 수 있습니다. 제목 줄을 검색하고 워크플로우의 쿼리 활동에서 추가 데이터에 추가하는 예:

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',data), 1, 255)
```

워크플로우의 데이터 보강 활동에서 제목 줄을 검색하는 예:

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',[target/data]), 1, 255)
```

## 기능

**클래스의 속성:** [DOMNode](c-domnode.md)

**읽기 전용:**

예

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
