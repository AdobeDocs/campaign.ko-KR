---
product: campaign
title: '활용 사례: 웹 양식'
description: '활용 사례: 웹 양식'
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: 7aa4646d-1325-47c2-b553-6fe375c48973
TQID: 'https://experienceleague.adobe.com/Zw-cfoQrq1PAe-swZ7gvMNyTb4ciCMF2kdT7fN2zLsg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
  - id: e739ee2b-6228-412e-878f-45de0791417d
    internal-label: Use cases
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '1451'
ht-degree: 0%
---
# 활용 사례: 웹 양식{#use-cases-web-forms}



## 이중 옵트인으로 구독 양식 만들기 {#create-a-subscription--form-with-double-opt-in}

정보 서비스를 제공할 때 수신자는 연결된 모든 통신을 수신하려면 구독해야 합니다. 부적절한 커뮤니케이션을 방지하고 수신자가 의도적으로 구독했는지 확인하려면 이중 옵트인을 만들기 위해 구독 확인 요청을 보내는 것이 좋습니다. 구독은 사용자가 확인 메시지에 포함된 링크를 클릭한 경우에만 유효합니다.

이 예제는 다음 시나리오를 기반으로 합니다.

1. 임시 서비스를 구독하기 위한 확인란이 포함된 웹 사이트에 뉴스레터 구독 양식 만들기. 이 서비스를 사용하면 구독 확인 메시지를 게재할 수 있습니다.
1. 웹 양식에 연결된 게재 템플릿을 사용하여 구독 확인 게재 만들기. 여기에는 뉴스레터 구독 양식을 호출하고 구독 승인 메시지를 표시하는 확인 링크가 포함되어 있습니다.

### 1단계 - 정보 서비스 만들기 {#step-1---creating-information-services}

1. 수신자에게 제공할 뉴스레터 구독 서비스를 만듭니다. 뉴스레터를 만드는 방법에 대한 자세한 내용은 [이 섹션](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/about-services-and-subscriptions){target="_blank"}을 참조하세요.

   레이블, 내부 이름, 유형 전자 메일 및 모드 뉴스레터 필드가 있는 주간 뉴스레터 서비스에 대한 ![서비스 대화 상자.](assets/s_ncs_admin_survey_double-opt-in_sample_1.png)

1. 두 번째 정보 서비스를 만듭니다. 이 서비스는 구독 확인 메시지를 보내기 위한 게재 템플릿에 연결된 임시 서비스입니다.

   ![Email, Mode Newsletter 및 해당 폴더를 표시하는 임시 서비스(temp_service) 대시보드](assets/s_ncs_admin_survey_double-opt-in_sample_1c.png)

### 2단계 - 확인 메시지 만들기 {#step-2---creating-confirmation-messages}

확인 메시지는 임시 서비스 수준에서 참조되는 전용 게재 템플릿을 통해 전송됩니다.

1. **[!UICONTROL Explorer]**&#x200B;에서 **[!UICONTROL Resources > Templates > Delivery templates]**&#x200B;을(를) 선택합니다.
1. 구독 확인 메시지를 보내기 위한 게재 템플릿을 만듭니다.
1. 게재 템플릿을 수신자 대신 구독 대상 매핑과 연결하려면 **[!UICONTROL Email parameters]**&#x200B;에서 **[!UICONTROL To]** 단추를 클릭하십시오.

   ![구독(nms:subscription) 대상 매핑이 선택된 게재 템플릿의 대상 선택 대화 상자](assets/s_ncs_admin_survey_double-opt-in_sample_1d.png)

1. 이 게재 수신자가 승인을 확인하지 않았기 때문에 아직 데이터베이스 차단 목록에 추가하다에 있습니다. 이들이 이 통신을 수신하려면 차단 목록에 추가하다에서 수신자를 타겟팅하기 위해 이 템플릿을 기반으로 하는 게재를 승인해야 합니다.

   이렇게 하려면 **[!UICONTROL Exclusions]** 탭을 클릭합니다.

