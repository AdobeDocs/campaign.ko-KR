---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 4%
---
# DBEngine(클래스)

데이터베이스 연결을 나타냅니다.

이 개체를 사용하면 데이터베이스를 쿼리하고 관련 작업을 수행할 수 있습니다.

이 클래스의 대부분의 메서드에는 &#39;sql&#39; 권한이 필요합니다. 연산자가 메서드를 호출하고 적절한 권한이 없으면 예외가 발생합니다. 일반적으로 데이터베이스를 변경하는 모든 메서드는 &#39;sql&#39; 권한이 필요한 반면, 단순히 정보를 보는 메서드는 필요하지 않습니다. 권한이 필요한지 여부는 각 방법에 대한 설명서를 참조하십시오.

## 방법

| 방법 | 설명 |
| --- | --- |
| [batchDelete](m-dbengine-batchdelete.md) | 패킷별로 테이블의 레코드를 삭제합니다. |
| [dispose](m-dbengine-dispose.md) | 연결된 모든 리소스에서 연결을 해제합니다. |
| [실행](m-dbengine-execute.md) | SQL 명령을 실행합니다. |
| [exec](m-dbengine-exec.md) | execute 명령의 별칭입니다. 이 함수는 더 이상 사용되지 않습니다. [execute()](m-dbengine-execute.md)을(를) 사용하십시오. |
| [쿼리](m-dbengine-query.md) | SELECT 유형 SQL 쿼리를 실행합니다. |
| [queryWithTypes](m-dbengine-querywithtypes.md) | 열 유형 지정으로 SELECT 유형 SQL 쿼리를 실행합니다. |
| [시작](m-dbengine-begin.md) | 연결에서 새 트랜잭션을 시작합니다. |
| [커밋](m-dbengine-commit.md) | 연결에 대해 진행 중인 트랜잭션을 승인합니다. |
| [롤백](m-dbengine-rollback.md) | 연결에서 진행 중인 트랜잭션을 취소합니다. |

## 속성

| 속성 | 설명 |
| --- | --- |
| [isOracle](p-dbengine-isoracle.md) | 데이터베이스가 Oracle인 경우 true를 반환합니다. |
| [isDB2](p-dbengine-isdb2.md) | 데이터베이스가 DB2 유형인 경우 true를 반환합니다. |
| [isMySQL](p-dbengine-ismysql.md) | 데이터베이스가 MySQL 유형인 경우 true를 반환합니다. |
| [isMSSQL](p-dbengine-ismssql.md) | 데이터베이스가 SQL Server인 경우 true를 반환합니다. |
| [isPostgreSQL](p-dbengine-ispostgresql.md) | 데이터베이스가 PostgreSQL인 경우 true를 반환합니다. |
| [isSybase](p-dbengine-issybase.md) | 데이터베이스가 Sybase인 경우 true를 반환합니다. |
| [isSybaseIQ](p-dbengine-issybaseiq.md) | 데이터베이스가 Sybase IQ인 경우 true를 반환합니다. |
| [isFDA](p-dbengine-isfda.md) | FDA를 통해 데이터베이스에 액세스하면 true를 반환합니다. |
| [isBroken](p-dbengine-isbroken.md) | 연결을 더 이상 사용할 수 없는 경우 true를 반환합니다. |
| [useUnicodeData](p-dbengine-useunicodedata.md) | 데이터베이스에 유니코드 데이터가 포함되어 있으면 true를 반환합니다. |
| [useNChar](p-dbengine-usenchar.md) | Adobe Campaign에서 NCHAR, NVARCHAR, NCLOB, NTEXT 유형 필드를 사용하는 경우 true를 반환합니다. |

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
