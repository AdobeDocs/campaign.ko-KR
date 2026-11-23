---
source-git-commit: 77f8182ea5b1fda08206021a164b2e0ff827890a
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 16%
---
# get환경

>[!WARNING]
>
>이 함수는 온-프레미스 환경에서 사용할 수 있습니다.

>[!NOTE]
>
>**XtkSecurity\_Disable\_GetSetEnv** 옵션을 **true**(으)로 전달하여 이 함수를 비활성화할 수 있습니다.

환경 변수의 값을 반환합니다.

```text
getEnv (name [, default ])
```

## 매개변수

변수의 **이름** 이름입니다.

환경 변수를 찾을 수 없는 경우 사용할 **기본값**.

## 반환 값

변수의 값입니다.

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
