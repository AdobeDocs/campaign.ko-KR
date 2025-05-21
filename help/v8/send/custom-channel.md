---
title: 사용자 지정 외부 채널 시작
description: Adobe Campaign 웹을 사용하여 사용자 지정 외부 채널 게재를 만들고 보내는 방법을 알아봅니다
role: User
level: Beginner, Intermediate
source-git-commit: 4ba419c52d6804e4f25f88990c226081ef0a06e6
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---


# 사용자 지정 외부 채널 시작 {#gs-custom-channel}

Adobe Campaign을 사용하면 서드파티와 통합된 사용자 지정 외부 채널을 만들 수 있습니다. 그런 다음 이러한 채널을 기반으로 게재를 오케스트레이션하고 실행할 수 있습니다.

게재 만들기와 전송은 클라이언트 콘솔과 웹 UI 모두에서 수행할 수 있습니다. 그러나 사용자 지정 외부 채널은 클라이언트 콘솔에서만 수행됩니다.

사용자 지정 외부 채널을 기반으로 게재를 만들고 보내는 방법을 알아보려면 이 [페이지](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/gs-custom-channel.html?lang=ko)를 참조하세요.

클라이언트 콘솔에서 새 외부 사용자 지정 채널을 만드는 단계는 다음과 같습니다.

1. 스키마를 구성하십시오. [자세한 내용](#configure-schema)
1. 새 외부 계정을 만드십시오. [자세한 내용](#create-ext-account)
1. 새 게재 템플릿 만들기, [자세히 보기](#create-template)

## 스키마 구성{#configure-schema}

먼저 사용 가능한 채널 목록에 새 채널을 추가하도록 스키마를 구성해야 합니다.

1. Campaign 탐색기에서 **관리** > **구성** > **데이터 스키마**&#x200B;를 선택합니다.

1. 스키마 확장을 만들어 messageType 열거형을 새 채널로 확장합니다.

   예제:

   ```
   <enumeration basetype="byte" default="mail" label="Channel" name="messageType">
   <value desc="My Webpush" img="ncm:channels.png" label="My Webpush" name="webpush"
          value="122"/>
   </enumeration>
   ```

   ![](assets/cus-schema.png){zoomable="yes"}

## 새 외부 계정 만들기{#create-ext-account}

그런 다음 새 라우팅 외부 계정을 만들어야 합니다.

1. Campaign 탐색기에서 **관리** > **플랫폼** > **외부 계정**&#x200B;을 선택합니다.

1. 새 외부 계정을 만듭니다.

1. 채널을 선택하고 게재 모드를 **외부**(으)로 변경하십시오.

   ![](assets/cus-ext-account.png){zoomable="yes"}

## 새 게재 템플릿 만들기{#create-template}

이제 새 채널과 연결된 새 템플릿을 만들어 보겠습니다.

1. Campaign 탐색기에서 **리소스** > **템플릿** > **게재 템플릿**&#x200B;을 선택합니다.

1. 새 템플릿을 만듭니다.

1. **속성**&#x200B;을 클릭하고 올바른 폴더와 라우팅을 선택하십시오.

   ![](assets/cus-template.png){zoomable="yes"}

이제 새 채널을 사용할 수 있습니다. 이 채널을 기반으로 하여 게재를 만들고 실행할 수 있습니다.


