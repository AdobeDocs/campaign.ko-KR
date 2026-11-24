---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 6%
---
# 응용 프로그램(클래스)

이 클래스에는 응용 프로그램 서버의 특정 속성에 대한 액세스를 제공하는 단일 인스턴스가 있습니다. 이 단일 항목은 `application` 전역 변수를 통해 액세스할 수 있습니다.

## 방법

| 방법 | 설명 |
| --- | --- |
| [hasPackage](m-application-haspackage.md) | 패키지가 설치되었는지 테스트합니다. |
| [getSchema](m-application-getschema.md) | Adobe Campaign 스키마에 대한 매핑을 반환하거나 스키마가 존재하지 않는 경우 null을 반환합니다. |
| [getDBMSType](m-application-getdbmstype.md) | 데이터베이스의 서버 유형을 반환합니다. |
| [getNewIds](m-application-getnewids.md) | 내부 데이터베이스 키의 ID 목록을 반환합니다. |
| [getConnection](m-application-getconnection.md) | 데이터베이스 서버에 대한 새 연결을 반환합니다. |
| [getTimezoneJson](m-application-gettimezonejson.md) | 시간대의 UNIX 기간과 비교한 UTC 시간 및 시작 날짜와의 시간 차이 목록의 JSON 표현인 문자열을 반환합니다. |
| [onLog](m-application-onlog.md) | 저널에 기록된 메시지에 대한 인터셉션 함수를 추가하거나 삭제합니다. |
| [onTrace](m-application-ontrace.md) | 추적 메시지 차단 기능을 추가하거나 삭제합니다. |

## 속성

| 속성 | 설명 |
| --- | --- |
| [buildNumber](p-application-buildnumber.md) | 응용 프로그램 서버의 빌드 번호를 반환합니다. |
| [instanceName](p-application-instancename.md) | 스크립트가 실행되는 인스턴스의 이름입니다. |
| [instanceVarDir](p-application-instancevardir.md) | 스크립트가 실행되는 인스턴스에 대한 &#39;var&#39; 디렉토리의 전체 경로입니다. |
| [instanceUploadDir](p-application-instanceuploaddir.md) | 스크립트가 실행되는 인스턴스에 대한 &#39;업로드&#39; 디렉터리의 전체 경로입니다. |
| [연산자](p-application-operator.md) | 현재 연산자에 대한 정보(이름, 식별자, 권한 등)가 포함된 개체를 반환합니다. |
| [로케일](p-application-locale.md) | Local 인스턴스와 일치하는 문자 문자열을 반환합니다. |

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
