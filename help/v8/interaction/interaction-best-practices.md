---
product: campaign
title: Adobe Campaign 상호 작용 모범 사례
description: Adobe Campaign에서 상호 작용 모듈을 관리하는 우수 사례
exl-id: 28f3a5bc-67f5-413e-b2ba-35c341f9ec5f
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 0%

---

# 상호 작용 모범 사례{#interaction-best-practices}

## 일반 권장 사항 {#general-recommendations}

Adobe Campaign에서 오퍼를 관리하려면 효율적으로 운영해야 합니다. 문제를 방지하려면 연락처 수와 오퍼 카테고리 및 오퍼 수 간에 균형을 찾아야 합니다.

이 섹션에서는 **상호 작용** 자격 규칙, 사전 정의된 필터, 워크플로우 활동 및 데이터베이스 옵션을 비롯한 Adobe Campaign의 모듈입니다.

* When **상호 작용 구현 및 구성**, 다음 권장 사항을 알고 있어야 합니다.

   * 배치 엔진의 경우(일반적으로 이메일과 같은 아웃바운드 커뮤니케이션에서 사용됨) 여러 연락처를 동시에 처리할 수 있으므로 처리량이 주요 관심사입니다. 일반적인 병목 현상은 데이터베이스 성능입니다.
   * 단일 엔진의 기본 제한(일반적으로 웹 사이트의 배너와 같은 인바운드 통신에 사용됨)은 누군가가 답변을 기다리고 있으므로 지연입니다. 일반적인 병목 현상은 CPU 성능입니다.
   * 오퍼 카탈로그 디자인은 Adobe Campaign 성능에 큰 영향을 줍니다.
   * 많은 오퍼를 사용하여 작업할 때 가장 좋은 방법은 여러 오퍼 카탈로그로 분할하는 것입니다.

* 다음은 작업 시 몇 가지 모범 사례에 대한 목록입니다 **자격 규칙**:

   * 규칙을 단순화합니다. 규칙 복잡성은 조회 범위를 확장하는 동안 성능에 영향을 줍니다. 복잡한 규칙은 5개 이상의 조건이 있는 모든 규칙입니다.
   * 성능을 향상시키기 위해 여러 오퍼에서 공유되는 사전 정의된 개별 필터에서 규칙을 분류할 수 있습니다.
   * 가장 제한적인 오퍼 카테고리 규칙을 트리에서 가능한 가장 높은 위치에 놓습니다. 이렇게 하면 가장 많은 연락처를 먼저 필터링하여 대상 번호를 줄이고 더 많은 규칙에 의해 처리되지 않게 됩니다.
   * 가장 비싼 규칙을 트리 맨 아래에 시간이나 처리에 포함시킵니다. 이렇게 하면 나머지 타겟 대상에서만 이러한 규칙이 실행됩니다.
   * 전체 트리를 스캔하지 않도록 특정 카테고리에서 시작합니다.
   * 처리 시간을 절약하려면 조인으로 복잡한 규칙을 작성하는 대신 합계를 미리 계산하십시오. 이렇게 하려면 자격 규칙 내에서 조회할 수 있는 참조 테이블에 고객 데이터를 저장해 보십시오.
   * 최소 가중치를 사용하여 쿼리 수를 제한합니다.
   * 오퍼 공간당 오퍼 수가 제한되어 있는 것이 좋습니다. 따라서 주어진 공간에서 오퍼를 신속하게 검색할 수 있습니다.
   * 특히 자주 사용하는 조회 열 시 인덱스를 사용합니다.

* 다음은 와(과) 관련된 몇 가지 우수 사례 목록입니다 **제안 테이블**:

   * 가능한 한 빨리 처리하려면 최소 수의 규칙을 사용하십시오.
   * 제안 테이블에 있는 레코드 수를 제한합니다. 상태 업데이트를 추적하는 데 필요한 레코드와 규칙에 필요한 레코드만 보관하고 다른 시스템에 보관합니다.
   * 인덱스 재구축이나 테이블 재생성과 같이 제안 테이블에서 데이터베이스 유지 관리를 집중적으로 수행합니다.
   * 대상당 필요한 제안 수를 제한합니다. 실제로 사용할 것 이상을 설정하지 마십시오.
   * 규칙 기준에서 가능한 한 조인을 사용하지 마십시오.

## 오퍼 관리 시 팁 {#tips-managing-offers}

이 섹션에서는 오퍼를 관리하고 Adobe Campaign에서 상호 작용 모듈을 사용하는 방법에 대한 자세한 조언을 제공합니다.

### 이메일에 여러 오퍼 공간 {#multiple-offer-spaces}

게재에 오퍼를 포함할 때 일반적으로 오퍼는 를 통해 캠페인 워크플로우에서 업스트림으로 선택됩니다 **데이터 보강** 워크플로우 활동(또는 다른 유사한 활동).

에서 오퍼를 선택할 때 **데이터 보강** 활동을 만들 때 사용할 오퍼 공간을 선택할 수 있습니다. 그러나 선택한 오퍼 공간에 관계없이 게재 사용자 지정 메뉴는 게재에 설정된 오퍼 공간에 따라 다릅니다.

아래 예에서는 게재에서 선택한 오퍼 공간이 있습니다 **[!UICONTROL Email (Environment - Recipient)]**:

![](assets/Interaction-best-practices-offer-space-selected.png)

