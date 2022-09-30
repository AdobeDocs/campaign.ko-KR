---
title: 대상 매핑 작업
description: 대상 매핑을 사용하고 만드는 방법을 알아봅니다
feature: Audiences, Profiles
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 1%

---

# 대상 매핑 작업{#gs-target-mappings}

기본적으로 게재 템플릿 타겟 **[!UICONTROL Recipients]**. 따라서 대상 매핑은 **nms:recipient** 테이블.

게재에 다른 대상 매핑을 사용하거나 새 대상 매핑을 만들 수 있습니다.

## 기본 제공 대상 매핑 {#ootb-mappings}

Adobe Campaign에는 다음과 같은 기본 제공 target 매핑이 포함되어 있습니다.

| 이름 | 다음 방법 사용 | 스키마 |
|---|---|---|
| 수신자 | 수신자에게 게재(기본 제공 수신자 테이블) | nms:recipient |
| 방문자 수 | 참조(바이럴 마케팅)를 통해 프로필을 수집한 방문자에게 게재를 합니다. | mns:visitor |
| 구독 | 뉴스레터와 같은 정보 서비스를 구독한 수신자에게 게재 | nms:구독 |
| 방문자 구독 | 정보 서비스를 구독한 방문자에게 게재 | nms:visitorSub |
| 연산자 | Adobe Campaign 운영자에게 게재 | nms:operator |
| 외부 파일 | 게재에 필요한 모든 정보가 포함된 파일을 통해 게재 | 연결된 스키마 없음, 대상 입력 없음 |

## 대상 매핑 만들기 {#new-mapping}

대상 매핑을 생성할 수도 있습니다. 예를 들어 다음 경우 사용자 지정 대상 매핑을 추가해야 할 수 있습니다.

* 사용자 지정 수신자 테이블을 사용하고
* 대상 매핑 화면에서 내장된 타겟팅 차원과 다른 필터링 차원을 구성합니다.

에서 사용자 지정 수신자 표에 대해 자세히 알아보십시오 [이 페이지](../dev/custom-recipient.md).

Adobe Campaign target 매핑 생성 마법사는 사용자 지정 대상 매핑을 사용하는 데 필요한 모든 스키마를 만들도록 도와줍니다.

1. 찾아보기 **[!UICONTROL Administration]** `>` **[!UICONTROL Campaign Management]** `>` **[!UICONTROL Target mappings]** Adobe Campaign 탐색기 을 통해 검색할 수 있습니다.

1. 새 대상 매핑을 만들고 사용자 지정 스키마를 타겟팅 차원으로 선택합니다.

   ![](assets/new-target-mapping.png)


1. 프로필 정보가 저장되는 필드를 지정합니다. 성, 이름, 이메일, 주소 등

   ![](assets/wf_new_mapping_define_join.png)

1. 확장 스키마의 접미사를 포함하여 정보 저장 영역에 대한 매개 변수를 지정하여 쉽게 식별할 수 있습니다.

   ![](assets/wf_new_mapping_define_names.png)

   제외( )를 저장할지 여부를 선택할 수 있습니다&#x200B;**제외 로그**), 메시지( )**broadlog**) 또는 를 포함할 수도 있습니다.

   이 게재 매핑에 대한 추적을 관리할지 여부를 선택할 수도 있습니다(**trackinglog**).

1. 그런 다음 고려할 확장을 선택합니다. 확장 유형은 Campaign 설정 및 추가 기능에 따라 다릅니다.

   ![](assets/wf_new_mapping_define_extensions.png)

   을(를) 클릭합니다. **[!UICONTROL Save]** 버튼 - 게재 매핑 생성 시작: 연결된 모든 테이블은 선택한 매개변수를 기준으로 자동으로 생성됩니다.