1. **[!UICONTROL Edit...]** 링크를 클릭하고 **[!UICONTROL Exclude recipients who no longer want to be contacted]** 옵션의 선택을 취소합니다.

   <!-- ![](assets/s_ncs_admin_survey_double-opt-in_sample_4d.png)-->

   >[!IMPORTANT]
   >
   >이 옵션은 이 유형의 컨텍스트에서만 비활성화될 수 있습니다.

1. 게재를 개인화하고 확인 링크를 메시지 콘텐츠에 삽입합니다. 이 링크를 사용하면 웹 양식에 액세스하여 구독 확인을 기록할 수 있습니다.

   ![게재 편집기에서 이름 개인화 필드와 여기를 클릭 링크가 있는 확인 전자 메일입니다.](assets/s_ncs_admin_survey_double-opt-in_sample_1b.png)

1. DCE를 사용하여 웹 양식에 URL을 연결합니다. 웹 양식이 아직 만들어지지 않았으므로 값을 만드는 즉시 값을 바꿉니다.

   ![확인 전자 메일의 여기를 클릭하세요 링크에 대한 웹 응용 프로그램 필드가 비어 있는 하이퍼텍스트 링크 창](assets/s_ncs_admin_survey_double-opt-in_sample_3.png)

1. 마지막으로 이 템플릿을 이전에 만든 임시 서비스에 연결합니다.

   ![구독 필드에서 확인 배달이 선택된 임시 서비스 편집 탭.](assets/s_ncs_admin_survey_double-opt-in_sample_3c.png)

### 3단계 - 가입 양식 만들기 {#step-3---creating-the-subscription-form}

웹 양식을 사용하면 수신자 구독과 구독 확인이 모두 가능합니다.

웹 양식 워크플로에는 다음 활동이 포함됩니다.

![웹 양식 워크플로: 미리 로드하고 테스트한 다음 빈 리드를 통해 웹 스크립트, 구독, 저장 종료](assets/s_ncs_admin_survey_double-opt-in_sample_4c.png)

이렇게 하려면 아래 단계를 수행합니다.

1. 웹 양식을 만들고 템플릿 **[!UICONTROL Newsletter subscription (subNewsletter)]**&#x200B;을(를) 선택하십시오.

   ![뉴스레터 구독(subNewsletter) 템플릿이 선택된 새 웹 응용 프로그램 대화 상자](assets/s_ncs_admin_survey_double-opt-in_sample_5a.png)

1. **[!UICONTROL Edit]** 탭에서 구독하려는 수신자에게 확인 메시지를 추가하려 하므로 기존 워크플로우를 구성해야 합니다.

   이렇게 하려면 **[!UICONTROL Preloading]** 상자를 두 번 클릭하고 다음과 같이 구성합니다.

   ![양식에서 참조되는 자동 로드 데이터가 포함된 활동 미리 로드 대화 상자 및 선택한 ID가 없는 경우 미리 로드를 건너뜁니다.](assets/s_ncs_admin_survey_double-opt-in_sample_5b.png)

   즉, 사용자가 확인 메시지의 링크를 통해 이 양식에 액세스하면 프로필 정보가 로드됩니다. 웹 사이트의 페이지를 통해 웹 양식에 액세스하면 정보가 로드되지 않습니다.

1. 워크플로우에 **[!UICONTROL Test]** 활동을 추가합니다.

   ![테스트 활동이 포함된 웹 양식 워크플로우가 전자 메일에서 구독, 저장 및 종료로 분기됩니다.](assets/s_ncs_admin_survey_double-opt-in_sample_6e.png)

   **[!UICONTROL Test]** 활동은 받는 사람 전자 메일과 관련이 있을 수 있습니다. 이 경우 다음과 같이 구성합니다.

   ![조건이 비어 있지 @email 테스트 활동 분기 편집기입니다.](assets/s_ncs_admin_survey_double-opt-in_sample_6d.png)

