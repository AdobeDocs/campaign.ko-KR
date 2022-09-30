---
title: Campaign에서 기존 프로필 보기
description: Campaign에서 연락처 데이터에 액세스하는 방법 알아보기
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 2%

---

# 기존 프로필 보기{#view-profiles}

찾아보기 **[!UICONTROL Profiles and targets]** Adobe Campaign 데이터베이스에 저장된 수신자에 액세스

이 페이지에서 다음을 수행할 수 있습니다 [새 수신자 만들기](create-profiles.md)기존 수신자를 편집하고 프로필 세부 정보에 액세스합니다.

![](assets/profiles-and-targets.png)

고급 프로필 조작의 경우, **[!UICONTROL Explorer]** 링크를 클릭합니다.

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>기본 제공 받는 사람 화면은 XML 스키마와 관련 양식을 통해 정의됩니다. XML 스키마는 **[!UICONTROL Administration > Configuration > Data schemas]** Adobe Campaign 탐색기 트리의 노드입니다. 전문가 사용자만 이러한 스키마를 변경할 수 있습니다.

## 프로필 편집{#edit-a-profiles}

새 탭에 세부 사항을 표시할 프로필을 선택합니다.

![](assets/edit-a-profile.png)

프로필에 대한 데이터는 탭으로 그룹화됩니다. 이러한 탭 및 콘텐츠는 특정 설정 및 설치된 패키지에 따라 다릅니다.

일반적인 기본 제공 수신자의 경우 다음 탭에 액세스할 수 있습니다.

* **[!UICONTROL General]**, 모든 일반 프로필 데이터에 대해 매핑해야 합니다. 특히 성, 이름, 이메일 주소, 이메일 형식 등이 포함되어 있습니다.

   이 탭에는 **옵트아웃** 프로필에 대한 플래그: http 화이트보드 **[!UICONTROL No longer contact (by any channel)]** 옵션이 선택되어 있으면 프로필이 설정 차단 목록 중입니다. 이 정보는 수신자가 예를 들어 뉴스레터에서 구독 취소 링크를 클릭한 경우 연락처 데이터에 추가됩니다. 이러한 수신자는 더 이상 채널(이메일, DM 등)에서 타겟팅되지 않습니다. 자세한 정보는 이 [페이지](../send/quarantines.md)를 참조하십시오.

* **연락처 정보**: 선택한 프로필의 DM 주소를 포함합니다.

   이 화면에서 주소의 품질 색인과 주소에 포함된 오류 수를 확인할 수 있습니다. 이 정보는 이전 게재 중에 발견된 오류 수를 기반으로 DM 공급자가 직접 사용되며 수동으로 변경할 수 없습니다.

* **기타**: 필요에 따라 개인화하고 채울 수 있는 특정 필드에 대해 설명합니다.

   를 사용하십시오 **[!UICONTROL Field properties…]** 컨텍스트 메뉴를 사용하여 필드 이름을 변경하고 형식을 정의합니다.

   ![](assets/other-tab-field-properties.png)

   다음과 같이 새 설정을 입력합니다.

   ![](assets/change-field-properties.png)

   UI에서 업데이트를 확인합니다.

   ![](assets/other-tab-updated.png)


   >[!CAUTION]
   >변경 사항은 모든 수신자에게 적용됩니다.


* **구독**: 서비스에 대한 모든 활성 구독에 대해 해당됩니다. 를 사용하십시오 **기록** 이 연락처에 대한 구독 및 구독 취소 세부 정보에 액세스하려면 탭입니다.

   ![](assets/subscription-tab.png)

   구독에 대해 자세히 알아보기 [이 섹션](../start/subscriptions.md).

* **게재**: 선택한 프로필에 대한 모든 게재 로그에 대해 히트를 생성합니다. 이 탭을 사용하여 연락처의 마케팅 기록에 액세스합니다. 모든 채널을 통해 프로필에 지정된 모든 게재 작업의 레이블, 날짜 및 상태입니다.


* **추적**: 선택한 프로필에 대한 모든 추적 로그에 대해 히트를 생성합니다. 이 정보는 게재 후 프로필 동작을 추적하는 데 사용됩니다. 이 탭에는 게재에서 추적된 모든 URL의 누적 합계가 표시됩니다. 이 목록은 구성 가능하며, 일반적으로 다음을 포함합니다. 클릭한 URL, 클릭 날짜 및 시간, URL이 포함된 문서

   추적에 대해 자세히 알아보기 [이 섹션](../start/tracking.md).


## 활성 프로필 {#active-profiles}

활성 프로필은 청구 용도로 계산되는 프로필입니다.

청구에는 **활성**. 지난 12개월 동안 어느 채널을 통해 프로필을 타겟팅하거나 통신한 경우 프로필이 활성 상태로 간주됩니다.

여러 게재에서 타겟팅한 프로필은 한 번만 카운트됩니다.

에 대해 활성 프로필 수를 사용할 수 있습니다 **마케팅 인스턴스** 전용. MID(중간 소싱) 및 RT(메시지 센터/실시간 메시징) 인스턴스를 의미하는 실행 인스턴스에는 사용할 수 없습니다.

>[!NOTE]
>
>Campaign Campaign 컨트롤 패널에서 직접 인스턴스에 있는 활성 프로필 수를 모니터링할 수도 있습니다. 자세한 내용은 [Campaign 컨트롤 패널 설명서](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
