---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 21%
---
# getCurrentDate

데이터베이스 서버의 현재 날짜를 반환합니다.

```text
getCurrentDate ()
```

## 매개변수

없음.

## 반환 값

데이터베이스 서버의 현재 날짜입니다.

## 비고

예:

```javascript
      date = formatDate(getCurrentDate(),"%4Y/%2M/%2D %02H:%02N:%02S")
```

formatDate() 함수에 대한 자세한 내용은 [formatDate(date, format)](f-formatdate.md)을(를) 참조하십시오.

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
