---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 73%
---
# session

애플리케이션 서버에 대한 세션

## 방법

| 방법 | 설명 |
| --- | --- |
| [중복 규칙 적용](sm-session-applyduplicaterules.md) | 복제 설정(기본값 포함)을 지정된 문서에 적용합니다. |
| [BearerTokenLogon](sm-session-bearertokenlogon.md) | 연결 토큰 |
| [암호 변경](sm-session-changepassword.md) | 현재 암호 변경 |
| [DeleteCollection](sm-session-deletecollection.md) | 조건에 따라 엔티티 목록 삭제 |
| [비교](sm-session-diff.md) | 문서의 현재 버전과 원래 버전을 반환합니다. |
| [복제](sm-session-duplicate.md) | 소스 문서에서 새 문서를 만듭니다. |
| [DuplicateTo](sm-session-duplicateto.md) | 소스 문서에서 지정된 폴더로 새 문서를 복제합니다. |
| [DuplicateWithMappingId](sm-session-duplicatewithmappingid.md) | ID 매핑을 사용하여 소스 문서에서 새 문서를 복제합니다. |
| [암호화](sm-session-encrypt.md) | 인스턴스 키로 문자열을 암호화합니다. |
| [EncryptServerPassword](sm-session-encryptserverpassword.md) | 서버 키로 문자열을 암호화합니다. |
| [FormatDataPolicy](sm-session-formatdatapolicy.md) | 매개 변수로 전달된 데이터 정책에 따라 문자열에 변환을 적용합니다. 실패할 경우 문자열을 변경하지 않습니다. |
| [GetActiveApplicationMenu](sm-session-getactiveapplicationmenus.md) | 현재 로그인에 사용할 수 있는 애플리케이션의 메뉴가 포함된 문서를 반환합니다. |
| [GetCnxInfo](sm-session-getcnxinfo.md) | 현재 연결에서 정보를 복구합니다. |
| [GetDefaultEntity](sm-session-getdefaultentity.md) | 기본값으로 빈 엔티티가 포함된 문서를 반환합니다. |
| [GetDirtyCacheEntities](sm-session-getdirtycacheentities.md) | 더티 캐시 엔티티 반환 |
| [GetEntityIfMoreRecent](sm-session-getentityifmorerecent.md) | MD5 키가 매개변수로 제공된 것과 다른 경우 엔티티를 로드합니다. |
| [이미지 가져오기](sm-session-getimages.md) | 이미지 목록 로드 |
| [GetNewIds](sm-session-getnewids.md) | 데이터베이스의 내부 키 식별자 목록을 수집합니다. |
| [GetNewIdsEx](sm-session-getnewidsex.md) | 시퀀스 이름이 지정된 데이터베이스에서 고유 식별자 목록을 가져옵니다. |
| [GetOption](sm-session-getoption.md) | 데이터베이스에 저장된 옵션의 값을 반환합니다. |
| [GetPkList](sm-session-getpklist.md) | 인스턴스 식별자의 목록을 가져옵니다. |
| [GetServerTime](sm-session-getservertime.md) | 서버 날짜 및 시간을 반환합니다. |
| [GetUserInfo](sm-session-getuserinfo.md) | 현재 운영자에 대한 정보 |
| [HashPassword](sm-session-hashpassword.md) | 서버 키로 암호를 해시합니다. |
| [ImportCollection](sm-session-importcollection.md) | 가져오기를 사용하여 엔티티 목록 업데이트 |
| [KillSession](sm-session-killsession.md) | 지정된 세션을 닫습니다. |
| [로드](sm-session-load.md) | 엔티티 로드 |
| [LoadAsText](sm-session-loadastext.md) | 엔티티 콘텐츠를 텍스트로 가져오기 |
| [LoadIfExists](sm-session-loadifexists.md) | 존재하는 경우 엔티티를 로드합니다. |
| [로그오프](sm-session-logoff.md) | 현재 세션 닫기 |
| [로그온](sm-session-logon.md) | 세션을 엽니다 |
| [새 인스턴스](sm-session-newinstance.md) | 새 문서 생성, 사전 초기화되었지만 저장되지 않음 |
| [제거](sm-session-remove.md) | 엔티티 삭제 |
| [서버 종료](sm-session-servershutdown.md) | 서버 종료 요청 |
| [SetDefaultValues](sm-session-setdefaultvalues.md) | 기본적으로 xpath를 사용해 값 수정 |
| [기본값 설정](sm-session-setdefaults.md) | 기본 값 설정 |
| [TestCnx](sm-session-testcnx.md) | 연결을 테스트합니다. |
| [쓰기](sm-session-write.md) | 엔티티 업데이트 |
| [WriteCollection](sm-session-writecollection.md) | 엔티티 목록 업데이트 |

## 제네릭 메서드

| 방법 | 설명 |
| --- | --- |
| [만들기](f-create.md) | 지정된 스키마에 해당하는 새 엔티티를 만듭니다. |
| [로드](f-load.md) | 주어진 스키마 및 키에 해당하는 엔티티를 로드하고 반환합니다. |
| [저장](m-entity-save.md) | 데이터베이스에 엔티티를 저장합니다. |
