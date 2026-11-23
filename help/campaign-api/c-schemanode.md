---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 1%
---
# SchemaNode(클래스)

스키마의 요소를 나타냅니다.

## 방법

| 방법 | 설명 |
| --- | --- |
| [findNode](m-schemanode-findnode.md) | 노드가 존재하지 않고 mustExist 매개 변수가 false로 설정된 경우 [SchemaNode](c-schemanode.md)의 인스턴스를 반환하거나 null을 반환합니다. |

## 속성

| 속성 | 설명 |
| --- | --- |
| [자식](p-schemanode-children.md) | 각 속성이 그 이름으로 인덱싱된 자식 노드인 개체를 반환합니다. |
| [computeString](p-schemanode-computestring.md) | 현재 노드에서 계산된 문자열을 반환합니다. |
| [dataPolicy](p-schemanode-datapolicy.md) | 현재 노드의 데이터 정책을 제공하는 문자 문자열을 반환합니다. |
| [설명](p-schemanode-description.md) | 현재 노드를 설명하는 문자 문자열을 반환합니다. |
| [defaultValue](p-schemanode-defaultvalue.md) | 현재 노드의 기본값을 제공하는 문자 문자열을 반환합니다. |
| [editType](p-schemanode-edittype.md) | 현재 노드의 편집 유형을 지정하는 문자 문자열을 반환합니다. |
| [열거](p-schemanode-enumeration.md) | 현재 노드에 연결된 열거형이거나 열거형이 없는 경우 null인 [Enumeration](c-enumeration.md) 개체를 반환합니다. |
| [enumerationImage](p-schemanode-enumerationimage.md) | 현재 노드의 이미지 이름을 문자열 형식으로 반환합니다. |
| [folderModel](p-schemanode-foldermodel.md) | 루트 노드에서만 폴더 템플릿이 포함된 문자열을 반환합니다. 다른 노드에서는 undefined를 반환합니다. |
| [이미지](p-schemanode-image.md) | 문자열 형식으로 이미지 이름을 반환합니다. |
| [무결성](p-schemanode-integrity.md) | 링크 무결성 유형을 반환합니다. |
| [키](p-schemanode-keys.md) | 현재 노드의 [SchemaKey](c-schemakey.md) 키에 대한 정의가 있는 테이블을 반환합니다. |
| [hasEnumeration](p-schemanode-hasenumeration.md) | 현재 노드 값이 열거형에 연결되어 있는지 여부를 나타내는 부울을 반환합니다. |
| [childrenCount](p-schemanode-childrencount.md) | 하위 노드의 수를 지정하는 숫자를 반환합니다. |
| [hasSQLTable](p-schemanode-hassqltable.md) | 현재 노드가 SQL 테이블에 연결되어 있는지 여부를 나타내는 부울을 반환합니다. |
| [hasUserEnumeration](p-schemanode-hasuserenumeration.md) | 현재 노드 값이 사용자 열거에 연결되어 있는지 여부를 나타내는 부울을 반환합니다. |
| [도움말](p-schemanode-help.md) | 도움말 문자열을 반환합니다. |
| [스키마](p-schemanode-schema.md) | 이 노드의 부모 [스키마](c-schema.md) 개체의 인스턴스를 반환합니다. |
| [isAdvanced](p-schemanode-isadvanced.md) | 현재 노드의 고급 여부를 나타내는 부울을 반환합니다. |
| [isAnyType](p-schemanode-isanytype.md) | 현재 노드가 일반적인지 여부를 나타내는 부울을 반환합니다. |
| [isAttribute](p-schemanode-isattribute.md) | 현재 노드가 속성인지 여부를 나타내는 부울을 반환합니다. |
| [isAutoIncrement](p-schemanode-isautoincrement.md) | 현재 노드의 값이 자동으로 증가하는지 여부를 나타내는 부울을 반환합니다. |
| [isAutoPK](p-schemanode-isautopk.md) | 현재 노드가 기본 키인지 여부를 나타내는 부울을 반환합니다. |
| [isBlob](p-schemanode-isblob.md) | 현재 노드가 BLOB인지 여부를 나타내는 부울을 반환합니다. |
| [isCalculated](p-schemanode-iscalculated.md) | 현재 노드 값이 계산 결과인지 여부를 나타내는 부울을 반환합니다. |
| [isCDATA](p-schemanode-iscdata.md) | 현재 노드가 CDATA 유형 XML에서 매핑되는지 여부를 나타내는 부울을 반환합니다. |
| [isCollection](p-schemanode-iscollection.md) | 현재 노드가 하위 요소 및/또는 속성의 컬렉션인지 여부를 나타내는 부울을 반환합니다. |
| [isDefaultOnDuplicate](p-schemanode-isdefaultonduplicate.md) | 부울 반환. 추가된 값이 값이면 레코드 중복 제거 중에 기본값(defaultValue에 정의됨)이 기록 중에 자동으로 다시 적용됩니다. |
| [isElementOnly](p-schemanode-iselementonly.md) | 현재 노드가 스키마의 논리적 하위 분할인지 여부를 나타내는 부울을 반환합니다. |
| [isExternalJoin](p-schemanode-isexternaljoin.md) | 노드가 링크이고 조인이 외부인 경우 true입니다. |
| [isFeature](p-schemanode-isfeature.md) | 노드가 기능인지 여부를 나타내는 부울을 반환합니다. |
| [isLink](p-schemanode-islink.md) | 노드가 링크인지 여부를 나타내는 부울을 반환합니다. |
| [isMappedAsXML](p-schemanode-ismappedasxml.md) | 노드가 XML 매핑인지 여부를 나타내는 부울을 반환합니다. |
| [isMemo](p-schemanode-ismemo.md) | 현재 노드가 메모로 매핑되었는지 여부를 나타내는 부울을 반환합니다. |
| [isMemoData](p-schemanode-ismemodata.md) | 현재 노드가 MemoData에 의해 매핑되는지 여부를 나타내는 부울을 반환합니다. |
| [isNotNull](p-schemanode-isnotnull.md) | 현재 노드가 null 값을 고려할 수 있는지 여부를 나타내는 부울을 반환합니다. |
| [isRequired](p-schemanode-isrequired.md) | 현재 노드 값이 필수인지 여부를 나타내는 부울을 반환합니다. |
| [isRoot](p-schemanode-isroot.md) | 노드가 스키마의 루트인지 여부를 나타내는 부울을 반환합니다. |
| [isSQL](p-schemanode-issql.md) | 현재 노드가 SQL에서 매핑되었는지 여부를 나타내는 부울을 반환합니다. |
| [isTemporaryTable](p-schemanode-istemporarytable.md) | 테이블이 임시 테이블인지 여부를 나타내는 부울을 반환합니다. 데이터베이스 생성 중에는 테이블이 생성되지 않습니다. |
| [isUnbound](p-schemanode-isunbound.md) | 현재 노드에 동일한 유형의 하위 노드가 무제한으로 있는지 여부를 나타내는 부울을 반환합니다. |
| [isUser](p-schemanode-isuser.md) | 노드가 사용자 유형인지 여부를 나타내는 부울을 반환합니다. |
| [joinPart](p-schemanode-joinparts.md) | 각 요소가 조인 조건을 나타내는 SchemaNode 인스턴스 테이블을 반환합니다. |
| [레이블](p-schemanode-label.md) | 현재 노드에 대한 설명인 문자열을 반환합니다. |
| [이름](p-schemanode-name.md) | 현재 노드의 이름인 문자열로 이루어진 문자열을 반환합니다. |
| [nodePath](p-schemanode-nodepath.md) | 현재 노드의 절대 경로인 문자 문자열을 반환합니다. |
| [상위](p-schemanode-parent.md) | 부모 개체인 [SchemaNode](c-schemanode.md) 개체를 반환하거나 개체가 없는 경우 null을 반환합니다. |
| [PKSequence](p-schemanode-pksequence.md) | 기본 키에 사용할 시퀀스의 이름을 제공하는 문자열을 반환합니다. |
| [packageStatus](p-schemanode-packagestatus.md) | 패키지 상태를 제공하는 숫자를 반환합니다. |
| [reverseLink](p-schemanode-reverselink.md) | 요소가 링크인 경우 은 대상 스키마를 통해 역방향 링크를 나타내는 [SchemaNode](c-schemanode.md) 개체를 반환합니다. 그렇지 않으면 속성이 정의되지 않습니다. |
| [SQLName](p-schemanode-sqlname.md) | 필드의 SQL 이름입니다. 개체가 SQL 유형 필드가 아닌 경우 속성은 빈 문자열입니다. |
| [SQLTable](p-schemanode-sqltable.md) | 테이블의 SQL 이름입니다. 개체가 주 요소가 아니거나 스키마 매핑이 SQL 유형이 아닌 경우 속성은 빈 문자열입니다. |
| [크기](p-schemanode-size.md) | 문자열 유형의 크기입니다. |
| [tableDefinition](p-schemanode-tabledefinition.md) | 현재 노드가 포함된 테이블에 대한 설명인 [SchemaNode](c-schemanode.md)의 인스턴스입니다. 노드가 없는 경우 null입니다. |
| [target](p-schemanode-target.md) | 링크 대상 스키마의 기본 요소입니다. 개체가 링크가 아니면 속성이 정의되지 않습니다. |
| [유형](p-schemanode-type.md) | 현재 노드의 값 유형을 제공하는 문자 문자열을 반환합니다. |
| [userEnumeration](p-schemanode-userenumeration.md) | 현재 노드에서 사용하는 사용자 열거형의 이름인 문자열을 반환합니다. |

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
