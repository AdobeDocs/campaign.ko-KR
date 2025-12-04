---
title: Campaign에서 기존 프로필 보기
description: Campaign에서 연락처 데이터에 액세스하는 방법 알아보기
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
version: Campaign v8, Campaign Classic v7
source-git-commit: 3453820bb0eca7847ec55d7e6ea15766a57ab94e
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 2%

---

# 기존 프로필 보기 {#view-profiles}

Adobe Campaign 데이터베이스에 저장된 수신자에 액세스하려면 **[!UICONTROL Profiles and targets]**(으)로 이동하십시오.

이 페이지에서 [새 받는 사람을 만들고](create-profiles.md)기존 받는 사람을 편집하고 해당 프로필 세부 정보에 액세스할 수 있습니다.

![](assets/profiles-and-targets.png)

고급 프로필 조작을 위해 Adobe Campaign 홈 페이지의 **[!UICONTROL Explorer]** 링크에서 캠페인 트리에 액세스합니다.

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>기본 제공 수신자 화면은 XML 스키마 및 관련 양식을 통해 정의됩니다. XML 스키마는 Adobe Campaign 탐색기 트리의 **[!UICONTROL Administration > Configuration > Data schemas]** 노드에 저장됩니다. 전문가 사용자만 이러한 스키마를 변경할 수 있습니다.
>

## 프로필 편집 {#edit-a-profiles}

새 탭에 세부 정보를 표시할 프로필을 선택하십시오.

![](assets/edit-a-profile.png)

프로필에 대한 데이터는 탭으로 그룹화됩니다. 이러한 탭과 해당 콘텐츠는 특정 설정 및 설치된 패키지에 따라 다릅니다.

일반적인 기본 제공 수신자의 경우 다음 탭에 액세스할 수 있습니다.

* **[!UICONTROL General]**(모든 일반 프로필 데이터). 특히 성, 이름, 이메일 주소, 이메일 형식 등을 포함하고 있다.

  이 탭에는 프로필에 대한 **옵트아웃** 플래그도 저장됩니다. **[!UICONTROL No longer contact (by any channel)]** 옵션을 선택하면 프로필이 차단 목록에 추가하다에 저장됩니다. 예를 들어 수신자가 뉴스레터에서 구독 취소 링크를 클릭한 경우 이 정보가 연락처 데이터에 추가됩니다. 이러한 수신자는 더 이상 어떤 채널(이메일, DM 등)에서도 타겟팅되지 않습니다. 자세한 정보는 이 [페이지](../send/quarantines.md)를 참조하십시오.

* **연락처 정보**(선택한 프로필의 DM 주소 포함).

  이 화면에서 주소의 품질 인덱스와 주소에 포함된 오류 수를 확인할 수 있습니다. 이 정보는 이전 게재 중 발견된 오류 수에 따라 DM 공급자가 직접 사용하며 수동으로 변경할 수 없습니다.

* 필요에 따라 개인화하고 채울 수 있는 특정 필드의 경우 **기타**.

  **[!UICONTROL Field properties…]** 상황별 메뉴를 사용하여 필드 이름을 변경하고 해당 형식을 정의합니다.

  ![](assets/other-tab-field-properties.png)

  다음과 같이 새 설정을 입력합니다.

  ![](assets/change-field-properties.png)

  UI에서 업데이트를 확인합니다.

  ![](assets/other-tab-updated.png)


  >[!CAUTION]
  >변경 사항은 모든 수신자에게 적용됩니다.
  >


* **구독**(서비스에 대한 모든 활성 구독). **내역** 탭을 사용하여 이 연락처의 구독 및 구독 취소에 대한 세부 정보에 액세스할 수 있습니다.

  ![](assets/subscription-tab.png)

  이 섹션[에서 &#x200B;](../start/subscriptions.md)구독에 대해 자세히 알아보세요.

* 선택한 프로필의 모든 게재 로그에 대해 **게재**. 이 탭을 사용하여 연락처의 마케팅 기록(모든 채널을 통해 프로필에 지정된 모든 게재 작업의 레이블, 날짜 및 상태)에 액세스할 수 있습니다.


* 선택한 프로필의 모든 추적 로그에 대해 **추적**&#x200B;합니다. 이 정보는 게재 후 프로필 동작을 추적하는 데 사용됩니다. 이 탭은 게재에서 추적된 모든 URL의 누적 합계를 보여줍니다. 목록은 구성할 수 있으며, 일반적으로 다음과 같은 항목이 포함됩니다. 클릭한 URL, 클릭한 날짜 및 시간, URL이 포함된 문서

  이 섹션[에서 &#x200B;](../send/tracking.md) 추적에 대해 자세히 알아보세요.
