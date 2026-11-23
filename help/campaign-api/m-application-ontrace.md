---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 9%
---
# onTrace

추적 메시지 차단 기능을 추가하거나 삭제합니다.

```text
onTrace ( [function ])
```

## 매개변수

**function** 추가할 차단 함수입니다. 이 매개 변수를 생략하면 가장 최근에 추가된 함수가 삭제됩니다.

## 반환 값

없음.

## 비고

함수는 다음 속성을 인수로 사용하는 및 개체를 사용합니다.

* 중력(문자열) - 메시지 심각도(&quot;error&quot;, &quot;warning&quot;, &quot;info&quot;, &quot;status&quot;, &quot;verbose&quot;)
* type (String) - 메시지 유형(&quot;log&quot;, &quot;wdbc&quot; 등)
* message (문자열) - 메시지

함수는 자체 만든 추적 메시지를 가로채지 않으므로 다시 입력할 수 없도록 보호됩니다. 예:

```javascript
var file = new File("c:/temp/trace.txt")
file.open("w")

// Add a new trace handler
application.onTrace(function(log) {
  file.writeln(log.gravity.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the trace handler
application.onTrace()

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