게재에서 선택한 오퍼 공간에 HTML 렌더링 기능이 설정되어 있지 않으면 게재 메뉴에 표시되지 않고 선택할 수 없습니다. 이는 에서 선택한 오퍼 공간과 독립적입니다 **데이터 보강** 활동.

아래 예에는 게재에서 선택한 오퍼 공간에 렌더링 함수가 있으므로 드롭다운 목록에서 HTML 렌더링 함수를 사용할 수 있습니다.

![](assets/Interaction-best-practices-HTML-rendering.png)

이 함수는 다음과 같은 코드를 삽입합니다. `<%@ include proposition="targetData.proposition" view="rendering/html" %>`.

제안을 선택하면 **[!UICONTROL view]** 속성은 다음과 같습니다.
* &quot;rendering/html&quot;: html 렌더링. HTML 렌더링 기능을 사용합니다.
* &quot;offer/view/html&quot;: html 콘텐츠. HTML 렌더링 기능을 사용하지 않습니다. 여기에는 HTML 필드만 포함됩니다.

단일 이메일 게재에 여러 오퍼 공백을 포함하고, 일부 오퍼에 렌더링 기능이 있고 일부 오퍼에는 렌더링 기능이 없는 경우, 어느 오퍼에서 어느 오퍼 공간을 사용하고 어떤 오퍼 공간에는 렌더링 기능이 있는지 기억해야 합니다.

따라서 문제를 방지하려면 오퍼 공간에만 HTML 컨텐츠가 필요한 경우에도 모든 오퍼 공간에 HTML 렌더링 기능이 정의된 것이 좋습니다.

### 제안 로그 표에서 등급 설정 {#rank-proposition-log-table}

오퍼 공백은 proposition이 생성되거나 수락될 때 제안 테이블에 데이터를 저장할 수 있습니다.

![](assets/Interaction-best-practices-offer-space-storage.png)

하지만 인바운드 상호 작용에만 적용됩니다.

또한 아웃바운드 상호 작용을 사용할 때와 상호 작용 모듈 없이 아웃바운드 오퍼를 사용할 때 제안 테이블에 추가 데이터를 저장할 수도 있습니다.

이름이 제안 테이블의 필드 이름과 일치하는 워크플로우 임시 테이블의 모든 필드는 제안 테이블의 동일한 필드에 복사됩니다.

예를 들어, 오퍼를 수동으로 (상호 작용 없이) 선택할 때 **데이터 보강** 워크플로우 활동에서 표준 필드는 다음과 같이 정의됩니다.

![](assets/Interaction-best-practices-manual-offer-std-fields.png)

다음과 같은 추가 필드를 추가할 수 있습니다. `@rank` 필드:

![](assets/Interaction-best-practices-manual-offer-add-fields.png)

왜냐하면 이름이 인 제안 테이블에 필드가 있기 때문입니다 `@rank`을 지정하면 워크플로우 임시 테이블의 값이 복사됩니다.

제안 테이블에 추가 필드를 저장하는 방법에 대한 자세한 내용은 [이 섹션](interaction-send-offers.md#storing-offer-rankings-and-weights).

상호 작용을 하는 아웃바운드 오퍼의 경우, 이 기능은 여러 오퍼를 선택하고 오퍼가 전자 메일에 표시될 순서를 기록하려는 경우 유용합니다.

또한 제안 테이블에 현재 지출 수준과 같은 추가 메타데이터를 직접 저장하여 오퍼가 생성된 시간에 소비에 대한 기록 레코드를 유지할 수도 있습니다.

아웃바운드 상호 작용을 사용하는 경우 `@rank` 위의 예와 같이 필드를 추가할 수 있지만, 이 값은 상호 작용에서 반환한 순서에 따라 자동으로 설정됩니다. 예를 들어 상호 작용을 사용하여 세 개의 오퍼를 선택하는 경우, `@rank` 필드에는 값 1, 2 및 3이 반환됩니다.

상호 작용을 사용하고 오퍼를 수동으로 선택할 때 사용자는 두 접근 방식을 결합할 수 있습니다. 예를 들어 사용자가 수동으로 `@rank` 수동으로 선택한 오퍼에 대해 1이 되도록 필드를 설정하고 다음과 같은 표현식을 사용합니다. `"1 + @rank"` 상호 작용에 의해 반환되는 오퍼에 대해 해당됩니다. 상호 작용이 세 개의 오퍼를 선택한다고 가정할 경우, 두 접근 방법 모두에서 반환되는 오퍼는 1-4로 평가됩니다.

![](assets/Interaction-best-practices-manual-offer-combined.png)

### nms:offer 스키마 확장 {#extending-nms-offer-schema}

nms:offer 스키마를 확장할 때는 이미 설정된 기본 구조를 따라야 합니다.
* 아래의 컨텐츠 저장소에 대한 새 필드를 정의합니다. `<element name="view">`.
* 각 새 필드를 두 번 정의해야 합니다. 한 번은 일반 XML 필드로, 그리고 한 번은 이름에 &quot;_js&quot;가 추가된 CDATA XML 필드로 사용됩니다. 예제:

   ```
   <element label="Price" name="price" type="long" xml="true"/>
   <element advanced="true" label="Script price" name="price_jst" type="CDATA" xml="true"/>
   ```

* 추적할 URL이 포함된 모든 필드는 아래에 배치해야 합니다 `<element name="trackedUrls">` 다음 위치에서 찾을 수 있습니다. `<element name="view" >`.
