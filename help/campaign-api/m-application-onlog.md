---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 6%
---
# onLog

저널에 기록된 메시지에 대한 인터셉션 함수를 추가하거나 삭제합니다.

```text
onLog ( [function ])
```

## 매개변수

**function** 추가할 차단 함수입니다. 이 매개 변수를 생략하면 가장 최근에 추가된 함수가 삭제됩니다.

## 반환 값

없음.

## 비고

가장 최근에 추가된 함수를 먼저 호출합니다. 함수는 다음 속성을 인수로 사용하는 및 개체를 사용합니다.

* type (숫자) - 메시지 유형 (0=error, 1=warning, 2=information, 3=status, 4=verbose)
* code (숫자) - 오류 코드(오류가 아닌 경우 0)
* object (String) - 메시지에 연결된 object (unused)
* message (문자열) - 메시지

함수는 부울을 반환해야 합니다. true 값은 다음 차단 함수가 메시지를 수신하지 못하도록 합니다. 함수는 저널 자체에 쓴 메시지를 가로채지 않고 다시 입력할 수 있도록 보호됩니다. 예:

```javascript
var file = new File("c:/temp/log.txt")
file.open("w")

// Add a new log handler
application.onLog(function(log) {
  file.writeln(log.type.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the log handler
application.onLog()

// This message won't be caught
logInfo("Finished.")

file.close()
```

## 기능

**클래스의 메서드:** [응용 프로그램](c-application.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
