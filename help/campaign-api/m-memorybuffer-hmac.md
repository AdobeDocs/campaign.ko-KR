---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 11%
---
# hmac

버퍼의 MD5, SHA-1 또는 SHA-256 해시를 계산합니다.

```text
hmac (key [, algo ])
```

## 매개변수

버퍼 형식의 **키** 키입니다.

사용할 **algo** 해시 유형입니다. 가능한 값은 &quot;MD5&quot;, &quot;SHA1&quot; 또는 &quot;SHA256&quot;입니다. 대소문자를 구분하지 않으므로 소문자 또는 대문자로 값을 입력할 수 있습니다. 매개 변수를 지정하지 않으면 기본적으로 &quot;SHA1&quot; 값이 선택됩니다.

## 반환 값

버퍼의 해시 MD5, SHA-1 또는 SHA-256(선택한 해시 유형에 따라)입니다.

## 기능

**클래스의 메서드:** [MemoryBuffer](c-memorybuffer.md)

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
