---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 3%
---
# 로그온

세션을 엽니다

```text
[ String sessionToken, sessionInfo sessionInfo, String securityToken ] = Logon ( String login, String password, XML parameters )
```

## 매개변수

**로그인** 사용자 계정

사용자 로그인과 연결된 **암호** 암호

**매개 변수** 연결 설정

## 반환 값

**sessionToken** 세션 토큰

**세션 정보** 세션 매개 변수

**securityToken** 보안 토큰

## 계정 잠금 메커니즘 구성

계정 잠금 메커니즘은 logon() API 내에서 사용할 수 있습니다. 지정된 기간 내에 특정 횟수의 연속 로그인 시도 실패 후 더 이상 로그인을 시도하지 못하도록 합니다.

네 가지 옵션을 사용하여 잠금 메커니즘을 구성할 수 있습니다.

* **XtkSecurity\_max\_Unsuccessul\_Attempts\_Allowed**: 지정된 기간 내에 최대 키 차단 시도에 실패했습니다. 기본값은 3입니다.
* **XtkSecurity\_Initial\_Ban\_Duration**: 키를 처음으로 금지하는 기간입니다. 기본 지속 시간은 5분입니다.
* **XtkSecurity\_Max\_Ban\_Duration**: 키를 금지할 수 있는 최대 기간입니다.
* **XtkSecurity\_Examine\_Window**: 잘못된 키를 금지하기 위해 실패한 로그인 시도 횟수를 추적하는 시간 창입니다. 기본 지속 시간은 10분입니다.

예를 들어, 10분 동안 3번의 시도를 성공하지 못하면 5분 동안 키가 차단됩니다.

## 기능

**스키마:** [xtk:session](s-xtk-session.md)

**정적:**

예
