---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 15%
---
# exec

execute 명령의 별칭입니다. 이 함수는 더 이상 사용되지 않습니다. [execute()](m-dbengine-execute.md)을(를) 사용하십시오.

```text
exec (command [, value1, ... ])
```

## 매개변수

**command** SQL 명령입니다.

명령의 **값1, ...** 변수.

## 반환 값

실행된 명령에 적용되는 경우 업데이트되거나 삽입된 기록 수입니다(0이 아닌 경우).

## 기능

**클래스의 메서드:** [DBEngine](c-dbengine.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
