---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 53%
---
# extAccount

외부 계정 정의(이메일, SMS...) 모듈에서 사용됨

## 방법

| 방법 | 설명 |
| --- | --- |
| [CreateFDASchema](sm-extaccount-createfdaschema.md) | 데이터베이스에 작업 스키마 생성 |
| [DeclareTableSpaces](sm-extaccount-declaretablespaces.md) | Adobe Campaign 데이터베이스에서 외부 계정을 통해 액세스할 수 있는 원격 데이터베이스의 특정 테이블스페이스를 사용하는 데 필요한 옵션을 선언합니다. |
| [DeploySQLFunctions](sm-extaccount-deploysqlfunctions.md) | 원격 RDBMS 서버에 Adobe Campaign 페더레이션 데이터 액세스에 필요한 함수 배포 |
| [테스트 계정](sm-extaccount-testaccount.md) | 연결 테스트 수행 |

## 제네릭 메서드

| 방법 | 설명 |
| --- | --- |
| [만들기](f-create.md) | 지정된 스키마에 해당하는 새 엔티티를 만듭니다. |
| [로드](f-load.md) | 주어진 스키마 및 키에 해당하는 엔티티를 로드하고 반환합니다. |
| [저장](m-entity-save.md) | 데이터베이스에 엔티티를 저장합니다. |
