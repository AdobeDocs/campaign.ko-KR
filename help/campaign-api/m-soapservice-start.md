---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 11%
---
# 시작

비동기 모드에서 쿼리를 실행합니다.

```text
start (context, name, ...)
```

## 매개변수

**context** [complete](p-soapservice-complete.md) 함수로 전달될 모든 사용자 매개 변수입니다.

**name** 호출할 메서드의 이름입니다.

**..** 함수 매개 변수입니다.

## 반환 값

생성된 쿼리입니다. 이 개체에는 속성이나 함수가 없으므로 작업이 끝날 때까지 대기할 수 있는 [wait](m-soapservice-wait.md) 함수에 유용합니다.

## 비고

서비스 연결은 비동기적이어야 합니다. 연결이 차단되는 경우 예외가 발생합니다. 현재 연결에서 다른 쿼리가 실행 중인 경우 쿼리를 실행할 수 없습니다. 이 경우 예외가 발생합니다.

## 기능

**클래스의 메서드:** [SoapService](c-soapservice.md)

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
