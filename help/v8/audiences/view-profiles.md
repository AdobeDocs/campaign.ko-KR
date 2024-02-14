---
title: Campaign에서 기존 프로필 보기
description: Campaign에서 연락처 데이터에 액세스하는 방법 알아보기
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
source-git-commit: b5574ba2d9fa520b701f7af4e34862304b825a66
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 2%

---

# 기존 프로필 보기{#view-profiles}

다음으로 이동 **[!UICONTROL Profiles and targets]** Adobe Campaign 데이터베이스에 저장된 수신자에 액세스합니다.

이 페이지에서 다음을 수행할 수 있습니다. [새 수신자 만들기](create-profiles.md)기존 수신자를 편집하고 프로필 세부 정보에 액세스합니다.

![](assets/profiles-and-targets.png)

고급 프로필 조작이 필요하면 **[!UICONTROL Explorer]** Adobe Campaign 홈 페이지의 링크.

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>기본 제공 수신자 화면은 XML 스키마 및 관련 양식을 통해 정의됩니다. XML 스키마는에 저장됩니다 **[!UICONTROL Administration > Configuration > Data schemas]** Adobe Campaign 탐색기 트리의 노드입니다. 전문가 사용자만 이러한 스키마를 변경할 수 있습니다.
>

## 프로필 편집{#edit-a-profiles}

새 탭에 세부 정보를 표시할 프로필을 선택하십시오.

![](assets/edit-a-profile.png)

프로필에 대한 데이터는 탭으로 그룹화됩니다. 이러한 탭과 해당 콘텐츠는 특정 설정 및 설치된 패키지에 따라 다릅니다.

일반적인 기본 제공 수신자의 경우 다음 탭에 액세스할 수 있습니다.

* **[!UICONTROL General]**&#x200B;모든 일반 프로필 데이터에 사용할 수 있습니다. 특히 성, 이름, 이메일 주소, 이메일 형식 등을 포함하고 있다.

  이 탭에는 **옵트아웃** 프로필에 대한 플래그: **[!UICONTROL No longer contact (by any channel)]** 옵션을 선택하면 프로파일이 [차단 목록]에 있습니다. 예를 들어 수신자가 뉴스레터에서 구독 취소 링크를 클릭한 경우 이 정보가 연락처 데이터에 추가됩니다. 이러한 수신자는 더 이상 어떤 채널(이메일, DM 등)에서도 타겟팅되지 않습니다. 자세한 정보는 이 [페이지](../send/quarantines.md)를 참조하십시오.

* **연락처 정보**: 선택한 프로필의 DM 주소를 포함합니다.

  이 화면에서 주소의 품질 인덱스와 주소에 포함된 오류 수를 확인할 수 있습니다. 이 정보는 이전 게재 중 발견된 오류 수에 따라 DM 공급자가 직접 사용하며 수동으로 변경할 수 없습니다.

* **기타**&#x200B;을 참조하십시오.

  사용 **[!UICONTROL Field properties…]** 상황별 메뉴를 사용하여 필드 이름을 변경하고 형식을 정의할 수 있습니다.

  ![](assets/other-tab-field-properties.png)

  다음과 같이 새 설정을 입력합니다.

  ![](assets/change-field-properties.png)

  UI에서 업데이트를 확인합니다.

  ![](assets/other-tab-updated.png)


  >[!CAUTION]
  >변경 사항은 모든 수신자에게 적용됩니다.
  >


* **구독**: 모든 활성 서비스 구독입니다. 사용 **기록** 탭으로 이동하여 이 연락처의 구독 및 구독 취소에 대한 세부 정보에 액세스합니다.

  ![](assets/subscription-tab.png)

  구독에 대해 자세히 알아보기 [이 섹션에서](../start/subscriptions.md).

* **게재**&#x200B;를 추가합니다. 이 탭을 사용하여 연락처의 마케팅 기록(모든 채널을 통해 프로필에 지정된 모든 게재 작업의 레이블, 날짜 및 상태)에 액세스할 수 있습니다.


* **추적**&#x200B;를 추가합니다. 이 정보는 게재 후 프로필 동작을 추적하는 데 사용됩니다. 이 탭은 게재에서 추적된 모든 URL의 누적 합계를 보여줍니다. 목록은 구성할 수 있으며, 일반적으로 다음과 같은 항목이 포함됩니다. 클릭한 URL, 클릭한 날짜 및 시간, URL이 포함된 문서

  추적에 대해 자세히 알아보기 [이 섹션에서](../start/tracking.md).


## 활성 프로필 {#active-profiles}

활성 프로필은 고객이 지난 12개월 동안 모든 채널을 통해 통신하려고 시도한 프로필입니다. 라이선스 지표는 활성 프로필을 기반으로 합니다. 다음에서 자세히 알아보기 [Adobe Campaign 제품 설명](https://helpx.adobe.com/kr/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

>[!CAUTION]
>
>* 여러 게재에서 타겟팅한 프로필은 한 번만 카운트됩니다.
>
>* X에서의 소셜 마케팅(이전의 Twitter)의 컨텍스트에서 타겟팅된 프로필은 활성 프로필로 간주되지 않습니다.

Campaign Campaign 컨트롤 패널에서 직접 인스턴스의 활성 프로필 수를 모니터링할 수 있습니다. 자세한 내용은 [Campaign 컨트롤 패널 설명서](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}.