1. 워크플로우에 두 개의 **[!UICONTROL Script]** 활동을 추가합니다.

   ![테스트 활동의 각 분기에 스크립트 활동이 있는 웹 폼 워크플로우입니다.](assets/s_ncs_admin_survey_double-opt-in_sample_6f.png)

   첫 번째 **[!UICONTROL Script]** 활동은 수신자가 뉴스레터 구독을 확인할 때까지 차단 목록에 추가하다에 수신자를 추가합니다. 콘텐츠는 다음과 같아야 합니다.

   ```javascript
   ctx.recipient.@blackList=1
   ```

   스크립트 ctx.recipient.@blackList=1.![&#128279;](assets/s_ncs_admin_survey_double-opt-in_sample_6bbis.png)이 포함된 스크립트 활동

   두 번째 **[!UICONTROL Script]** 활동은 사용자에게 전송할 게재를 승인하고 뉴스레터를 구독합니다. 스크립트의 마지막 두 줄을 사용하면 임시 폴더에서 다른 폴더로 수신자를 전송하고 구독을 확인하는 즉시 기존 프로필과 조정할 수 있습니다.

   ```javascript
   ctx.recipient.@blackList=0
   nms.subscription.Subscribe("INTERNAL_NAME_OF_THE_NEWSLETTER", ctx.recipient, false)
   ctx.recipient.folder = <folder name="nmsRootRecipient"/>
   nms.subscription.Unsubscribe("TEMP", ctx.recipient)
   ```

   >[!NOTE]
   >
   >**[!UICONTROL Temp]** 파티션은 워크플로우를 사용하여 정기적으로 제거할 수도 있습니다.

   ![차단 목록, 구독, 폴더 및 구독 취소 스크립트 줄이 포함된 두 번째 스크립트 활동.](assets/s_ncs_admin_survey_double-opt-in_sample_6b.png)

1. **[!UICONTROL Subscription]** 활동을 두 번 클릭하여 구독 양식을 개인화하고 이전에 만든 임시 서비스에 확인란을 연결합니다.

   ![동의 확인란이 서비스 필드의 임시 서비스에 연결된 페이지 편집기.](assets/s_ncs_admin_survey_double-opt-in_sample_5c.png)

1. 양식 페이지에 입력한 정보를 저장하려면 **[!UICONTROL Storage]** 활동을 구성하십시오.

   이 활동을 사용하면 전용 임시 폴더에 수신자 프로필을 만들어 메시지를 보낼 수 있는 데이터베이스의 프로필과 별도로 설정할 수 있습니다.

   ![임시 폴더가 생성 폴더로 설정된 저장소 활동 대화 상자.](assets/s_ncs_admin_survey_double-opt-in_sample_5g.png)

   >[!NOTE]
   >
   >조정 옵션을 정의해서는 안 됩니다.

1. **[!UICONTROL End]** 활동을 두 개 추가하여 사용자에 대한 메시지를 표시합니다.

   구독이 완료되면 두 번째 **[!UICONTROL End]** 상자에 확인 메시지가 표시됩니다.

   ![구독이 완료되었다는 메시지가 표시된 활동 대화 상자를 종료합니다. 곧 뉴스레터를 받게 됩니다.](assets/s_ncs_admin_survey_double-opt-in_sample_5h.png)

1. 웹 양식을 만들고 구성하고 나면 이제 게재 템플릿에서 웹 양식을 참조하여 확인 메시지를 보낼 수 있습니다.

   ![뉴스레터 구독 이중 옵트인 웹 응용 프로그램을 가리키는 여기를 클릭하세요 링크가 있는 확인 게재.](assets/s_ncs_admin_survey_double-opt-in_sample_7b.png)

### 4단계 - 양식 게시 및 테스트 {#step-4---publishing-and-testing-the-form}

이제 양식을 게시하여 사용자가 액세스할 수 있도록 할 수 있습니다.

![웹 응용 프로그램 대시보드에 [게시] 단추가 있고 온라인에서 액세스할 수 있도록 게시해야 한다는 메시지가 있습니다.](assets/s_ncs_admin_survey_double-opt-in_sample_8b.png)

뉴스레터 구독에는 다음 단계가 포함됩니다.

1. 웹 사이트의 사용자는 구독 페이지에 로그인하고 양식을 승인합니다.

   ![브라우저 뉴스레터 구독 양식에 이름 및 전자 메일을 입력하고 동의 상자를 선택했으며 [구독] 단추를 추가했습니다.](assets/s_ncs_admin_survey_double-opt-in_sample_8c.png)

   이들은 브라우저의 메시지를 통해 요청이 고려되었다는 알림을 받습니다.

   ![요청이 등록되었으며 메시지가 나타난다는 브라우저 종료 페이지입니다.](assets/s_ncs_admin_survey_double-opt-in_sample_8d.png)

   사용자가 **[!UICONTROL Temp]** 폴더의 Adobe Campaign 데이터베이스에 추가되고 구독이 전자 메일로 확인될 때까지 프로필이 차단 목록에 추가하다에 있습니다.

   ![새 프로필이 선택되어 있고 더 이상 연락하지 않는 임시 수신자 폴더(모든 채널에서)가 확인되었습니다.](assets/s_ncs_admin_survey_double-opt-in_sample_8f.png)

1. 구독 승인 링크가 포함된 확인 메시지가 전송됩니다.

   ![뉴스레터 구독을 확인하려면 여기를 클릭하세요.](assets/s_ncs_admin_survey_double-opt-in_sample_8e.png)

1. 방문자가 이 링크를 클릭하면 브라우저에 승인 페이지가 표시됩니다.

   ![브라우저 페이지 제목이 [축하합니다]입니다! 이제 구독 확인이 활성 상태입니다.](assets/s_ncs_admin_survey_double-opt-in_sample_8.png)

   Adobe Campaign에서 사용자 프로필은 다음과 같이 업데이트됩니다.

   * 그들은 더 이상 차단 목록에 있지 않습니다.
   * 그들은 정보 서비스에 가입되어 있다.

     ![받는 사람 프로필이 업데이트되어 더 이상 연락하지 않고 뉴스레터 동영상 구독이 목록에 추가되었습니다.](assets/s_ncs_admin_survey_double-opt-in_sample_9.png)

## 선택한 값에 따라 다른 옵션 표시 {#displaying-different-options-depending-on-the-selected-values}

다음의 예에서, 사용자는 차량의 유형을 선택하라는 요청을 받는다. 선택한 유형에 따라 사용 가능한 차량 범주를 표시할 수 있습니다. 즉, 오른쪽 열에 표시되는 항목은 사용자의 선택에 따라 달라집니다.

![차량 종류 드롭다운 목록이 [선택]으로 설정된 차량 선택 페이지](assets/s_ncs_admin_survey_condition_sample0.png)

* 사용자가 &#39;자가용&#39;을 선택하면 &#39;컴팩트&#39;와 &#39;미니밴&#39; 중 선택이 제공된다.

  ![개인 차량을 선택한 차량 선택 페이지로 표준 및 소형 옵션을 표시합니다.](assets/s_ncs_admin_survey_condition_sample2.png)

* 사용자가 &#39;상용차&#39;를 선택하면 선택 항목이 드롭다운 목록에 표시됩니다.

  ![이동 트럭이 선택된 차량 선택 페이지 및 차량 유형의 클래스 드롭다운 목록](assets/s_ncs_admin_survey_condition_sample1.png)

이 예에서, 차량 타입은 데이터베이스에 저장되지 않는다. 드롭다운 목록은 다음과 같이 구성됩니다.

![Select, Personal car 및 Moving truck 값이 있는 자동차 콤보 상자 속성 유형](assets/s_ncs_admin_survey_condition_config1.png)

이 정보는 로컬 변수에 저장됩니다.

오른쪽 열의 조건부 표시가 컨테이너에 구성됩니다.

![자동차 종류 필드에 대해 선택한 변수 옵션이 있는 저장소 대화 상자.](assets/s_ncs_admin_survey_condition_config1bis.png)

* 전용 차량에 대한 필드의 조건부 가시성:

  ![개인용 자동차 컨테이너의 가시성 조건: 개인용 자동차와 같은 자동차의 종류](assets/s_ncs_admin_survey_condition_config2.png)

* 상용차 필드의 조건부 가시성:

  ![트럭/밴 컨테이너의 가시성 조건: 이동 트럭과 같은 자동차 종류.](assets/s_ncs_admin_survey_condition_config3.png)
