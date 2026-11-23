---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%
---
# LinkEdit

링크 편집을 위한 컨트롤입니다.

![LinkEdit 컨트롤](assets/linkedit.7cb7bf14.png)

## 속성

**backColor - string** 배경색(btnshadow, white).

**border - string** 컨트롤 윤곽선 스타일(단색, 이중, 인세트, 시작, 없음)을 변경합니다.

**choiceButton - 부울** 선택 단추를 숨기거나 표시합니다(기본적으로 숨겨짐).

**computeStringExpr - string** 계산된 필드 식입니다.

**computestringKey - string** 외래 키가 아닌 계산된 문자열을 업데이트합니다.

**computeStringAlias - string** 계산된 문자열 별칭입니다.

**createMode - string** 링크가 없는 경우(없음, 인라인) 기본 편집 모드로 링크를 만듭니다.

**externalKey - 부울** 외부 키를 사용합니다.

**font-size - integer** 글꼴 크기를 변경합니다.

**양식 - 문자열** 링크 편집 양식을 강제로 적용합니다.

**레이블 - 문자열** 관련 레이블입니다.

**loadEntityOnChange - 부울** 링크가 변경되면 엔터티를 다시 로드합니다.

**필수 - 부울** 빈 값을 거부합니다.

**noAutoComplete - 부울** 자동 완성 모드를 사용하지 않습니다.

**noEdition - 부울** 링크를 수정할 수 없습니다.

**nolabel - 부울** 연결된 레이블을 숨깁니다.

**notifyPathList - string** 연결된 요소에서 쉼표로 구분하여 컨텍스트에 로드할 수 있는 XPath 목록입니다.

**noTransaction - 부울** 트랜잭션 모드를 사용하지 않습니다.

**noZoom - 부울** 링크 편집 양식이 없습니다.

**orderBy - 요소** 선택 일정을 예약합니다.

**읽기 전용 - 부울** 컨트롤을 읽기 전용으로 강제 실행합니다.

**필수 - 부울** 필드는 필수입니다.

링크의 **스키마 - 문자열** 스키마.

**serialize - boolean** 사용자 구성에서 마지막 선택을 저장합니다.

**sysFilter - 요소** 선택 제한.

**xpathMandatory - string** 링크가 비어 있을 수 있는지 여부를 나타내는 부울 속성에 대한 경로입니다.

## 비고

예:

```xml
<input xpath="operator">
  <sysFilter>
    <condition expr="@type= 1/>
  </sysFilter>
  <orderBy>
    <node expr="@name"/>
  </orderBy>
</input>

<input xpath="/tmp/recipient" type="linkEdit" label="Recipient"
       schema="nms:recipient">
```
