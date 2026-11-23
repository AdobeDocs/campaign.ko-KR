---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%
---
# 스키마(클래스)

스키마 정의를 나타냅니다.

`application` 전역 변수의 메서드를 호출하여 스키마를 가져옵니다. 이 개체의 인스턴스에는 프로토타입 개체가 있으므로 해당 메서드를 상속합니다.

## 방법

| 방법 | 설명 |
| --- | --- |
| [toDocument](m-schema-todocument.md) | 스키마를 XML 문서 양식으로 변환합니다. |

## 속성

| 속성 | 설명 |
| --- | --- |
| [열거형](p-schema-enumerations.md) | 이 스키마에 정의된 [열거형](c-enumeration.md) 목록을 포함하는 테이블을 반환합니다. |
| [id](p-schema-id.md) | 문자열 형식의 스키마 식별자입니다. |
| [isLibrary](p-schema-islibrary.md) | 스키마가 구성 요소 라이브러리인지 여부를 지정하는 부울을 반환합니다. |
| [labelSingular](p-schema-labelsingular.md) | 문자열 형식의 스키마 단일 이름. |
| [mappingType](p-schema-mappingtype.md) | 문자열 형식의 스키마 매핑 특성 |
| [md5](p-schema-md5.md) | 16진수 문자열 형식의 스키마 MD5 코드입니다. |
| [네임스페이스](p-schema-namespace.md) | 문자열 형식의 스키마 네임스페이스. |
| [루트](p-schema-root.md) | 스키마의 기본 요소이거나 정의되지 않은 경우 null입니다. |
| [사용자 설명](p-schema-userdescription.md) | 문자열 형식의 스키마 설명. |

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
