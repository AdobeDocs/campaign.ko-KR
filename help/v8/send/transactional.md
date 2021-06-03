---
product: Adobe Campaign
title: 캠페인 트랜잭션 메시지
description: 트랜잭션 메시지 시작
feature: 개요
role: Data Engineer
level: Beginner
source-git-commit: 973e04eb25887f63564b416515c6e229ed5233a4
workflow-type: tm+mt
source-wordcount: '1477'
ht-degree: 1%

---

# 트랜잭션 메시지 시작{#send-transactional-messages}

트랜잭션 메시지(메시지 센터)는 트리거 메시지를 관리하기 위해 설계된 캠페인 모듈입니다. 이러한 메시지는 정보 시스템에서 트리거된 이벤트에서 생성되며 다음을 수행할 수 있습니다.예를 들어 송장, 주문 확인, 출하 확인, 비밀번호 변경, 제품 미가용성 통지, 계정명세서 또는 웹사이트 계정 생성 등이 있습니다.

[!DNL :speech_balloon:] 관리 Cloud Services 사용자는  [Adobe](../start/campaign-faq.md#support) 에 문의하여 환경에 Campaign 트랜잭션 메시지를 설치하고 구성합니다.

트랜잭션 메시지는 보내는 데 사용됩니다.

* 예를 들어 주문 확인 또는 암호 재설정과 같은 알림
* 고객 작업에 대한 개별 실시간 응답
* 홍보되지 않는 콘텐츠

[!DNL :bulb:] 트랜잭션 메시지 설정은  [이 섹션에 자세히 설명되어 있습니다](../config/transactional-msg-settings.md).

[!DNL :bulb:]  [이 페이지의 트랜잭션 메시지 아키텍처를 이해합니다](../dev/architecture.md).

>[!CAUTION]
>
>트랜잭션 메시징에는 특정 라이센스가 필요합니다. 사용권 계약을 확인하십시오.

## 트랜잭션 메시지 템플릿 정의

각 이벤트는 개인화된 메시지를 트리거할 수 있습니다. 이 경우 각 이벤트 유형과 일치하는 메시지 템플릿을 만들어야 합니다. 템플릿에는 트랜잭션 메시지를 개인화하는 데 필요한 정보가 포함되어 있습니다. 템플릿을 사용하여 최종 타겟에 게재하기 전에 메시지 미리 보기를 테스트하고 시드 주소를 사용하여 증명을 전송할 수도 있습니다.

### 템플릿 만들기

메시지 템플릿을 만들려면 아래 단계를 수행하십시오.

1. Adobe Campaign 트리의 **[!UICONTROL Message Center >Transactional message templates]** 폴더로 이동합니다.
1. 트랜잭션 메시지 템플릿 목록에서 마우스 오른쪽 단추를 클릭하고 드롭다운 메뉴에서 **[!UICONTROL New]** 을 선택하거나 트랜잭션 메시지 템플릿 목록 위에 있는 **[!UICONTROL New]** 버튼을 클릭합니다.

   ![](assets/messagecenter_create_model_001.png)

1. 게재 창에서 사용할 채널에 적합한 게재 템플릿을 선택합니다.

   ![](assets/messagecenter_create_model_002.png)

1. 필요한 경우 레이블을 변경합니다.
1. 전송할 메시지와 일치하는 이벤트 유형을 선택합니다.

   ![](assets/messagecenter_create_model_003.png)

   Adobe Campaign에서 처리하도록 지정된 이벤트 유형은 Adobe이 제어 인스턴스에서 만들어야 합니다.

   >[!NOTE]
   >
   >이벤트 유형은 두 개 이상의 템플릿에 연결할 수 없습니다.

1. 특성과 설명을 입력한 다음 **[!UICONTROL Continue]** 을 클릭하여 메시지 본문을 만듭니다. [메시지 콘텐츠 만들기](#create-message-content)를 참조하십시오.

### 컨텐츠 만들기{#create-message-content}

트랜잭션 메시지 콘텐츠의 정의는 Adobe Campaign의 모든 게재와 동일합니다. 예를 들어 이메일 게재의 경우 HTML 또는 텍스트 형식으로 콘텐츠를 만들거나 첨부 파일을 추가하거나 게재 개체를 개인화할 수 있습니다. 이 작업에 대한 자세한 정보는 [이 섹션](../start/create-message.md)을 참조하십시오.

>[!CAUTION]
>
>메시지에 포함된 이미지는 공개적으로 액세스할 수 있어야 합니다. Adobe Campaign은 트랜잭션 메시지를 위한 이미지 업로드 메커니즘을 제공하지 않습니다.\
>JSSP 또는 webApp과 달리 `<%=`에는 기본 이스케이프가 없습니다.
>
>이벤트에서 들어오는 각 데이터를 제대로 이스케이프 처리해야 합니다. 이스케이프는 이 필드를 사용하는 방식에 따라 다릅니다. 예를 들어 URL 내에서 encodeURIComponent를 사용하십시오. HTML에 표시되도록 하려면 escapeXMLString을 사용할 수 있습니다.

메시지 콘텐츠를 정의하고 나면 이벤트 정보를 메시지 본문에 통합하여 개인화할 수 있습니다. 개인화 태그 덕분에 텍스트 본문에 이벤트 정보가 삽입됩니다.

![](assets/messagecenter_create_content.png)

* 페이로드에서 모든 개인화 필드를 가져옵니다.
* 트랜잭션 메시지에서 하나 또는 여러 개의 개인화 블록을 참조할 수 있습니다. 실행 인스턴스에 게시하는 동안 블록 컨텐츠가 게재 콘텐츠에 추가됩니다.

이메일 메시지 본문에 개인화 태그를 삽입하려면 다음 단계를 적용합니다.

1. 메시지 템플릿에서 이메일 형식(HTML 또는 텍스트)과 일치하는 탭을 클릭합니다.
1. 메시지 본문을 입력합니다.
1. 텍스트 본문에 **[!UICONTROL Real time events>Event XML]** 메뉴를 사용하여 태그를 삽입합니다.

   ![](assets/messagecenter_create_custo_1.png)

1. 다음 구문을 사용하여 태그를 채웁니다.**요소 이름**.@**특성 이름**&#x200B;은 아래와 같이 표시됩니다.

   ![](assets/messagecenter_create_custo_2.png)

### 시드 주소 추가{#add-seeds}

시드 주소를 사용하면 메시지를 보내기 전에 메시지 미리 보기를 표시하고, 증명을 보내고, 메시지 개인화를 테스트할 수 있습니다. 시드 주소는 게재에 연결되므로 다른 게재에 사용할 수 없습니다.

1. 트랜잭션 메시지 템플릿에서 **[!UICONTROL Seed addresses]** 탭을 클릭한 다음 **[!UICONTROL Add]** 단추를 클릭합니다.

   ![](assets/messagecenter_create_seed_1.png)

1. 나중에 쉽게 선택할 수 있도록 레이블을 지정한 다음 시드 주소(통신 채널에 따라 이메일 또는 휴대폰)를 입력합니다.

1. 외부 식별자를 입력합니다.이 선택적 필드를 사용하면 비즈니스 키(고유 ID, 이름 + 이메일 등)를 입력할 수 있습니다. 이는 프로필을 식별하는 데 사용되는 웹 사이트의 모든 애플리케이션에서 일반적으로 사용됩니다. 이 필드가 Adobe Campaign 마케팅 데이터베이스에도 있으면 데이터베이스의 프로필로 이벤트를 조정할 수 있습니다.

   ![](assets/messagecenter_create_seed_2.png)

1. 테스트 데이터를 삽입합니다. [이 섹션](#personalization-data)을 참조하십시오.

   ![](assets/messagecenter_create_custo_3.png)

1. **[!UICONTROL Ok]** 을 클릭하여 시드 주소 만들기를 확인합니다.

1. 프로세스를 반복하여 필요한 수만큼 주소를 만듭니다.

   ![](assets/messagecenter_create_seed_6.png)

주소가 만들어지면 미리 보기 및 개인화에 액세스할 수 있습니다.

### 개인화 데이터 추가{#personalization-data}

메시지 템플릿에 데이터를 추가하여 트랜잭션 메시지 개인화를 테스트할 수 있습니다. 이를 통해 미리 보기를 생성하거나 증명을 보낼 수 있습니다. **게재 가능성** 모듈을 설치하는 경우 이 데이터를 사용하면 다양한 데스크탑, 웹 또는 모바일 클라이언트에 대한 메시지 렌더링을 표시할 수 있습니다.

이 데이터의 목적은 최종 게재 전에 메시지를 테스트하는 것입니다. 이 메시지는 메시지 센터에서 처리할 실제 데이터와 일치하지 않습니다. 그러나 XML 구조는 아래와 같이 실행 인스턴스에 저장된 이벤트의 구조와 동일해야 합니다.

![](assets/messagecenter_create_custo_4.png)

이 정보를 사용하면 개인화 태그를 사용하여 메시지 콘텐츠를 개인화할 수 있습니다.

1. 메시지 템플릿에서 **[!UICONTROL Seed addresses]** 탭을 클릭합니다.
1. 이벤트 콘텐츠에 XML 형식으로 테스트 정보를 입력합니다.

   ![](assets/messagecenter_create_custo_3.png)

### 트랜잭션 메시지 미리 보기{#transactional-message-preview}

하나 이상의 시드 주소와 메시지 본문을 생성했으면 메시지를 미리 보고 개인화를 확인할 수 있습니다.

1. 메시지 템플릿에서 **[!UICONTROL Preview]** 탭을 클릭한 다음, 드롭다운 목록에서 **[!UICONTROL A seed address]** 를 선택합니다.

   ![](assets/messagecenter_preview_1.png)

1. 이전에 만든 시드 주소를 선택하여 개인화된 메시지를 표시합니다.

   ![](assets/messagecenter_create_seed_7.png)

### 증명 보내기

이전에 만든 시드 주소로 증명을 보내 메시지 전달을 테스트할 수 있습니다.

증명 전송에는 게재와 동일한 프로세스가 포함됩니다.

[!DNL :arrow_upper_right:]  [Campaign Classic v7 설명서에서 증명에 대해 자세히 알아보십시오]((https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html))

그러나 트랜잭션 메시지의 증명을 보내려면 다음 작업을 수행해야 합니다.

* 개인화 테스트 데이터를 사용하여 하나 이상의 [시드 주소](#add-seeds)를 만듭니다
* 메시지 콘텐츠 만들기

증명을 보내려면

1. 배달 창에서 **[!UICONTROL Send a proof]** 버튼을 클릭합니다.
1. 게재를 분석합니다.
1. 오류를 수정하고 게재를 확인합니다.

   ![](assets/messagecenter_send_proof_001.png)

1. 메시지가 시드 주소에 전달되었고 콘텐츠가 구성을 준수하는지 확인합니다.

   ![](assets/messagecenter_send_proof_002.png)

**[!UICONTROL Audit]** 탭을 통해 각 템플릿에서 증명에 액세스할 수 있습니다.

![](assets/messagecenter_send_proof_003.png)

### 템플릿 게시

컨트롤 인스턴스에서 만든 메시지 템플릿이 완료되면 게시할 수 있습니다. 이 프로세스는 모든 실행 인스턴스에도 게시합니다.

>[!NOTE]
>
>트랜잭션 메시지 템플릿을 게시할 때 유형화 규칙도 실행 인스턴스에 자동으로 게시됩니다.

게시를 사용하면 실행 인스턴스에 두 개의 메시지 템플릿을 자동으로 만들 수 있으며, 이 템플릿을 사용하면 실시간 및 배치 이벤트에 연결된 메시지를 보낼 수 있습니다.

>[!CAUTION]
>
>템플릿을 변경할 때마다 트랜잭션 메시지 게재 중에 이러한 변경 사항이 적용되도록 다시 게시해야 합니다.

1. 컨트롤 인스턴스에서 트리의 **[!UICONTROL Message Center > Transactional message templates]** 폴더로 이동합니다.
1. 실행 인스턴스에 게시할 템플릿을 선택합니다.
1. **[!UICONTROL Publish]**&#x200B;을(를) 클릭합니다.

   ![](assets/messagecenter_publish_template.png)

게시가 완료되면 일괄 처리에 적용할 메시지 템플릿과 실시간 유형 이벤트가 모두 **[!UICONTROL Administration > Production > Message Center Execution> Default > Transactional message templates]** 폴더의 프로덕션 인스턴스의 트리에 만들어집니다.

![](assets/messagecenter_deployed_model.png)

템플릿이 게시되면 해당 이벤트가 트리거되면 실행 인스턴스에서 이벤트를 수신하고 트랜잭션 템플릿에 연결하고 해당 트랜잭션 메시지를 각 수신자에게 보냅니다.

>[!NOTE]
>
>보낸 사람 주소와 같은 트랜잭션 메시지 템플릿의 기존 필드를 빈 값으로 바꾸면 트랜잭션 메시지가 다시 게시되면 실행 인스턴스의 해당 필드가 업데이트되지 않습니다. 이전 값이 여전히 포함됩니다.
>
>그러나 비어 있지 않은 값을 추가하는 경우 다음 게시 후 해당 필드가 평소대로 업데이트됩니다.


### 템플릿 게시 취소

메시지 템플릿이 실행 인스턴스에 게시되면 게시 취소할 수 있습니다.

* 실제로, 게시된 템플릿은 해당 이벤트가 트리거되는 경우 여전히 호출할 수 있습니다.더 이상 메시지 템플릿을 사용하지 않는 경우 게시를 취소하는 것이 좋습니다. 실수로 원치 않는 트랜잭션 메시지를 보내지 않기 위한 것입니다.

   예를 들어, 크리스마스 캠페인에만 사용하는 메시지 템플릿을 게시했습니다. 크리스마스 기간이 끝난 후에 게시를 취소하고, 내년에 다시 게시할 수 있습니다.

* 또한 **[!UICONTROL Published]** 상태가 있는 트랜잭션 메시지 템플릿은 삭제할 수 없습니다. 먼저 게시 취소해야 합니다.

트랜잭션 메시지 템플릿 게시를 취소하려면 아래 단계를 따르십시오.

1. 컨트롤 인스턴스에서 **[!UICONTROL Message Center > Transactional message templates]** 폴더를 찾습니다.
1. 게시를 취소할 템플릿을 선택합니다.
1. **[!UICONTROL Unpublish]**&#x200B;을(를) 클릭합니다.
1. **[!UICONTROL Start]**&#x200B;을(를) 클릭합니다.

![](assets/message-center-unpublish.png)

트랜잭션 메시지 템플릿 상태가 **[!UICONTROL Published]**&#x200B;에서 **[!UICONTROL Being edited]**(으)로 다시 변경됩니다.

게시 취소가 완료되면

* 두 메시지 템플릿(배치 및 실시간 유형 이벤트에 적용됨)이 각 실행 인스턴스에서 모두 삭제됩니다.

   더 이상 **[!UICONTROL Administration > Production > Message Center Execution > Default > Transactional message templates]** 폴더에 나타나지 않습니다.

* 템플릿의 게시를 취소하면 컨트롤 인스턴스에서 해당 템플릿을 삭제할 수 있습니다.

   이렇게 하려면 목록에서 해당 항목을 선택하고 화면 오른쪽 위의 **[!UICONTROL Delete]** 버튼을 클릭합니다.
