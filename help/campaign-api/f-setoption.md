---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 7%
---
# setOption

옵션 테이블에서 옵션 값을 변경합니다.

```text
setOption (name, value, description )
```

## 매개변수

**이름** 옵션 이름입니다.

옵션의 **값** 값입니다.

**설명** 설명의 값입니다(선택 사항).

## 반환 값

없음.

## 비고

다른 데이터 유형은 다음과 같습니다.

* 텍스트,
* 정수,
* 부동 소수점,
* 날짜 + 시간,
* longtext

API에서 longText 및 integer 유형을 만들 수 없습니다.

이러한 두 가지 유형의 경우 먼저 콘솔에서 옵션을 만들어야 setOption API를 통해 값을 관리할 수 있습니다.

**예:**

```javascript
               //create option of type Date+Time'
               var ourDate = getCurrentDate();
               setOption("testOptionDateTime",ourDate,"option of type Date+Time");
                              
               //create option of type Floating point'
               setOption("testOptionFloat",1,"option of type Floating point");
               
               //create option of type Text'
               setOption("testOptionText","I am a text","option of type Text");               
           
```

설명을 삭제하려면 빈 설명(setOption(name,value,&quot;))을 사용하여 API를 호출해야 합니다.

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
