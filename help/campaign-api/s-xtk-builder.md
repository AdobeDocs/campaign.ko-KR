---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 73%
---
# 빌더

애플리케이션 서버의 생성 서비스

## 방법

| 방법 | 설명 |
| --- | --- |
| [BuildOutputNavTree](sm-builder-buildoutputnavtree.md) | 데이터베이스에 있는 탐색 트리 정의를 매개변수에 지정된 탐색 트리 정의와 병합합니다. |
| [BuildOutputSchema](sm-builder-buildoutputschema.md) | 소스 스키마에서 스키마를 생성합니다. |
| [BuildSchema](sm-builder-buildschema.md) | 소스 스키마에서 스키마를 생성합니다. |
| [BuildSchemaFromId](sm-builder-buildschemafromid.md) | 소스 스키마 식별자로 스키마를 생성합니다. |
| [BuildSqlSchemaDiff](sm-builder-buildsqlschemadiff.md) | 실제 데이터베이스 구조와 해당 논리적 설명 간의 차이점을 설명하는 문서를 생성합니다. |
| [BuildUpdateOneSchemaDiff](sm-builder-buildupdateoneschemadiff.md) | 실제 데이터베이스의 테이블과 이 테이블의 논리적 설명 간의 차이점을 설명하는 문서를 생성합니다. |
| [BuildUpdateSchemaDiff](sm-builder-buildupdateschemadiff.md) | 실제 데이터베이스 구조와 해당 논리적 설명 간의 차이점을 설명하는 문서를 생성합니다. |
| [CheckTableExists](sm-builder-checktableexists.md) | 데이터베이스에 테이블이 존재하는지 확인합니다. |
| [CreateDb](sm-builder-createdb.md) | 데이터베이스 만들기 |
| [EvaluateJavaScript](sm-builder-evaluatejavascript.md) | JavaScript 코드 평가. |
| [EvaluateJavaScriptTemplate](sm-builder-evaluatejavascripttemplate.md) | JavaScript 템플릿(JST) 평가. |
| [ExecSql](sm-builder-execsql.md) | SQL 문 실행 |
| [ExecSqlScript](sm-builder-execsqlscript.md) | SQL 스크립트 실행 |
| [GenCreateDbDDL](sm-builder-gencreatedbddl.md) | 데이터베이스 구조를 만드는 데 사용되는 SQL 스크립트를 생성합니다. |
| [GenCreateOrUpdateSchemaSequenceDDL](sm-builder-gencreateorupdateschemasequenceddl.md) | autoPk 스키마 시퀀스를 생성하거나 업데이트하는 데 사용되는 SQL 스크립트를 생성합니다. |
| [GenerateNavTree](sm-builder-generatenavtree.md) | 모든 탐색 트리 정의를 병합하고 결과를 &#39;xtk:merged&#39;(으)로 저장합니다. |
| [GenerateSchema](sm-builder-generateschema.md) | 상위 수준 매개변수를 사용하여 스키마 코드를 생성합니다. |
| [GetDbParams](sm-builder-getdbparams.md) | 데이터 소스의 현재 매개 변수를 검색합니다. |
| [GetDefaultNamespace](sm-builder-getdefaultnamespace.md) | 기본 네임스페이스를 가져옵니다. |
| [패키지 설치](sm-builder-installpackage.md) | 패키지를 설치합니다. |
| [InstallPackageImpl](sm-builder-installpackageimpl.md) | 패키지 설치(내부 방법, 사용하지 말 것). |
| [InstallVendorPackage](sm-builder-installvendorpackages.md) | 하나 이상의 표준 패키지를 설치합니다. |
| [RemoveSchemaLinkRef](sm-builder-removeschemalinkref.md) | 스키마와 이를 참조하는 역방향 링크를 제거합니다. |
| [패키지 참조 확인](sm-builder-resolvepackagereferences.md) | 패키지의 종속성 해결 |
| [UpdateDb](sm-builder-updatedb.md) | 데이터베이스 구조 업데이트. |
| [UpdateSchemaFromDatabase](sm-builder-updateschemafromdatabase.md) | 데이터베이스에서의 실제 표시를 기반으로 스키마를 업데이트합니다. |
| [UpdateTempSchemasFromDatabase](sm-builder-updatetempschemasfromdatabase.md) | 데이터베이스에서의 실제 표시를 기반으로 스키마 컬렉션을 업데이트합니다. |

## 제네릭 메서드

| 방법 | 설명 |
| --- | --- |
| [만들기](f-create.md) | 지정된 스키마에 해당하는 새 엔티티를 만듭니다. |
| [로드](f-load.md) | 주어진 스키마 및 키에 해당하는 엔티티를 로드하고 반환합니다. |
| [저장](m-entity-save.md) | 데이터베이스에 엔티티를 저장합니다. |
