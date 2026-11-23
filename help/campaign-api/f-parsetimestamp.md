---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 9%
---
# parseTimestamp

ISO 8601 표준의 간소화된 버전을 기반으로 공식화된 날짜가 포함된 문자열을 날짜 유형 개체로 변환합니다.

```text
parseTimeStamp (aString)
```

## 매개변수

**aString** ISO 8601 형식의 문자열 날짜입니다.

## 반환 값

매개 변수로 설정된 날짜와 일치하는 Date 유형 개체입니다.

## 비고

구문은 다음과 같습니다.

```javascript
              date
              time[time-zone]
            
```

또는

```javascript
              dateTtime[time-zone]
            
```

날짜는 다음 형식이어야 합니다.

```javascript
YYYY-MM-DD
```

호환성을 위해 다음 형식도 허용됩니다.

```javascript
YYYY/MM/DD
```

시간은 다음 형식을 가져야 합니다.

```javascript
hh:mm:ss
hh:mm:ss.nnn
```

시간대를 지정할 경우 형식은 다음과 같아야 합니다.

```javascript
Z
+hh:mm
-hh:mm
+hh
-hh
```

시간대가 지정되지 않은 경우 날짜는 상황에 따라 현재 시간대로 변환됩니다. 예:

```javascript
2005-03-02 00:00:00
2005-03-02
2005-03-02T14:32:26
2005-03-02T14:32:26.0000
2005-03-02T14:32:26.0000000+01:00
2005-03-02T14:32:26+01:00
2005-03-02T14:32:26Z
2005-03-02T14:32:26.0005Z
2005/03/02 14:32:25
```

날짜 형식이 올바르지 않으면 예외가 발생합니다.

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
